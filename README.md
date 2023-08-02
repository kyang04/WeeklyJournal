# WeeklyJournal
This project was made during the Northeastern University 2023 Summer 1 semester for CS 3500 Object-Oriented Design. It is a weekly planner to keep track of events and tasks.
Preview of the Journal:
[weekview.jpg](https://github.com/kyang04/WeeklyJournal/blob/fecf46f1138b9e2c5b4dea7c820e518008f8e15c/weekview.jpg)

### Contributors
Partnered with Rup Jaisinghani
https://github.com/rupjaisinghani0904

### Features
This Bullet Journal application supports a multitude of features 
to help users keep track of events and tasks during the week 
- a view of the week, with tasks and events displayed for each day
- buttons + shortcuts to add events and tasks
- ability to save and open weeks, in files with the extension (.bujo)
- set a max number of tasks and events per day
- a sidebar that seamlessly appears on the screen to show all tasks
- a menubar that contains all commands a user may wish to use to customize their week with intuitive keyboard shortcuts
- an area to write quotes of the user's choice
- the ability to delete and edit tasks and events 
- a dialog which shows total tasks + events and task completion %
- the ability to determine which day the week starts on


How this application was designed with SOLID in mind:
- Single-Responsibility: We followed single responsibility in each class
we designed by ensuring they only carry out a single task. Our controller class takes
care of updating the view and model depending on user input, our view classes only take care of 
the visuals, and our model classes are about handling data and storing it, as well as sending it to the view
- Open/Closed Principle: We made use of interfaces in each of our packages to ensure classes are able
to extend the necessary functionality but are also prevented from potentially adding unexpected bugs
from modifying the classes directly. For example, we used EventEntry and TaskEntry interfaces which
both extend JournalEntry, to ensure that our classes will not lose the methods from journal-entry, but are still
able to add methods to their classes through their separate interfaces
- Liskov Substitution: We used Liskov substitution with our JournalEntry class, specifically
in the deleteEntry method, where if we were to replace a journal entry with an event or task entry
it would not cause our program to break. In summary, a journal entry could be replaced with either of its 
subtypes
- Interface Segregation: This was done, as stated before in our journal entry interface, get extended by two
other interfaces, so that task-specific methods are only available to the task, and the same for the event
- Dependency Inversion: We used dependency inversion in our event and task entry classes, by using the dependency injection pattern
to facilitate decoupling. This was also done in the bujo writer and reader classes. Our many abstractions also
allow for less dependency on specific implementations and allow for more flexibility 

