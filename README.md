# QrcodeGenerator

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.5.6.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `-prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

### TUTORIAL: Create a QR Code Generator with Angular 4+

#### Author: Techiediaries
#### Website: https://www.techiediaries.com/generate-qrcodes-angular/

Throughout this tutorial we are going to create a QR Code generator web application with Angular 4+ so lets get started .
You can also read the second part How To Read QR Codes In Angular ?

First, lets start by creating an Angular 4 project using the Angular CLI.

Open your terminal or command prompt ,depending on your operating system ,then generate a new Angular 4 application by running :

```bash
ng new qrcode-generator 
```

_Project 'qrcode-generator' successfully created._

After the command completion ,proceed by installing ngx-qrcode2 from npm ,which is an Angular 4+ component library
to generate QR Codes .

```bash
cd qrcode-generator
npm install ngx-qrcode2 --save 
```

Open your project with your favorite code editor .I'm using Visual Studio Code which has a nice TypeScript support .

```bash
code .
```

Head over to _src/app/app.module.ts_ .

Then import NgxQRCodeModule from ngx-qrcode2 and add it to the list of module imports .

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';
import { NgxQRCodeModule } from 'ngx-qrcode2';

@NgModule({
declarations: [
    AppComponent
],
imports: [
    BrowserModule,
    NgxQRCodeModule
],
providers: [],
bootstrap: [AppComponent]
})
export class AppModule { }        
```

Once this is done you can use ngx-qrcode component to generate QR Codes .

Head over to _src/app/app.component.html_ and add :

```xml
<ngx-qrcode [qrc-element-type]="elementType" [qrc-value] = "value">
</ngx-qrcode>
```

Now you should add two variables value and elementType to your app component with some default values .

Head over to _src/app/app.component.ts_ .

```typescript
import { Component } from '@angular/core';

@Component({
selector: 'app-root',
templateUrl: './app.component.html',
styleUrls: ['./app.component.css']
})
export class AppComponent {
elementType : 'url' | 'canvas' | 'img' = 'url';
value : string = 'Techiediaries';
}
```

value is of type string .

elementType can take either url ,canvas or img .

That's it ,you can now run

```bash
ng serve 
```

_To serve your app ,then visit http://localhost:4200/_ .

You should see a QR Code generated and rendered for the value "Techiediaries" .

**Conclusion**
We have created an Angular 4 application which makes use of ngx-qrcode2 component library to generate QR Codes .This is just a basic example demo but you can further develop it by binding the value variable to some textarea and add more features .
