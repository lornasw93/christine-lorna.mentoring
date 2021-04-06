# How-To
The aim of this document is to provide a guide on 'how to' do things whether it be creating a new project to installing packages, anything and everything.

## Creating a new Angular Project
`cd` into your chosen repo directory and create new project with both routing enabled and styling set.

```
cd C:\Users\lornn\source\repos\lornasw93\mentoring\christine
ng n project-name --routing=true --style=less
```

Next, to `cd` into app directory and add basic pages (new components). 
```
cd project-name/src/app
ng g c home
ng g c about
ng g c contact
```
Create a folder called `shared` - this is where the navbar and footer components will be created. 
```
mkdir shared
cd shared
ng g c navbar
ng g c footer
```
Ensure the components have been added into the `app.module.ts` file, they should've been automatically added but doesn't hurt to check.
```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppRoutingModule } from './app-routing.module';

import { AppComponent } from './app.component';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';
import { ContactComponent } from './contact/contact.component';
import { NavbarComponent } from './navbar/navbar.component';
import { FooterComponent } from './footer/footer.component';

@NgModule({
  declarations: [
    AppComponent,
    HomeComponent, //✨
    AboutComponent, //✨
    ContactComponent, //✨
    NavbarComponent, //✨
    FooterComponent //✨
  ],
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```
Let's now run the project. Enter the following command and wait for your browser to open (port 4200).
```
ng serve --o
```

![angular](https://user-images.githubusercontent.com/7913006/113355824-4087e980-9339-11eb-93a3-e08305eee1a7.PNG)

## Installing Bootstrap
Installing the 'bootsrap' package purely for it's css which we copy into the `angular.json` fil (see next step). `ng-bootstrap` for specific for Angular and doesn't require any JS. For more info [check here](https://ng-bootstrap.github.io/#/getting-started#installation).
```
npm i @ng-bootstrap/ng-bootstrap
npm i bootstrap
```

Add the following line in the `angular.json` file above the default styling file.
``` 
"styles": [
    "node_modules/bootstrap/dist/css/bootstrap.min.css", //✨
    "src/styles.less"
],
```

Install an additional package.
```
npm i @angular/localize
```

In the `polyfills.ts` add this line at the top.
```
import '@angular/localize/init';
```

Ensure the `NgbModule` is included in the `app.module.ts`. 
```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { NgbModule } from '@ng-bootstrap/ng-bootstrap';

import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';
import { ContactComponent } from './contact/contact.component';
import { NavbarComponent } from './shared/navbar/navbar.component';
import { FooterComponent } from './shared/footer/footer.component';

@NgModule({
  declarations: [
    AppComponent,
    HomeComponent,
    AboutComponent,
    ContactComponent,
    NavbarComponent,
    FooterComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    NgbModule //✨
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Run the project.
```
ng serve --o
```
