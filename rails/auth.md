# Autenticación Rails
## Usando la gema "Devise"

### Configuración para usar devise
1. Buscar la gema en [RubyGems](https://rubygems.org/)
2. Agregar la gema al archivo GemFile.rb de nuestro proyecto ```$ gem 'devise', '~> 4.4', '>= 4.4.3'```
3. Instalar las gemas usando el comando ```$ bundle install```
4. Verificar que tengamos la gema instalada ```$ bundle list ```

### Pasos para usar devise
1. Configuración inicial devise ```$ rails generate devise:install ```
    >Este comando va a instalar el archivo de configuración en la carpeta `initializers` y tambien algunos mensajes que se podran modificar despues, para las notificaciones que se pueden ver en  la aplicación

2. Garantizar que tenemos una ruta "raiz" para nuestro proyecto 
    ```ruby 
    root to: "view#index"
    ```

3. Agregar los mensajes flash en ```app/views/layouts/application.html.erb```
    ```html
    <div class="notice">
        <%= notice %>
    </div>
    <div class="alert">
        <%= alert %>
    </div>
    ```
> En este momento el proyecto ya tiene configuradas las vistas para manejar el proceso de autenticación, sin embargo normalmente necesitamos personalizar estas vistas.
4. Verificar las rutas que estan creadas por devise
    ```
    $ rails routes
    ```

5. Agregar las vistas para personalizarlas 
    ```
    $ rails g devise:views
    ```

### Generar Usuario con sistema de autenticación

1. ```$ rails generate devise User ```
    >Este comando va a crear un modelo  ```User``` con los campos email y password y generara algunos campos como la ultima vez que se autentico, la ultima vez que se reinio la contraseña, etc.
2. Con el anterior comando se generaron los archivos de migración, ahora vamos a aplicar esta migración usando ```rails db:migrate ```

Los anteriores pasos deben generar el siguiente codigo
```ruby
app/models/user.rb

class User < ActiveRecord::Base
  devise :database_authenticatable, :registerable, :recoverable, :reemberable, :trackable, :validatable
end
```