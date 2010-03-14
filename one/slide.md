!SLIDE
# Sammy #

![Sammy and Jack](sammy.jpg)

!SLIDE bullets incremental
# Sammy #

* framework Javascript
* basé sur jQuery
* basé sur les événements
* inspiré de Sinatra
* crée par Aaron Quint

!SLIDE center 

# Sinatra ![Sammy and Jack](sinatra.png) #

* Framework Ruby cool

![Sammy and Jack](haha.jpg)


!SLIDE code

# De ruby ... #

       require 'rubygems'
       require 'sinatra'
       get '/hi' do
         "Hello World!"
       end

!SLIDE code

# .. à javascript #

       $.sammy(function() {
         this.get('#/hi', function() {
             $('#main').text('Hello World!');
          });
        });

!SLIDE bullets incremental smaller

# Fonctionnalités #

* RESTful
* Gestion des événements
* Plusieurs instances sur la même page
* Gestion de l'historique
* Système de plugin
* Testé intensivement
* Libre ! (MIT)

!SLIDE subsection

# Application #

!SLIDE code smaller

# Une application simple #

    var app = $.sammy(function() {
         this.get('#/hi', function() {
             $('#main').text('Hello World!');
          });
        });
    app.run();

!SLIDE code smaller

# Application sur un élément du document #

    var app = $.sammy('#plop', function() {
         this.get('#/hi', function() {
             $('#main').text('Hello World!');
          });
        });
    app.run()
  
!SLIDE subsection

# Routes #

!SLIDE

## GET ##

       get('#/hi', function() {
           $('#main').text('Hello World!');
       });

       <a href="#/hi">Hi !</a>

!SLIDE code

## POST ##

       post('#/hi', function() {
           $('#main').text('POST!');
       });


       <form action="#/hi" method="post">
         <input type="submit" value="Submit" />
       </form>

!SLIDE

# put() et del() existe aussi #

!SLIDE subsection

# Evenements #

!SLIDE code

        bind('click', function(e) {
            console.log(e);
        });


        bind('hello-word', function(e) {
            console.log(e);
        });

        trigger('hello-word', 'plop');


!SLIDE subsection

# Plugins #

!SLIDE bullets incremental

* Template (Mustache, haml, ...)
* Cache (LocalStorage, SessionStorage, Cookie)
* JSON
* ...

!SLIDE code

       use(Sammy.NestedParams);


       var app = $.sammy(function() {
              this.use(Sammy.JSON);
              
              this.get('#/', function() {
                this.json({user_id: 123});
              });
            })


!SLIDE bullets small

# Ressources #

* http://github.com/quirkey/sammy
* http://code.quirkey.com/sammy/
* http://jquery.com/

