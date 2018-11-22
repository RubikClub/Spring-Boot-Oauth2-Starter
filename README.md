<p align="center">
<img src="https://github.com/RubikClub/Spring-Boot-Oauth2-Starter/blob/master/public/logo.png" alt="Rubik">
</p>
<h2 align="center">Spring Boot Oauth2</h2>

<p align="center">
<a href="https://github.com/95Revolution/Kiyamuda-pwa/blob/master/LICENSE"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
<a href="https://join.slack.com/t/rubikclub/shared_invite/enQtNDg0NzcwMjkzMDA4LTNjMTI3Njc4Y2JjYWExYjNkYjk1NTE5NmM5NmU1NzVlNTllMTZhODFjZTFmOGNiMDVkYTMzZDIzYjA2ZGQ0Y2U"><img src="https://img.shields.io/badge/chat-on%20slack-7289da.svg" alt="Slack"></a>
</p>

# About Project

This Project `Spring Boot Oauth2` is a starter template that will guide you to configure your own social logins for individual projects.

This project is an open source initiative launched by `Rubik Club` :blush: in order to maintain a standarized *Dev Community*  :heart: within its members.

If you are a _huge nerd_ like us help us to help you by contributing to this awesome adventure.

Show us you're capabilities :muscle: and the spread message about our journey!!!

## Tech Stack

This projects backend is is fully powered with the awesome :sunglasses: **Spring Boot** and we are using our favorite frontend framework **React** for client side. 

### Current Progress

Right now we have successfully added social logins for `Google`, `FaceBook`, and `GitHub`. 
If you like to tackle other platforms feel free to add them to the project.

## How to setup

Clone the project using

```sh
git clone
```

Run the REST API via

```sh
mvn spring-boot:run
```

Run the Client via

```sh
cd client && npm start
```

Now, find :beetle: and create issues so we can help you :grin:.

## Guidelines

We are modularizing our project for the ease of management. 
When you first init the project don't forget to add the necessary **CLIENT IDs** and **CLIENT SECRETs** to the `application.yml` file below.

```yml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/spring_social?useSSL=false
    username: demouser
    password: demouser

  jpa:
    show-sql: true
    hibernate:
      ddl-auto: update
      naming-strategy: org.hibernate.cfg.ImprovedNamingStrategy
    properties:
      hibernate:
        dialect: org.hibernate.dialect.MySQL5InnoDBDialect
  security:
    oauth2:
      client:
        registration:
          google:
            clientId: 5014057553-8gm9um6vnli3cle5rgigcdjpdrid14m9.apps.googleusercontent.com
            clientSecret: tWZKVLxaD_ARWsriiiUFYoIk
            redirectUriTemplate: "{baseUrl}/oauth2/callback/{registrationId}"
            scope:
            - email
            - profile
          facebook:
            clientId: 121189305185277
            clientSecret: 42ffe5aa7379e8326387e0fe16f34132
            redirectUriTemplate: "{baseUrl}/oauth2/callback/{registrationId}"
            scope:
            - email
            - public_profile
          github:
            clientId: d3e47fc2ddd966fa4352
            clientSecret: 3bc0f6b8332f93076354c2a5bada2f5a05aea60d
            redirectUriTemplate: "{baseUrl}/oauth2/callback/{registrationId}"
            scope:
            - user:email
            - read:user
        provider:
          facebook:
            authorizationUri: https://www.facebook.com/v3.0/dialog/oauth
            tokenUri: https://graph.facebook.com/v3.0/oauth/access_token
            userInfoUri: https://graph.facebook.com/v3.0/me?fields=id,first_name,middle_name,last_name,name,email,verified,is_verified,picture.width(250).height(250)
app:
  auth:
    tokenSecret: 926D96C90030DD58429D2751AC1BDBBC
    tokenExpirationMsec: 864000000
  oauth2:    
    authorizedRedirectUris:
    - http://localhost:3000/oauth2/redirect
    - myandroidapp://oauth2/redirect
    - myiosapp://oauth2/redirect
```