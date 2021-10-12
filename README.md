
# What is Angular?
  > Angular is an open-source web application development framework created by Google.It is  a development platform to build sophisticated and efficient single page applications.It takes care of many aspects of frontend web applications such as HTTP requests, routing, layout, forms, reactivity, validation, etc.
# What are the main building blocks of an Angular Application?
  **NgModule** : Angular application is a set of NgModules as angular supports modular programming.You can create a module class using @NgModule decorator with some 
  properties. Module can contain any components, service providers and other code for that module.
  You can create a module class using @NgModule decorator with some properties. Module can contain any components, service providers and other code for that module.
  ```
   @NgModule({
    imports: [],
    declarations: [],
    providers: [],
    bootstrap: [AppComponent],
  })
  export class AppModule { }
  ```
  **Components** - Components define and control the view , it's associated data and logic. 
  ```
  @Component({
      selector: 'web-portal-home',
      templateUrl: './home.component.html',
      styleUrls: ['./home.component.scss'],
  })
  export class HomeComponent {
  }
  ```
  **Services** - Services are used to share the data across the components. The decorator @Injectable() defines the class just below it as a service that can be injected 
  as  a dependency.
  ```
  @Injectable()
  export class UserService {
  }
  ```
  **Dependency Injection** - Dependency Injection is a design pattern that is used to resolve the dependencies in different classes or components. you can inject the service 
  in a component's constructor as below.
  ```
  constructor(private service: UserService) { }
  ```
  **Routing** - Angular provides a RouterModule to handle the navigation between the states and view of application.

# What is the host view in Angular?
  When a component is created it's directly associated with a single view that is called host view.

# What are the directives? How many types of directives are available in Angular?
  Directives provide the Program logic and extend the power of HTML by providing new syntax.
  Angular supports 3 types of directives as below.
  
  **Components** - These are the directives with templates.
 
 **Structure directives** - You can change DOM structure by adding or removing the elements. we use asterisk as a prefix to the directive name. Structure directive    
    examples are ngIf, ngFor etc.
 
 **Attribute directives** - When you want to change the appearance or behavior of a DOM element, you can use attribute directive. Attribute directive example.
   ```
   import { Directive, ElementRef } from '@angular/core';
      @Directive({
      selector: '[highlight]'
      })
      export class HighlightDirective {
          constructor(el: ElementRef) {
          el.nativeElement.style.backgroundColor = 'yellow';
      }
    }
    // directive usage
    <span highlight>High light content!</span>(*)
  ```
# What are the Services in Angular?
  In Angular services are the classes with well defined purpose. Services provide the functionality in a modular way which can be reused across the components. To share 
  the data between components you can use services. You can make your components efficient by delegating some functionality code to services like fetch the data from 
  server, validation rules etc. By defining this code into services you can make your code reusable to any component. You can create a service by using @Injectable 
  decorator.  
# How to make a service a singleton in Angular?
  - First way is - inject the service in root by setting 'providedIn' property to 'root' in @Injectable decorator.
  - Second way is - include the service in AppModule only or in a module that is imported only in AppModule no where else.
# What is the provider in Angular?
  In Angular, dependency injection is used to inject the dependencies of services, A Provider works as an instructor for dependency injection system to resolve the 
  dependencies. When you create any service it comes with a default @Injectable decorator that contains a default property 'providedIn' which creates the provider for 
  service.  
# Explain the dependency injection in Angular?
  Dependency Injection (DI) is a design pattern. Angular provides it's own dependency injection to Angular applications to increase their efficiency and modularity. 
  Dependency is an object or class that another class needs to complete its operations, for example A 'UserComponent' needs 'UserService' to perform user operations. 
  Angular DI framework injects the dependencies when it's instantiating the class or component.
  In angular it's mandatory to create the service with @Injecible decorator. To get injected the service by dependency injection you need to specify providers.  
   ```
    @Injectable({
      providedIn: 'root', // to inject the dependency in root
    })
    export class UserService {
    } 
    //In user component constructor you can inject the dependency like this
    constructor(userService: UserService){}
   ```
# What is RxJS library?
  RxJS (Reactive Extensions for JavaScript) is a library that uses the observable sequences for asynchronous and event-based or callback-based code. RxJS library has one 
  core type 'Observable' and satellite types including (Observer, Schedulers, Subjects).
  RxJS provides many operators to support the below features. 
# What is the HTTP interceptor?
  HTTP Interceptor intercepts and handles an HTTP request or response. You create your own interceptor by implementing the HttpInterceptor interface.  
  In case of multiple interceptors, the first interceptor transforms the request before passing it to next with 'next.handle(transformedReq)' method.
  To use the same instance of HttpInterceptor for the entire application, import HttpClientModule in your appModule and add the interceptor to the root application 
  injector. If you want to override this interceptor then specify another interceptor in the feature module.
