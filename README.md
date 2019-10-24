MyNgApp
This project was generated with Angular CLI version 8.3.9.

Development server
Run ng serve for a dev server. Navigate to http://localhost:4200/. The app will automatically reload if you change any of the source files.

Code scaffolding
Run ng generate component component-name to generate a new component. You can also use ng generate directive|pipe|service|class|guard|interface|enum|module.

Build
Run ng build to build the project. The build artifacts will be stored in the dist/ directory. Use the --prod flag for a production build.

Running unit tests
Run ng test to execute the unit tests via Karma.

Running end-to-end tests
Run ng e2e to execute the end-to-end tests via Protractor.

Further help
To get more help on the Angular CLI use ng help or go check out the Angular CLI README. #=============================================================================

for(var i=0;i<4;i++){.....} i++; console.log(i); // 5

The TypeScript Programming Language,

ES 6 based Language by Microsoft
Features
The scope declaration using 'let' keyword
for(let i=0;i<4;i++){.....} i++; console.log(i); // undefined
Data-Types
number, string, date, object, Array, boolean, any
syntax
let v:number =100; // explicit datatype declaration
let v=100; // v is typed to number, implicit datatype declaration
Array declaration
let arr:Array; // explicit Array Declaration
let arr=[]; // implicit array of 'any', late-binding
Both ar an instance of Array class
Properties
length
Methods
sort(), reverse(), filter(), reduce(), etc.
Template string
${<PLACE-HOLDER / VARIABLE>}
Older Concatination
var fname="fff"; var lname="dfdfd";
var fullName = fname + ' ' + lname;
ES 6 Template String
let fullName = Full NAme is ${fname} ${lname};
Template string is also known as 'String Interpolation' OR 'Expression'
Arrow Operator
=>
Used when Callfunction is used as parameter to a function
OLD Style
function x(function(a,b){.....});
Arrow Operator
x((a,b)=>{.......});
OOPs
Class
Access Specifier
public (default)
private, protected
Access Modifier
static
Parameterized Constructor
Constructor-Scopped parameters
Parameterized ctor having all parameters scoped only for that ctor
constrctor(x:number,y:number)
x and y will be used only in ctor
Private Parameters to ctor
constrctor(private x:number,private y:number)
x and y will be used only in ctor and inside class
Public Parameters to ctor
constrctor(public x:number,public y:number)
x and y will be used only in ctor and inside class also outside class
All members of class are accessed within class using 'this'. This is Mandatory
Inheritence
extends
derived class, if have ctor, then must used super() call to class base class ctor
Interface
Use 'implements' to implement interface
No Overloading No-Overriding
rest parameters
Varible number of parameters to a method
function x(...p:[]){.....}
... is known as 'spread' operator
Internally ... means
object.copy();
let a = object.copy(b);
a anb b are having same structure and value
a =...b
Union Type
Defining a variable with more than one datatype at a time
let x:number|string;
Modules
export
export : class, interface, method, const
import
All exports can be imported
The 'tsc' command, TypeScript Compiler
tsc .ts
Compile into .js
#============================================================================= Angular Core Concepts

STandard packages
@angular/core
NgModule
Angular Module
Component
Directive
Pipe
Injectable
Applied on Class to make it as Angular Service
Class will be Dependency Injected
HostListener
Decides which event is hosted by a method so that the method will be executed only when that hosted event is reaised
OnInit
Component Lifecycle Management Interface
Input
Accepting data from Other (parent) component or Directive
Output
Emits event from child component
EventEmitter
Emit an event
T is Event Args.
ViewChild
@angular/common
Provided CommonModule, used for createing reusable Angular Modules aka libraries aks Packages
Provides @angular/common/http
For Http Communication
@angular/compiler
Ahead-Of-Time (AOT) compilation
@angular/platform-browser
@angular/platform-browser-dynamic
@angular/animation
@angular/forms
Angular Forms
@angular/router
#============================================================================= ANgular Decorators

