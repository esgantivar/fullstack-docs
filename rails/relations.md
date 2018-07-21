# Asociaciones entre Modelos
En rails una asociación es una conexión entre dos modelos ```Active Record```.

Consideremos un modelo sencillo: Autores y Libros. Cada autor puede tener muchos libros. Sin asociaciones la declaracion de los modelos es 
```ruby

class Author < ApplicationRecord
end
 
class Book < ApplicationRecord
end

```

Ahora supongamos que queremos un nuevo libro para un autor que ya existe, necesitariamos algo como lo siguiente

```ruby
@book = Book.create(published_at: Time.now, author_id: @author.id)
```

O consideremos borrar un autor  y garantizar que todos los libros asociados 

```ruby 
@books = Book.where(author_id: @author.id)
@books.each do |book|
  book.destroy
end
@author.destroy
```
Con las asociaciones de rails podemos simplificar esta operacion indicandole a rails que existe una relación entre los dos modelos

```ruby
class Author < ApplicationRecord
  has_many :books, dependent: :destroy
end
 
class Book < ApplicationRecord
  belongs_to :author
end
```
Con lo anterior podemos crear un nuevo libro asi:
```ruby
@book = @author.books.create(published_at: Time.now)
```
Y la operación de borrado:
```ruby
@author.destroy
```
## Uno a Muchos
Esta relación entre modelos la podremos implementar usando el tipo de asociación ```belongs_to```

Por ejemplo para nuestro ejemplo un libro tiene exactamente un autor, esta asociación se declararia de la siguiente manera
```ruby
class Book < ApplicationRecord
  belongs_to :author
end
```

Para que la anterior asociacion funcione debemos implementar la siguiente migración

```ruby
class CreateBooks < ActiveRecord::Migration[5.2]
  def change
    # Crea una tabla con un atributo llamado nombre de tipo string 
    create_table :authors do |t|
      t.string :name
      t.timestamps
    end
 
    # Crea una tabla libro con un atributo publicado el de tipo datetime
    # Adicionalmente crea una relacion con la tabla autor indexada
    create_table :books do |t|
      t.belongs_to :author, index: true
      # podemos asignar mas restricciones de la siguiente manera t.belongs_to :author, index: { unique: true }, foreign_key: true
      t.datetime :published_at
      t.timestamps
    end
  end
end
```

Como complemento a la relación ```belongs_to``` tenemos la relacion ```has_many```
```ruby
class Author < ApplicationRecord
  has_many :books
end
```
## Muchos a Muchos (Many to Many)
Ahora consideremos una relacion muchos a muchos, por ejemplo una tienda puede tener muchos productos y un producto puede estar en muchas tiendas 

Para este particular caso es necesario una tabla puente para manejar la relacion 

```ruby
class Store < ApplicationRecord
  has_many :stocks
  has_many :products, through: :stocks
end
 
class Stock < ApplicationRecord
  belongs_to :store
  belongs_to :product
end
 
class Product < ApplicationRecord
  has_many :stocks
  has_many :stores, through: :stocks
end
```

La migración correspondiente es:
```ruby
class CreateStock < ActiveRecord::Migration[5.2]
  def change
    create_table :stores do |t|
      t.string :name
      t.timestamps
    end
 
    create_table :products do |t|
      t.string :name
      t.timestamps
    end
 
    create_table :stocks do |t|
      t.belongs_to :store, index: true
      t.belongs_to :product, index: true
      t.integer :available
      t.timestamps
    end
  end
end
```