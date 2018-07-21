# Autenticación Rails
## Usando la gema "Devise"

### Configuración para usar devise
1. Buscar la gema en [RubyGems](https://rubygems.org/)
2. Agregar la gema al archivo GemFile.rb de nuestro proyecto ```$ gem 'devise', '~> 4.4', '>= 4.4.3'```
3. Instalar las gemas usando el comando ```$ bundle install```
4. Verificar que tengamos la gema instalada ```$ bundle list ```

### Pasos para usar devise
1. Configuración inicial devise ```$ rails generate devise:install ```
⋅⋅*Este comando va a instalar el archivo de configuración en la carpeta `initializers` y tambien algunos mensajes que se podran modificar despues para las notificaciones que se pueden ver en  la aplicación
