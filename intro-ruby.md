# Ruby de 0 a 100% :nerd_face:

## Introduccion
### Tipos de datos

```ruby
my_num = 25
my_boolean = true
my_string = "Ruby"
```

### Matematicas
* Suma (+)
* Resta (-)
* Multiplicación (*)
* Division (/)
* Exponenciación (**)
* Modulo (%)
```ruby
  puts 5*5
```

### Impresión en Consola
```ruby
my_num = 100
print my_num
puts my_num
```

### Todo en ruby es un objeto
#### '.length'
```ruby
  puts "I love ruby".length
```

#### '.reverse'
```ruby
  puts "I love ruby".reverse
```
#### Letras
```ruby
puts "eric".upcase
puts "eric".downcase
```

### Comentarios
```ruby
# Comentarios de una linea
=begin
Comentario multilinea
=end
```

### Capturar información Consola

```ruby
print "Cual es tu nombre? "
first_name = gets.chomp
first_name.capitalize!

print "Cual es tu apellido? "
last_name = gets.chomp
last_name.capitalize!

print "En que ciudad naciste? "
city = gets.chomp
city.capitalize!

puts "Tu nombre es #{first_name} #{last_name} y naciste en #{city}!"
```

## Estructuras de Control
1. == (Igualdad)
2. != (Diferencia)
3. >, <, <=, >=

### If
```ruby
print "Integer please: "
user_num = Integer(gets.chomp)

if user_num < 0
  puts "El numero es negativo!"
elsif user_num > 0
  puts "El numero es positivo!"
else
  puts "Es un cero!"
end
```

### unless

```ruby
hungry = false

unless hungry
  puts "Escribamos mas codigos!"
else
  puts "Tiempo del break!"
end
```

### Operadores Logicos
1. Or (||)
2. And (&&)


## Algunas operaciones sobre strings
### Concatenacion
```ruby
name = 'Sneyder'
puts "Mi nombre es: #{name}"
```

### Multiplicación(*)
```ruby
s = "-*-"
puts = s*10
```

## Ciclos
### While
```ruby
counter = 1
while counter < 11
  puts counter
  counter = counter + 1
end
```

### Until
```ruby
counter = 1
until counter > 10
  puts counter
  counter +=1
end
```

### For
#### Rango incluyente
```ruby
for num in 1...10
  puts num
end
```
#### Rango excluyente
```ruby
for num in 1...10
  puts num
end
```

### Arreglos

```ruby
my_array = [1,2,3,4,5]
```

#### Iterar un array
```ruby
array.each { |x|
  x += 10
  puts "#{x}"
}
```

### Ciclo Time

```ruby
10.times { print "spam" }
```

## Hashes
```ruby
my_hash = { "name" => "Eric",
  "age" => 26,
  "hungry?" => true
}

puts my_hash["name"]
puts my_hash["age"]
puts my_hash["hungry?"]

puts my_hash
```

```ruby
pets = Hash.new


pets['cat']='cat'

puts pets['cat']
```


```ruby
family = { "Homer" => "dad",
  "Marge" => "mom",
  "Lisa" => "sister",
  "Maggie" => "sister",
  "Abe" => "grandpa",
  "Santa's Little Helper" => "dog"
}
family.each { |x, y| puts "#{x}: #{y}" }
```

## Metodos
```ruby
def mi_primer_metodo
  puts "mi primer metodo"
end


```
