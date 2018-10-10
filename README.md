# Ngapp

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.0.3.

## Prerequisite
To use this application, you need below dependencies..

1. Node.js `https://nodejs.org/en/download/` [Recommended Node.js 6.10.x]
2. Angular Cli. Open command prompt and install `npm install @angular/cli -g`
3. Clone the ngapp repository
4. On Command Prompt, cd into 'ngapp' directory, 
   then Run `npm install`


## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## API Server

We have API server that provides GET, PUT, POST and DELETE methods, handles CORS, Authentication.

The code for api-server located in /server/api-server.js
and the backend is a simple json file /server/db.json

To start API server, run the below command, this starts api-server at port 7070

> npm run api

we have below apis, products are taken from wikipedia smart phone page

    1. /api/products
    2. /api/brands
    3. /api/cities
    4. /api/states
    
we also have delayed resonse apis, useful for promise.all during promise workshop. Delayed api adds random 2-8 seconds delay before response.

    1. /delayed/api/products
    2. /delayed/api/brands
    3. /delayed/api/cities
    4. /delayed/api/states

### Authentication

Note, Authentication is not enabled by default.
We have basic oauth authentication for api-server, which can be enabled on need basis by running below command 

To run the server with authentication, we need below command
 
   > npm run api-with-auth

We have three users with hardcoded password.

    staff: staff
    password: staff

    username: user
    password: user

    username: admin
    password: admin

To Authenticate with the server, the client should call below api

    POST http://localhost:7070/oauth/token

must send url-form encoded key/values, with 'username' and 'password' field


Server validate username and password, send JSON reply with serialized user object (without password), user id, JWT Token.

After Authentication, the client should send "Authorization" with Bearer scheme

    Example:

    Authorization: Bearer flfkalsdjflkajdfalflkjdslkfjaslk.kfalsjdklfajsl

    
== Cors ==

Cors is included by default, to disable Cors, command line "noCors" while running the server. We disable cors for demonstration purpose.

       > npm run api-nocors

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. `ng build` build the files in development mode, that includes JIT Compilation for Angular application at browser side.

## Production Build

Run `ng build -prod` to build the project in the production build. Production flag enable Angular `enableProdMode()`.  The build artifacts will be stored in the `dist/` directory. 

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).
Before running the tests make sure you are serving the app via `ng serve`.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
