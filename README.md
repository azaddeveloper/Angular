
# What is Angular?
  Angular is an open-source web application development framework created by Google. It is used to build frontend, single-page applications that run on JavaScript. It is a full-
  fledged framework, i.e., it takes care of many aspects of frontend web applications such as HTTP requests, routing, layout, forms, reactivity, validation, etc.
# What is the difference between @ViewChild() and @ContentChild()
# How would you insert an embedded view from a prepared TemplateRef?
# Explain the difference between Constructor and ngOnInit
  The Constructor is a default method of the class that is executed when the class is instantiated and ensures proper initialization of fields in the class and its subclasses.
  ngOnInit is a life cycle hook called by Angular to indicate that Angular is done creating the component. We have to import OnInit in order to use like this (actually    
  implementing OnInit is not mandatory but considered good practice).
# What is AOT?
# What is difference between declarations, providers and import in NgModule?
  imports are used to import supporting modules like FormsModule, RouterModule, CommonModule, or any other custom-made feature module.
  
  declarations are used to declare components, directives, pipes that belong to the current module. Everyone inside declarations knows each other. 
  
  components or pipes are only matched against the HTML if they are declared or imported.

  Providers are used for injecting the services required by components, directives, pipes in the module.

# How to detect a route change in Angular?  
  class MyClass {
    constructor(private router: Router) {
        router.subscribe((val) => /*whatever*/ )
    }
  }
# What are the lifecycle hooks for components and directives?
  A component in Angular has a life-cycle, a number of different phases it goes through from birth to death. We can hook into those different phases to get some pretty fine 
  grained control of our application.

  constructor This is invoked when Angular creates a component or directive by calling new on the class.
  
  ngOnChanges Invoked every time there is a change in one of th input properties of the component.
  
  ngOnInit Invoked when given component has been initialized. This hook is only called once after the first ngOnChanges
  
  ngDoCheck Invoked when the change detector of the given component is invoked. It allows us to implement our own change detection algorithm for the given component.
  
  ngOnDestroy This method will be invoked just before Angular destroys the component. Use this hook to unsubscribe observables and detach event handlers to avoid memory leaks.
  These hooks are only called for components and not directives.

  ngAfterContentInit Invoked after Angular performs any content projection into the components view (see the previous lecture on Content Projection for more info).
  
  ngAfterContentChecked Invoked each time the content of the given component has been checked by the change detection mechanism of Angular.
  
  ngAfterViewInit Invoked when the component’s view has been fully initialized.
  
  ngAfterViewChecked Invoked each time the view of the given component has been checked by the change detection mechanism of Angular.

  ![lifecycle-hooks](https://user-images.githubusercontent.com/40568415/135086330-7161dd54-25ef-40e4-827c-3a95bd59b5f8.png)
# Why would you use lazy loading modules in Angular app?
  To load a feature module lazily we need to load it using loadChildren property in route configuration and that feature module must not be imported in application module. Lazy 
  loading is useful when the application size is growing. In lazy loading, feature module will be loaded on demand and hence application start will be faster.
# What do you mean by data binding?
  Data binding is among the most important and powerful features that help in establishing communication between DOM and the component. It makes the defining process of 
  interactive applications simple as you no longer need to panic about data pushing or pulling between the component and the template.
  Listed below are the four types of data binding in Angular:

  Event binding
  Property binding
  String interpolation
  Two-way data binding
# What do you mean by string interpolation?
  String interpolation in Angular, also known as the mustache syntax, only allows one-way data binding. It is a special syntax that makes use of double curly braces {{}} so that 
  it can display the component data.
# What are the differences between Angular decorator and annotation?
  In Angular, decorators are design patterns that help in the modification or decoration of the respective classes without making changes in the actual source code.
  Annotations, on the other hand, are used in Angular to build an annotation array. They use the Reflective Metadata library and are a metadata set of the given class.  
# What is DOM?
  The full form of DOM is Document Object Model, and it is responsible for representing the content of a web page and changes in the architecture of an application. Here, all 
  the objects are organized in the form of a tree, and the document can easily be modified, manipulated, and accessed only with the help of APIs.
# What are services in Angular?
  A service in Angular is a term that covers broad categories of functionalities. A service is any value, function, or feature that an app needs. A service is typically used to 
  accomplish a very narrow purpose such as HTTP communication, sending data to a cloud service, decoding some text, validating data, etc. A service does one thing and does it 
  well. It is different from a component as it is not concerned with HTML or any other kind of presentation logic. Normally, a component uses multiple services to accomplish 
  multiple tasks.
# What is a two-way data binding?
  Two-way data binding is done in Angular to ensure that the data model is automatically synchronized in the view. For example, when a user updates some data in a model and that 
  model is being displayed in multiple places in a component, that update should be reflected in all the places  
# What are pipes in Angular?
  When we are trying to output some dynamic data in our templates, we may sometimes need to manipulate or transform the data before it is put into our templates. Though there 
  are several ways of doing that, in Angular, using pipes is the most preferred way. A pipe is just a simple function, which we can use with expressions in our templates. 

  Pipes are extremely useful as we can use them throughout our application after declaring them just once and registering them with the Angular framework. Some of the most 
  common built-in pipes in Angular are UpperCasePipe, LowerCasePipe, CurrencyPipe, etc.  
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
# What is RxJS?
# What is the difference between an observable and a subject?
# How would you cache an observable data?

# What do you mean by dependency injection?
# What is server-side rendering in Angular?
# What is Angular Universal?
# What are HttpInterceptors in Angular?
# What is the difference between a component and a directive?
# How to create two way data binding in Angular?
  https://github.com/Yonet/Angular-Interview-Questions/blob/main/components.md
# What is the difference between a component and a directive?
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
  https://github.com/Yonet/Angular-Interview-Questions/blob/main/pipes.md
# What is the difference between RouterModule.forRoot() vs RouterModule.forChild()? Why is it important?
  https://github.com/Yonet/Angular-Interview-Questions/blob/main/router.md  
  
