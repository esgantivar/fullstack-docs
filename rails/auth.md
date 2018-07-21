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
> En este momento el proyecto ya tiene configuradas las vistas para manejar el proceso de autenticación, sin embargo si n
necesitamos personalizar estas vistas.
4. Verificar las rutas que estan creadas por devise
    ```
    $ rails routes
    ```

5. Agregar las vistas para personalizarlas 
    ```
    $ rails g devise:views
    ```
