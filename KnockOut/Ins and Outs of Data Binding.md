### Binding HTML Data
HTML Bindings work similarly to text with the exception that they render any HTML tags provided. If we use text binding the HTML content would be escaped and content will be displayed as text.

```js
<!DOCTYPE html>
<html>
<head>
 <title>Data Binding with KnockoutJS</title>
</head>
<body>
 <h1 data-bind="html: getName()"></h1>
<script type='text/javascript' src='js/knockout-3.2.0.js'></script>
 <script>
 function ViewModel() {
 var self = this;
 self.name = 'Mayank Sharma';
 self.getName = function() {
 return 'Hello <em>' + self.name + '</em>!';
 };
 };
 var viewModel = new ViewModel();
 ko.applyBindings(viewModel);
 </script>
</body>
</html>
```
### Binding HTML Attributes, CSS Classes and CSS Styles 
Example:
```js
<p data-bind="style: {marginBottom: 0, paddingBottom: '1em'}, css: 'myClass'">This text has custom styles and a CSS class</p>
```
Similaly to add a custom HTML attribute:
```js
<p data-bind="attr: {id: 'myCustId'}">This p tag has an id data bound to it' }.</p>
```
### Condition-Based Data Binding
Placing conditional statements inside our data binding.
Example:
The text data binding contains condtional statement to print "Create" or "Update" inside the button depending upon whether the id is 0 or 1
```js
<button type="submit" data-bind="text: (id == 0) ? 'Create' : 'Update'"></button>
<script>
	var viewModel = function(){
		var self = this;
		self.id = 0;
	};
	ko.applyBindings(viewModel);
</script>
```
Same thing can be done using a function inside the data bind:
```js
<button type="submit" data-bind="text: (isNew()) ? 'Create' : 'Update'"></button>
<script>
	var viewModel = function(){
		var self = this;
		self.id = 0;
		self.isNew = function(){
			return id == 0;
		};
	};
	ko.applyBindings(viewModel);
</script>
```
