- Open source JS library, allows to create dynamic and rich web applications
- It is built with the **Model-View-ViewModel** (MVVM) pattern 
- Implementing Knockout involves three distinct things
	- A View that contains HTML and CSS elements that get data bound to it
	- A ViewModel that contains the data to bind the view
	- Telling Knockout to perform the data binding to the view the ViewModel

### Data Binding Syntax
- Data binding is accomplished by adding an HTML attribute called `data-bind` to any HTML element that we want to replace with information from our ViewModel.
- Sometimes HTML tag does not work so Knockout allows to specify data bindings with HTML comments.
- eg: `<!-- ko -->`, `<!-- /ko -->`

## What is MVVM
- MVVM is based on MVC and the MV part is the same infact
- MVVM was designed to implement data binding between the ViewModel and View.

#### Creating a ViewModel
- A ViewModel can be any type of Javascript Variable

Basic View Model
```js
var myFirstViewModel = {
name: 'Mayank Sharma'
};
```
### Object Oriented ViewModels
```js
var mySecondViewModel = function(){
var self =this;
self.name = 'Mayank Sharma';
self.getName = function(){
	return self.name;
};
};
```
### ViewModels with Parameters
Most of the times the value in the ViewModel is cominng from an outside source like a database, the results of an AJAX call etc. 
```js
function viewModel(name){
var self = this;
self.name = name;
self.getName = function(){
return self.name
};
};

var myThirdModel = new ViewModel('Mayank Sharma');
```
