Intro
#### Components
@Component() decorator

Before a view is displayed,
Angular evaluates the directives and resolves the binding syntax

Templates
directives
data binding
pipes

services and dependency injection
@Injectable()

#### Modules
**\*.module.ts**
```
import { NgModule }      from '@angular/core';  
import { BrowserModule } from '@angular/platform-browser';  

@NgModule({  
  //modules whose exported classes are needed by component templates   of in this NgModule.  
  imports:      [ BrowserModule ],  
  //Creators of services that this NgModule contributes to the global collection of services;  
  providers:    [ Logger ],  
  //components, directives, and pipes of this
  declarations: [ AppComponent ],  
  //declarations for component templates of other NgModules.  
  exports:      [ AppComponent ],  
  //for the main app module  
  bootstrap:    [ AppComponent ]  
})  
export class AppModule { }
```
The components that belong to an NgModule share a compilation context.
A component and its template together define a view.
Component, it's associated directly with a single view, called the host view.
view in the hierarchy could belong to other modules

**\*.component.ts**

A component controls a patch of screen called a view.
It contains the application logic

```
@Component({
  selector:    'app-hero-list',
  templateUrl: './hero-list.component.html',
  providers:  [ HeroService ]
})
export class HeroListComponent implements OnInit {  
  heroes: Hero[];  
  selectedHero: Hero;  

  constructor(private service: HeroService) { }  

  ngOnInit() {  
    this.heroes = this.service.getHeroes();  
  }  

  selectHero(hero: Hero) { this.selectedHero = hero; }  
}  
```

the **@Component** decorator identifies the class immediately below it as a component class, and specifies its metadata.

**selector** css selector, if found in html of all app this view will be inserted `es: <app-hero-list></app-hero-list>`  
**templateUrl** position of the html template of the component's host view  
**providers** An array of providers for services that the component requires.

**Template syntax**  
html + Angular template syntax (it alters the HTML based on your app's logic and the state of app and DOM data)

##### DOM->Component  
**{{value}}**  <- interpolation  es:hero.name property of the component  
**[property] = 'value'** <- property binding  
**(event) = 'handler'** -> event binding  es:(click)="selectHero(hero)" (method)
**[(ngComponent)] = 'property'** <-> Two-way data binding combines event and property binding set the html parameter and the component parameter

`<app-hero-detail [hero]="selectedHero"></app-hero-detail>`  
passes the value of selectedHero from the parent HeroListComponent to the hero property of the child HeroDetailComponent.


#### Pipes

a class decorated by  @Pipe
define a function that transforms input values to output values for display in a view.
api from angular are available
use them in html:
`<p>The date is {{today | date:'fullDate'}}</p>`

#### Directives

A directive is a class with a @Directive() decorator.  
**Structural directive**  
`<li *ngFor="let hero of heroes"></li>`  
**\*ngFor** is an iterative; it tells Angular to stamp out one **\<li\>**  per hero in the heroes list.  
`<app-hero-detail *ngIf="selectedHero"></app-hero-detail>`  
**\*ngIf** is a conditional (if a selected hero exists.)  

**attribute directive**
