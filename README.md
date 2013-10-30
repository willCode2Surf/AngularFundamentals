#Angular - Introduction

Before beginning the code portion it is important to visit the AngularJs website.  Below are a couple key links to get to the download and resources you will reference will using Angular to develop applications.

###Angular Library Download
<http://angularjs.org>  

On the AngularJs website there will be an option to download the library or visit the Github repo.  The Github repo would require us to build the library so at this stage of the introduction we will just want to download it.

###Angular Developer Guide
<http://docs.angularjs.org/guide/>

This is a key resource to any Angular developer.  The guide has various topics that users can select, research, and discuss.

###Angular API Reference
<http://docs.angularjs.org/api/>

Developers should be aware of where the API is for any technology they are using to create applications.  This is the detailed scaffolding overview and information of the entire Angular stack and will be a goto reference.

#What is Angular

Angular is an open source project written in JavaScript that is maintained by Google and has over 100 unique contributors.  By most references Angular is often described as an MVC framework but the Angular team calls it an MV* framework.

What is the star for?  It simply means that frameworks adopting the MV* approach represent Model / View / [Controller / Presenter / View Model] philosophy.  Angular actually uses a Controller.

Angular is similiar to some familiar other familiar frameworks in the open source community and will often be categorized in the likes of BackboneJs, KnockoutJs, and EmberJs among others.

>Angular Is Opinionated and allows Vision
>>Angular is proud to opinionated but what does that actually mean to developers?
>>>The term opinionated means that the framework will *guide* developers *NOT enforce* them.  This means that there can be many different ways to accomplish something (such as manipulate the DOM) in Angular but the framwork **recommends** one way to accomplish something.

>>>This vision is *broad* and can cause confusion on larger teams because simple work is left to the developer.  This lack of idiomatic structure can become a maintainence issue if not addressed early on and **rigid** coding standards are enforced.

#Angular Features
>Angular will offer many features and what makes Angular special will vary from developer to developer so here is a quick list of the highlights Angular offers.

>>* handles Ajax calls for developers
* data stored in Plain Old JavaScript Object (POJO)
* handles page display
* two-way binding
* routing
* testable (unit and end to end testing with Karma)
* extends the HTML vocabulary through directives
* futuristic and forward thinking (web components, Object.observe)

#Angular Architecture
>Angular is built on a few key concepts that should be understood as the keys to Angular's architecture.

>>* two-way binding
* dirty checking; model data can respond to changes in POJOs
* dependency injection; Angular is built on this concept

#Angular Components

>Controllers
>>controllers are the central player and contain logic/state info
>Views
>>views are where bindings and directives live
>>>this is where Angular communicates with the end user
>Services
>>services encapsulate the complex business logic of the app, manage state, and handle server communication.

#Hello Angular World
The first dive into Angular will be very simple but allow us a chance to look at the key components and architecture discussed.  We are going to walk through the different portions of the `index.html` file.

>*Step 1: The basic html shell* 
```
<!DOCTYPE html>
<html lang="en" ng-app>
    <head>
    	<meta charset="UTF-8">
		<title>Hello Angular World</title>
	</head>
    <body>
	</body>
</html>
```
>Everything looks pretty standard here with the exception of the `ng-app` attribute inside the `html` tag.  This is part of every Angular application.

>*Step 2: Adding an Angular expression*
>The expressionis contains a placeholder that will display our hello message.  We will put this expression inside of an `<h1>` tag inside the body.  
```
    <body>
      <h1>{{helloAngularMessageHolder}}</h1>
	</body>	
```

>*Step 3:  Adding Angular*
>The expression above will not serve us much purpose nor will any other ng (Abbreviation for Angular) tags until we make the framework available.  As with JavaScript best practices we will do this towards or at the end of the body tag.
```
	<script src="angular.min.js"></script>
	</body>
```
>*Step 4:  Adding the Controller*
>So that we can modify the placeholder in our expression we will create a quick Angular Controller with another `<script>` tag.  You will notice that in the Controller we are passing a `$scope` parameter.   
>>This special parameter is used to move data between the controller and the view.  We can assign properties to the $scope variable and they are availble in the view.
>Notice that the name of the function is the controller name.  This block of code is placed after the Angular library is included.
```
		<script type="text/javascript">
			function HelloAngularWorldCtrl($scope){
				$scope.helloAngularMessageHolder = "Hello Angular World!";
			}
		</script>
```
>*Step 5:  Wiring up the Controller*
>In order for the expression and the $scope to work in conjunction we need to assign an `ng-controller` attribute on the tag that holds the expression.  We will set the value of the attribute to be the Controller name that it is working with.  
```
		<h1 ng-controller="HelloAngularWorldCtrl">{{helloAngularMessageHolder}}</h1>
```

>*Summary*
>The `index.html` page will now run and should look as follows:
```

<!DOCTYPE html>
<html lang="en" ng-app>
	<head>
		<meta charset="UTF-8">
		<title>Hello Angular World</title>
	</head>
	<body>
		<h1 ng-controller="HelloAngularWorldCtrl">{{helloAngularMessageHolder}}</h1>
		<script src="angular.min.js"></script>
		<script type="text/javascript">
			function HelloAngularWorldCtrl($scope){
				$scope.helloAngularMessageHolder = "Hello Angular World!";
			}
		</script>
	</body>
</html>

```