# What is Transpiling in Angular?
  Transpiling is the one o the process to convert the typescript into javascript. We can do this by using Traceur, a JS compiler.
# What is the use of trackBy in ngFor?
  The trackBy function takes the index and the current item as arguments and needs to return the unique identifier for this item. Now when you change the collection, Angular can   track which items have been added or removed according to the unique identifier and create or destroy only the items that changed.
# Why we use async pipe with ngFor?   
  The async pipe gives the latest value from an observable. In this case (as in other cases) it will refresh the data involved when a new value comes down the observable. So if   the screen renders and the observable updates the ngFor will re-render.
# What is the difference between @ViewChild() and @ContentChild()
  As the name suggests, @ContentChild and @ContentChildren queries will return directives existing inside the <ng-content></ng-content> element of your view, 
  whereas @ViewChild and @ViewChildren only look at elements that are on your view template directly.
# How would you insert an embedded view from a prepared TemplateRef?
  we can create an embedded view using createEmbeddedView method then attach that view to the DOM via ViewContainerRef:
# Explain the difference between Constructor and ngOnInit
  - Constructor is a default method of the class that is executed when the class is instantiated and ensures proper initialization of fields in the class and its 
  subclasses.
  - ngOnInit is a life cycle hook called by Angular to indicate that Angular is done creating the component. We have to import OnInit in order to use like this (actually    
  implementing OnInit is not mandatory but considered good practice).
# Explain the AOT compilation? Or What is the difference between JIT and AOT?
  - **JIT - Just-in-Time (JIT)**, it compiles the application at runtime in the browser. JIT is the default compiler in angular. When you run ng-build or ng-server it will 
  compile your application.
  - **AOT - Ahead-of-Time (AOT)**, it compiles the application at build time. AOT compiler converts all HTML and TypeScript code into JavaScript code during build before 
  browsers start downloading JavaScript code. It makes rendering faster.
# What is difference between declarations, providers and import in NgModule?
  **imports** are used to import supporting modules like FormsModule, RouterModule, CommonModule, or any other custom-made feature module.
  
  **declarations** are used to declare components, directives, pipes that belong to the current module. Everyone inside declarations knows each other. 
  
  **components** or pipes are only matched against the HTML if they are declared or imported.

  **Providers** are used for injecting the services required by components, directives, pipes in the module.

# How to detect a route change in Angular?  
  ```
  class MyClass {
    constructor(private router: Router) {
        router.subscribe((val) => /*whatever*/ )
    }
  }
 ``` 
