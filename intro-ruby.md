# 0 a 100% Ruby

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
print "What's your first name? "
first_name = gets.chomp
first_name.capitalize!

print "What's your last name? "
last_name = gets.chomp
last_name.capitalize!

print "What city are you from? "
city = gets.chomp
city.capitalize!

print "What state or province are you from? "
state = gets.chomp
state.upcase!

puts "Your name is #{first_name} #{last_name} and you're from #{city}, #{state}!"
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
