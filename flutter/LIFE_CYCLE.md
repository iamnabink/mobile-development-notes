`createState()`: This is the first method that’s called when a stateful widget is inserted into the widget tree. It creates an instance of the State class associated with the widget.
`mounted`: It is a bool value, that turns true when the buildContext is assigned to the widget.
`initState()`: It is a method that is called just before the widget gets built. This is where you can initialize data or perform setup operations. It runs only once during the widget’s lifecycle.
`didChangeDependencies()`: It is called just after the initState() method and it can be called multiple times. This method is more suitable when changes to inherited widgets (like InheritedWidget) affect the current widget, not for normal property changes.
`build()`: The build method is responsible for returning the widget's user interface. This method rebuilds when setState is called.
`didUpdateWidget()`: If the parent widget changes and triggers a rebuild of the stateful widget, the didUpdateWidget method is called.This method is called when the widget's configuration (e.g., properties) changes. In this case, when the error changes, didUpdateWidget is triggered, allowing you to perform actions or trigger a rebuild if necessary.
`setState()`: This method is used to signal that the widget’s internal state has changed and that a rebuild is needed. When setState is called, it schedules a call to the build method and marks the widget as needing to be rebuilt.
`deactivate()`: It is called when the widget is popped but it might be reinserted before the current frame change is finished.
`dispose()`: This method is called when the widget is removed permanently from the widget tree.
