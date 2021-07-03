When we are accessing the properties to the data bind everything is relative to the context we are in.

The root context is the ViewModel that is supplied to the `ko.applyBindings`.

Knockout offers several useful variables to allow us to navigate between diffent parent/child contexts
- `$root`: accesses the root context (ViewModel bound to the Knockout) in any child context.
- `$parent`: accesses the current context's direct parent.
- `$parents`: contains an array of parent contexts to the context we are currently in. `$parents[0]` is the same as `$parent` and `$parents[$parent.length - 1]` is the same as `$root`.
- `$data`: Provides access to the current object our context is in.
- `$index`: only availabl within the foreach binding, contains an integer that represents the current postition of the loop starting at 0 and going to length - 1.

### foreach Binding