# What are the lifecycle hooks for components and directives?
  A component in Angular has a life-cycle, a number of different phases it goes through from birth to death. We can hook into those different phases to get some pretty
  fine 
  grained control of our application.

  - constructor This is invoked when Angular creates a component or directive by calling new on the class.
  
  - ngOnChanges Invoked every time there is a change in one of th input properties of the component.
  
  - ngOnInit Invoked when given component has been initialized. This hook is only called once after the first ngOnChanges
  
  - ngDoCheck Invoked when the change detector of the given component is invoked. It allows us to implement our own change detection algorithm for the given component.
  
  - ngOnDestroy This method will be invoked just before Angular destroys the component. Use this hook to unsubscribe observables and detach event handlers to avoid memory 
  leaks.
  These hooks are only called for components and not directives.

  - ngAfterContentInit Invoked after Angular performs any content projection into the components view (see the previous lecture on Content Projection for more info).
  
  - ngAfterContentChecked Invoked each time the content of the given component has been checked by the change detection mechanism of Angular.
  
  - ngAfterViewInit Invoked when the component’s view has been fully initialized.
  
  - ngAfterViewChecked Invoked each time the view of the given component has been checked by the change detection mechanism of Angular.

  ![lifecycle-hooks](https://user-images.githubusercontent.com/40568415/135086330-7161dd54-25ef-40e4-827c-3a95bd59b5f8.png)
# Why would you use lazy loading modules in Angular app?
  Lazy Loading is the technique of loading the module or data on demand. It helps us to better the application performance and reduce the initial bundle size of our 
  files. The initial page loads faster and we can also split the application into the logic chunks which can be loaded on demand.
# What do you mean by data binding?
  Data binding is among the most important and powerful features that help in establishing communication between DOM and the component. It makes the defining process of 
  interactive applications simple as you no longer need to panic about data pushing or pulling between the component and the template.
  Listed below are the four types of data binding in Angular:

  - Event binding,
  - Property binding,
  - String interpolation,
  - Two-way data binding
# What do you mean by string interpolation?
  String interpolation in Angular, also known as the mustache syntax, only allows one-way data binding. It is a special syntax that makes use of double curly braces {{}} 
  so that it can display the component data.
# What are the differences between Angular decorator and annotation?
  Traceur gives us annotations. TypeScript gives us decorators. But Angular 2 supports both.

  Annotations create an "annotations" array. whereas Decorators are functions that receive the decorated object and can make any changes to it they like.

  As angular use TypeScript instead of atScript so it is using decorators. There are basically four kind of decorators are there which are

  Class decorators, e.g. @Component and @NgModule
  
  Property decorators for properties inside classes, e.g. @Input and @Output
  
  Method decorators for methods inside classes, e.g. @HostListener
  
  Parameter decorators for parameters inside class constructors, e.g. @Inject  
# What is DOM?
  The full form of DOM is Document Object Model, and it is responsible for representing the content of a web page and changes in the architecture of an application. Here, all 
  the objects are organized in the form of a tree, and the document can easily be modified, manipulated, and accessed only with the help of APIs.

# What is a two-way data binding?
  Two-way data binding is done in Angular to ensure that the data model is automatically synchronized in the view. For example, when a user updates some data in a model and that 
  model is being displayed in multiple places in a component, that update should be reflected in all the places .
# How to create two way data binding in Angular?
  https://github.com/Yonet/Angular-Interview-Questions/blob/main/components.md  
# What are pipes in Angular?
  A Pipe provides the functionality of transforming the data from your data input to desired output. For example, You receive some lower case data from the back end and 
  now you want to display that data as upper case then you can Angular built in pipe 'uppercase'. You can also create your custom pipes in angular.
  To implement a custom pipe, decorate your class with '@Pipe' metadata and implement PipeTransform interface's transform method as below.
  @Pipe({name: 'exponentialStrength'})
  export class ExponentialPipe implements PipeTransform {
    transform(value: number, exponent?: number): number {
      return Math.pow(value, isNaN(exponent) ? 1 : exponent);
    }
  }
# What are observables in Angular?
  An observable is a declarative way using which we can perform asynchronous tasks. Observables can be thought of as streams of data flowing from a publisher to a subscriber. 
  They are similar to promises as they both deal with handling asynchronous requests. # However, observables are considered to be a better alternative to promises as the former 
  comes with a lot of operators that allow developers to better deal with asynchronous requests, especially if there is more than one request at a time.
# How are observables different from promises?
  Although both promises and observables are used to handle asynchronous requests in JavaScript, they work in very different ways. Promises can only handle a single event at a 
  time, while observables can handle a sequence of asynchronous events over a period of time. Observables also provide us with a wide variety of operators that allow us to 
  transform data flowing through these observables with ease. 

  A promise is just a way to wrap asynchronous operations so that they can be easily used, while an observable is a way to turn asynchronous operations into a stream of data 
  that flows from a publisher to a subscriber through a well-defined path with multiple operations transforming the data along the way.

# What is the difference between an observable and a subject?
  While plain Observables are unicast (each subscribed Observer owns an independent execution of the Observable), Subjects are multicast. A Subject is like an Observable, but 
  can multicast to many Observers. Subjects are like EventEmitters: they maintain a registry of many listeners.
# What is the difference between a component and a directive?
  Component is used to break up the application into smaller components. But Directive is used to design re-usable components, which is more behavior-oriented. That is why   
  components are widely used in later versions of Angular to make things easy and build a total component-based model.
  There are three kinds of directives in Angular:

  components - directive with a template
  structural directives - changes DOM layout by adding and removing elements i.e. *ngFor
  attribute directives - changes appearance or behaviour of an element, component or another directive (ngStyle for example)
  so precisely:

  component uses @Component decorator, directive uses @Directive decorator
  component has template, directive has not  
# Forms Questions:
# When do you use template driven vs model driven forms? Why?
# How do you submit a form?
# What's the difference between NgForm, FormGroup, and FormControl? # How do they work together?
# What's the advantage of using FormBuilder?
# How do you add form validation to a form built with FormBuilder?
# What's the difference between dirty, touched, and pristine on a form element?
# How can you access validation errors in the template to display error messages?
# What is async validation and # how is it done?
# What is the correct form control class name which is set to true when value is modified?
# What is the difference between a module's forRoot() and forChild() methods and why do you need it?
# What is a pure pipe?
# What is server-side rendering in Angular?
# What is Angular Universal?
  https://github.com/Yonet/Angular-Interview-Questions/blob/main/pipes.md
# What is the difference between RouterModule.forRoot() vs RouterModule.forChild()? Why is it important?
  https://github.com/Yonet/Angular-Interview-Questions/blob/main/router.md  
  
