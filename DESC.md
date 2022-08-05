### Descriptive Questions:
1. What is the difference between Hot Reload and Hot Restart?

| Hot Reload          | Hot Restart |
| ------           | ------ |
| Hot reload preserve state and update widget. Fastest way to apply changes.  | Hot restart destroy the preserve state and set it to default state. Whole code is compile again |
| faster | slower than hot reload |
| Hot reload loads code changes into the VM and re-builds the widget tree, preserving the app state. It doesn’t rerun main() or initState() | Hot restart loads code changes into the VM, and restarts the Flutter app, losing the app state |



2. What are the different ways we can create a custom widget?

Ans :       1. We can build our custome widgets by combining simpler widgets(predefine widget)
            2. We can also use customPainter to Draw widget.




3. How can I access platform(iOS or Android) specific code from Flutter?

Ans:  We can acces platform specific code using platform channels. We can use a Method channel , Event Channel 
