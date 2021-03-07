# AngularPwaApp

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 10.1.7.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

## **Details**
Steps to add Service Worker in Your Project / How to make your application A PWA ?

1.	While creating a new application –
a.	ng new appname
b.	ng add @angular/pwa --project appname
2.	For an existing application –
a.	ng add @angular/pwa --project <name of project as in angular.json>
3.	The application scaffolded is almost identical to an application without PWA support. Let's see what this flag includes, in case you need to upgrade an application manually.
4.	We can see that the @angular/service-worker package was added to package.json. Also, there is a new flag serviceWorker set to true in the CLI configuration file angular.json.
5.	This flag will cause the production build to include a couple of extra files in the output dist folder:
•	The Angular Service Worker file ngsw-worker.js
•	The runtime configuration of the Angular Service Worker ngsw.json
Note that ngsw stands for Angular Service Worker.
6.	Serviceworker module provides a couple of injectable services:
•	SwUpdate for managing application version updates
•	SwPush for doing server Web Push notifications
	
7.	This module registers the Angular Service Worker in the browser (if Service Worker support is available), by loading the ngsw-worker.js script in the user's browser via a call to navigator.serviceWorker.register().
8.	The call to register() causes the ngsw-worker.js file to be loaded in a separate HTTP request. And with this in place, there is only one thing missing to turn our Angular application into a PWA.-> The build configuration file ngsw-config.json
9.	The CLI has also added a new configuration file called ngsw-config.json, which configures the Angular Service Worker runtime behavior, and the generated file comes with some intelligent defaults.
10.	Now, we will generate the production build -> ng build –prod
11.	After that, we will need a small web server. A great choice is http-server, so let's install it:
a.	npm install -g http-server
b.	cd dist
c.	http-server -c-1
12.	Go and check -  http://localhost:8080, 
13.	Now, ng serve -> Open ur app at – localhost:4200
				Your App is ready!! ( Add manifest.json using below link)
For other features Refer - https://blog.angular-university.io/angular-service-worker/ 