@NgModule --> Class with Angular Module
@Component
@Injectable --> Class will be service
@Input() --> Applied on Public member
@Output --> Applied on EventEmitter
@HostListener --> Applied on Method
@Pipe
@Dirctive
@ViewChild --> Applied on Component's instance to make it as child on other component.
=========================================================================
Angular Directives

Component Directive
Each Angular Component is Directive
Attribute Directive
Attribute of HTML DOM to set its behavior
E.g. ngModel
ngClass
Structural Directive
Dynamically add/remove HTML DOM
e.g.
*ngFor ==> for..of loop, new in ES 6
*ngFor="let of "
*ngIf ==> If Statement
*ngIf="condition"
*ngSwitch, *ngSwitchCase
#================================================================================================ To use ngModel for Two-Way binding, use FormsModule imported from @angular/forms

FormsModule
Two-Way Databinding
Form Types
Template Forms
Reactive Forms / Data-Driven Forms / Model-Driven Forms
Forms those are directly bound to the Model Object aka Entity
Managed using Model Properties
Implementation of Reactive Forms
Import ReactiveFormsModule in @NgModule from @angular/forms pacakge
Use FormGroup
Represents an instance of ngForm, and ngForm is by default maped with tag, and it will provide (ngSubmit) event
FormGroup will have all Editable Elements in it, this is known as 'FormControlCollection'
Each element in FormControlCollection is actually a 'FormControl' object
The FormControl is used to map the Public Property of the Model Class with the HTML Editable element in the form
FormControl('Name of the Property from Model Class', Validation Rules if any)
The 'formControlName' attribute provided by ReactiveFormsModule will actually bind the Model property with UI element.
The 'value' property of the FormGroup will represent the Value collection of Each FormControl bound with the Model class.
The Validators class with static validation methods
required(AbstractControl) -->Value must be mandatory in AbstractControl
requiredTrue() --> Value must be true
min()/max()
minlength()/maxlength()
pattern() --> regular Expression
email()
compose() --> method to apply validation rules on property and its corresponding element
==========================================================================
Communication Across Components

Component Related with Parent-Child Relationship
To accept data from Parent, the child must define a public property to accept data decorated with @Input() decorator
The Input Decorated property can now be used for Property-Binding
Child Component can emit data to parent using EventEmitter class. The T is the payload that is the data to be emitted. The EventEmitter object must be decorated using @Output() decorator. The parent must subscribe to the EventEmitter from child using EVENT-BINDING
The parent can tread the Payload from child using $event object
===========================================================================
Multi-Module Programming

Angular Application with 'Only-One' Application Module i.e. AppModule
SharedModules
Contains Reusable-Parts of the Application i.e. AppModule
Use SharedModule as a Library application (aka sub-application, that will contains Components, Services, Routing, Pipes, Directives, etc)
Generaly Library Module is used by AppModule using 'Lazy-Loading'
Angular Routing
@angular/router, the package
RouterModule
The infrastructure for Routing
Provide Router Table using 'Routes' object
Routes Object contains 'Route' object with following properties
path: Relative uri string, '' for default route
component: the name of the component
redirectTo: to set default when route expression does not match
children: [], array of Route
loadChildren: for Lazy Loading
Router class
Used for explicit routing using 'navigate()' method
navigate(['Route Expression URI'])
ActivatedRoute
Used for Parameterized Routing to read parameter from URL
ActivateRoute.subscribe((p)=> {p.})
[routerLink], the attribute directive for hyperlink.
This queries to RouteTable to navigate
e.g. [routerLink]="['']" ==> default
[routerLink]="['']"
[routerLink]="['/',]"
Parameterized Routing
The Component-Directive
USed for ibjecting the navigated component after routing is executed
RouterModule.forRoot(); --> register route table for root of the application, RouterModule.forChild(), register route table for lazy-loading
{path:,component:,loadchildren:'#'}
