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

>*Step 2: Adding an Angular expression with a 