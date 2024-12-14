добрый день.
Задание 1.
ознакомился с зависимостями в packages.json
основные зависимости связаны с react. нет зоопарка фреймворков. нет необходимости в сильной изоляции модулей.
благодаря тренировочному заданию по webmodule federation получается, что опыта у моей команды разрабов (состоящей из меня 1) больше 
с webpack module federation чем с single spa :D
по итогу для реализации переезда монолита на микрофронтенды выбран фреймворк - webpack module federation
ознакомился с компонентами api.js auth.js
выделил для себя 3 микрофронтенда - microfrontends: auth, cards, profile и host как управляющий
такое разделение получилось так как в проекте на мой взгляд присуствует три основных бизнес домена - 
управление фотографиями
управление профайлом
аутентификация юзера

примерная новая структура

+---auth-microfrontend (микрофронтенд аутентификации)
¦   ¦   .babelrc
¦   ¦   .gitignore
¦   ¦   compilation.config.js
¦   ¦   package.json
¦   ¦   webpack.config.js
¦   ¦   
¦   L---src
¦       ¦   App.jsx
¦       ¦   index.css
¦       ¦   index.html
¦       ¦   index.js
¦       ¦   
¦       +---components
¦       ¦       InfoTooltip.js
¦       ¦       Login.js
¦       ¦       Register.js
¦       ¦       
¦       +---images
¦       ¦       close.svg
¦       ¦       error-icon.svg
¦       ¦       
¦       +---styles
¦       ¦   +---auth-form
¦       ¦   +---login
¦       ¦   L---popup           
¦       L---utils
¦               auth.js
¦               
+---cards-microfrontend (микрофронтенд по работе с картинками)
¦   ¦   .babelrc
¦   ¦   .gitignore
¦   ¦   compilation.config.js
¦   ¦   package.json
¦   ¦   webpack.config.js
¦   ¦   
¦   L---src
¦       ¦   App.jsx
¦       ¦   index.css
¦       ¦   index.html
¦       ¦   index.js
¦       ¦   
¦       +---components
¦       ¦       AddPlacePopup.js
¦       ¦       Card.js
¦       ¦       ImagePopup.js
¦       ¦       
¦       +---images
¦       ¦       card_1.jpg
¦       ¦       card_2.jpg
¦       ¦       card_3.jpg
¦       ¦       delete-icon.svg
¦       ¦       like-active.svg
¦       ¦       like-inactive.svg
¦       ¦       
¦       +---styles
¦       ¦   +---card
¦       ¦   +---places
¦       ¦   L---popup
¦       L---utils
¦               api.js
¦               
+---host-microfrontend (управляющий микрофронтенд)
¦   ¦   .babelrc
¦   ¦   .gitignore
¦   ¦   compilation.config.js
¦   ¦   package.json
¦   ¦   webpack.config.js
¦   ¦   
¦   L---src
¦       ¦   App.jsx
¦       ¦   index.css
¦       ¦   index.html
¦       ¦   index.js
¦       ¦   
¦       +---components
¦       ¦       App.js
¦       ¦       Footer.js
¦       ¦       Header.js
¦       ¦       Main.js
¦       ¦       ProtectedRoute.js
¦       ¦       
¦       +---contexts
¦       ¦       CurrentUserContext.js
¦       ¦       
¦       +---images
¦       ¦       avatar.jpg
¦       ¦       edit-icon.svg
¦       ¦       logo.svg
¦       ¦       
¦       +---styles
¦       ¦   +---content
¦       ¦   +---footer
¦       ¦   +---header
¦       ¦   L---page            
¦       L---utils
¦               api.js
¦               
L---profile-microfrontend (микрофронтенд по работе с профилем)
    ¦   .babelrc
    ¦   .gitignore
    ¦   compilation.config.js
    ¦   package.json
    ¦   webpack.config.js
    ¦   
    L---src
        ¦   App.jsx
        ¦   index.css
        ¦   index.html
        ¦   index.js
        ¦   
        +---components
        ¦       EditAvatarPopup.js
        ¦       EditProfilePopup.js
        ¦       PopupWithForm.js
        ¦       
        +---images
        ¦       avatar.jpg
        ¦       close.svg
        ¦       
        +---styles
        ¦   +---popup  
        ¦   L---profile
        L---utils
                api.js
                
ранее с реактом не работал. но хочу разобраться и доделать 3 часть первого задание позже. Спасибо.

Задание 2.
ссылка на схему - https://drive.google.com/file/d/1edr3JZqo1tYYfpcaZae856HLAwMi9Jrd/view?usp=sharing