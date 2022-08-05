## Descriptive Questions:
#### What is the difference between Hot Reload and Hot Restart?

| Hot Reload          | Hot Restart |
| ------           | ------ |
| Hot reload preserve state and update widget. Fastest way to apply changes.  | Hot restart destroy the preserve state and set it to default state. Whole code is compile again |
| faster | slower than hot reload |
| Hot reload loads code changes into the VM and re-builds the widget tree, preserving the app state. It doesn’t rerun main() or initState() | Hot restart loads code changes into the VM, and restarts the Flutter app, losing the app state |



#### What are the different ways we can create a custom widget?
 	- We can build our custome widgets by combining simpler widgets(predefine widget)
	- We can also use customPainter to Draw widget.


#### How can I access platform(iOS or Android) specific code from Flutter?               
	 - We can access platform specific code using platform channels. We can use 	a Method channel , Event Channel to get data from native .

Method Channel : In this we invoke a method from your Flutter app to the native code, the native code does something and finally responds with a success or error. This call could be to get the current battery status, network information or temperature data. Once the native side has responded, it can no longer send more information until the next call.

Event Channel:  Event Channel is used to _stream_ data. This results in having a stream on the _Dart_ side of things and being able to feed that stream from the native side.
This is useful if you want to send data every time a particular _event_ occurs, e.g. when the wifi connection of a device changes.


#### What do you know about eventloop and what is the relationship with isolates?

Event Loop : An event loop’s job is to take an item from the event queue and handle it, repeating these two steps for as long as the queue has items.
The items in the queue might represent user input, file I/O notifications, timers, and more.

Isolates :  Isolate is like a little space in a machine, with its memory  _(a system that stores information that will be needed soon on a short-term basis)_  and a single thread running an event loop that processes the code.

Each isolate will contain its own memory and event loops.
