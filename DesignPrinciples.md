# Design-Patterns

Creational Patterns
  - [Abstract Factory](#abstract-factory)
  - [Builder](#builder)
  - [Factory Method](#factory-method)
  - [Prototype](#prototype)
  - [Singleton](#singleton)

Structural Patterns
  - [Adapter](#adapter)
  - [Bridge](#bridge)
  - [Composite](#composite)
  - [Decorator](#decorator)
  - [Facade](#facade)
  - [Flyweight](#flyweight)
  - [Proxy](#proxy)

Behavioral Patterns
  - [Chain of Responsibility](#chain-of-responsibility)
  - [Command](#command)
  - [Interpreter](#interpreter)
  - [Iterator](#iterator)
  - [Mediator](#mediator)
  - [Memento](#memento)
  - [Observer](#observer)
  - [State](#state)
  - [Strategy](#strategy)
  - [Template method](#template-method)
  - [Visitor](#visitor)

## Creational Patterns

### Abstract Factory
 - You are designing a framework for creating widgets for both computers and mobile devices. Depending upon the type of the device, appropriate widgets for the underlying platform should be initialized.
 - A car manufacturer wants to build automobiles in Japan, Germany, and California. It makes sedans, minivans, and SUVs. Each one of these needs to be
constructed differently in different locations: righthand drive vs. lefthand rive, and for different mileage, emissions, and safety regulations. These differences lead to several variations in the production process, which are more cleanly handled by encapsulating the creation methods than by checking parameters at many points in the code.

### Builder
 - **A creational pattern that can be used to avoid confusingly long parameter lists.**
 - Suppose we have code that is supposed to construct a Car object for use in a simulation.  It has several different constructors:
Car(Make make) { ... }        
Car(Make make, Model model) { ... }    
Car(Make make, Model model, Engine engine) { ... }    
Car(Make make, Model model, Engine engine, Color color) { ... }
... and so forth, so that the longest constructor has a parameter for each option.
What pattern can we use to simplify this construction?  (Note that all the objects being constructed are elements of the same class.)
  - Your program is drawing a line chart. To draw the chart, it needs to know the min and max values along each access, the axis scale and the axis labels, the resolution of the grid (if any), as well as the color, weight, and type (e.g., solid, dashed, or dotted) of each line on the graph. Not to mention the points on each line. What would be a good design pattern for drawing the chart?
  - Suppose that a billing system has a Customer object, which can contain (i) an Invoices collection that holds information on everything the customer has purchased, (ii) a set of Address objects that represents the various kinds of addresses a customer might have (shipping, billing, etc.), and PaymentMethods object, containing information on credit cards, purchase orders, and other accounts that the customer has used for paying bills. A Customer object will not be usable without any of these components. But few methods that create Customers will need to create all of these component objects. What pattern is cleanest for creating the billing objects?


### Factory Method
 - Remember our example of how to represent money. We saw that different currencies had different symbols, and different numbers of digits to the right of the decimal point. We would like to write code that will work for any currency. When it needs a new instance of that currency, the code will call a creational method of an abstract class, which at run time will create instances of the currency that this invocation of the program is using.
 - Your 3D printer will be fabricating a dozen different kinds of devices. You want to set up the code so that a device will be constructed when your program calls a single method, and passes a single parameter, which identifies the type of device to be constructed.


### Prototype
 - Consider the case where an architect is creating the layout of a home. Since objects such as walls, doors, windows, which may be of different sizes & configurations, are common to different parts of the home, the architect can reuse the same objects. What type of pattern could be used to create the layout with the reuse of existing objects?
 - I have a superhero object. Creation of this object is very cumbersome. Some superheroes are well known and some are sidekicks. A dictionary contains a collection of all superheroes. A clone method has been added to my Superhero class. Which pattern is in use?
 - When a new player joins the game, instead of creating a new playable character, the game engine copies a random character from one of the existing players already in the game and then applies the new player's customizations (eg. skins, weapons) on it.
 - A simple game, in the style of Where s Waldo, requires creating many figures on a screen, most of which are identical, or of very few types, in an effort to make it more difficult to find the three soughtafter instances, which really are different from the others.
 - Suppose that you have a drawing program, and want to make it easy to draw pictures containing various animals. So you, as the programmer, draw an example of each animal (dog, cat, elephant, aardvark, etc.), each of which is made up of various body parts arranged in a particular way. Then you let users copy these animals, and after that, customize them in any way that they want, so that no two animals need be exactly alike.


### Singleton
 - **A design pattern that requires making the constructor private.**
 - A common way of organizing parallel programs is to use a thread pool: a certain number of threads are created to perform tasks, and when a thread finishes one task, it takes a new task from the queue. There is only one such pool, created at startup. So when more work comes along, a new thread is not created; rather, the work just sits in the queue till an existing thread can get to it.
 - You are working on a refactoring project. You intend to rename some of the methods so the names are reflective of what they do. Now to do this, you would do a "ctrlF" to find all occurrences of the method, so you can replace them with the new name you intend for the method. The dialog box for find comes up only if a dialogue box is not already open.



## Structural Patterns


### Adapter
 - You want to use a method that someone else has written because it performs some function that you need. You can't incorporate the routine directly into your program, and the interface is not compatible with your program.
 - Suppose we have a Deque (double-ended queue) class and want to use an instance as a Stack, sending its objects push and pop messages. We can define another class that calls the Deque object. This class is an example of
 - In our system, the mobile site is different from the desktop site. However, some users wish to see the desktop site on their mobile devices. When such a request is made, we handle the request and show the user the desktop site. What pattern are we using here.


### Bridge
 - **A pattern that helps detach interface from implementation.**
 - Different operating systems use different frameworks to implement their graphical user interface. But, many applications run on the various operating systems. Windows and other widgets need to be displayed in essentially the same way on each operating system, regardless of what application is displaying them.
 - I would like any application on my system to be able to read or write data to local files, to network drives, or to cloud storage. What pattern can I use so that I don t have to rewrite the code that reads and writes data separately for each application?


### Composite
 - **A pattern that helps to break down a problem into manageable chunks by sending the same message to an object and to its components.**
 - In Java Server Faces, there is a UIPanel that is a UIComponent, and hence any UIComponent can be added to any other UIComponent. Which pattern is being used?
 - The game has an in-game chat system. A player can message his/her friends individually, or in groups. When he sends a message to a group of people, the effect is to send the message to each individual in the group.
 - Evaluate expression using syntax tree.
 - In Java's Swing hierarchy, all containers are components, and can thus any container can be added to any other container. This is an example of ...
 - Your contact list contains individual people as well as groups of people, such as families or relatives, for example, Mom, Dad, and then four members of a family consisting of Uncle Bob, Aunt Carol, Cousin Jason and Cousin Katelyn. You want to be able to message the people individually, or in groups, such as Parents, or Uncle Bob's Family. When you message a group of people, the effect is to send the same message to each individual in the group.


### Decorator
 - On a project team, certain people have additional responsibility. For example, one team member might be in charge of documentation, and another member might be in charge of testing. We don’t want to implement these additional responsibilities by subclassing, since team members’ roles might change over time. Which pattern should we use to implement these extra responsibilities?
 - In an etail system, tickets printed in the US need headers and footers. Tickets printed in Canada need headers and footers in English and French. Tickets printed in Australia need only footers.
 - Suppose we are designing a hierarchy of cars for an ordering system. The system has a notion of a basic car. Instead of being a basic car, the vehicle we are ordering could also be a sports car, a minivan, or an SUV. Various features can be added to each of these cars: premium sound system, rear video camera, collision avoidance, etc. Cars with each set of features behave in a certain way. But we don t want to create separate subclasses for each combination of cars and features.


### Facade
 - **A structural pattern that avoids the need to pass many parameters in a single message.**
 - There's an app that allows you to manage several bank accounts, which may belong to different banks. The app allows you to view at a glance your total balance, recurring expenses and previous statements for all linked accounts. This makes it easier to get an eagle's eye overview of all your finances.
 - You are tasked with designing an application for scheduling a conference room. This process uses web services from the facilities team for heating, IT team for audiovisual and with security to grant access to the rooms at the booked time. However, to save employees time you create simple interface which takes care of this in the background. What pattern is used here.
 - Suppose I want to draw UML diagrams, and I am have a general drawing program that will draw geometric shapes, lines, arrows, etc. But I just want to draw shapes that represent classes and objects, and connect them via edges that have arrows at one end. What design pattern should I use to reduce the complexity of the API to something I can remember and easily use?


### Flyweight
 - **A pattern that saves memory by allowing objects to share parts of their implementation.**
 - Suppose we have a wordprocessor that needs to place variable-width characters of different font sizes on a page. To do this, we need a lot of information on each character. We need a glyph object that contains the outline of the character. We need font metrics to know where to place this character relative to other characters and the baseline. We don't have enough space to store this information for each character; if we tried, the memory requirement would be so high that the application would grind to a halt.
 - There are at least 100 people playing the game at any point of time. Your game has n weapons. Each weapon object consumes a lot of memory. Instead of creating different weapon objects for each player, the game loads a single complete weapon object, and shares as much of its data as possible with each user of weapons.
 - You have a large number of objects being used in your software. These objects are not simple ones . They are heavy objects which consume a lot of system resources. The customer complains about the same to you. They do not want to increase the resources and they want you to improve the efficiency of the software. What design pattern would you recommend to the customer? Most of the objects have properties which are generic and properties which are specific to them. They also insist that you do not use template design pattern.
 - A program uses a large number of objects, which are created independently by the same constructor. The objects are complex, and consume a large amount of memory. They differ only in a few characteristics. The customer wants to reduce memory usage, and comes to you for help. What design pattern would you recommend to the customer?
 - When a printer puts characters onto paper, it does not load each characters design (glyph) each time the character is to be printed; rather it loads the glyphs once and simply refers to that glyph each time it needs to be rendered on the paper.


### Proxy
 - You want to take some run-time measurements on your system. Each time a method is called, you want to record the parameters and the return address, and the clock time. Before your method returns, you want to again record the clock time, so you can determine how long it took the method to execute. Rather than doing this by instrumenting the run-time system, you want to transform the source program so that instead of calling method x directly, the caller calls a "wrapper" for x that logs all of this information (parameters, return address, time). Then the "wrapper" calls the original method x. After the original method returns, the wrapper calculates the time spent in the method, and then returns back to the caller of the original method.
 - The Java Remote Method Invocation (RMI) system allows an object running in one Java virtual machine to invoke methods on an object running in another Java virtual machine.
 - An Internet filter for a school accepts requests to visit Web pages. Unless it is determined that the pages contain inappropriate content, the requested URL is sent on to the school’s ISP.
 - You have multiple machines in the cloud , each of them called as "instance" . These machines form a loadbalancing system. However, the user accesses only one application, suggesting there is only one entry point to the system. Which design pattern has been used here?
 - An internet filter is implemented by having a browser call a stand-in page that will in turn call the real page, unless it violates the
proprietors acceptable-use policy, in which case it will display a message saying that access to that page is blocked.




## Behavioral Patterns

### Chain of Responsibility
 - You are writing a Java run-time system, which responds to various kinds of exceptions. The exception needs to be handled by the first exception handler it encounters that handles exceptions of the appropriate type. For example, a FileNotFoundException can be handled by an exception handler for that specific exception type, but it can also be handled by a handler for IOExceptions, if one is encountered before a handler for FileNotFoundExceptions.
 - In a coin-sorting machine, coins are placed into the slot at the top. If they are small enough to fall into the slot for dimes, they do. If not, they are passed over the penny slot, and pennies fall out at this point. Next are nickels; coins that are small enough fall into the nickel slot. Other coins make their way to the quarter slot.
 - According to Wikipedia, mime sniffing is the practice of inspecting the content of a byte stream to attempt to deduce the file format of the data within it. Let’s say we implement mime sniffing by first sending the content to an HTML parser, and if it’s not recognized as HTML, we send it to a plaintext parser. If it’s not recognized as plaintext, we try to parse it as JSON, and if that doesn’t succeed, as XML.
 -  In poker, the hand containing the highest card wins, unless one hand holds a pair. The highest pair wins unless one hand contains two pairs. If multiple hands have two pairs, the one whose highest pair contains the highest cards wins, unless one hand has three of a kind. Three of a kind is beaten by a straight (5 cards in sequence, like 5,6,7,8,9). A straight is beaten by a flush (5 cards in the same suit). A flush is beaten by a full house (three of one kind, a pair of another). A full house is beaten by 4 of a kind. 4 of a kind is beaten by a straight-flush (5 cards in sequence and all of the same suit), and the highest hand is a royal flush (the ace-high version of the straight flush). The code for determining the winning hand in poker uses what design pattern?
 -  Here is a physical analogy to a design pattern. Which pattern? When you call Microsoft tech support, you deal with a Level 1 consultant. If (s)he can t answer your question, eventually you are routed to a Level 2 consultant. If this consultant can t answer your question, you are transferred to a Level 3 consultant. 


### Command
 - **A pattern that stores up an action for later use.**
 - A program uses closures to implement various operations. For example, it might want to perform a set of statistical tests on data, pre-specifying certain parameters. A closure is created of a method and its pre-specified parameters; then when the program needs to perform a particular test, it simply executes the appropriate closure.
 - You write a program to simulate an auto dealership. A customer comes into the service department, describes what needs to be done to her car, and the person behind the desk takes the report and passes it on to the mechanics, who perform the requested operation.
 - In an editor, we want to allow editing functions to be assigned to keys, so that each time we press a key, the corresponding function will be executed. Note that we can assign an arbitrary macro (i.e., procedures or functions) to be invoked by hitting a key. And the user needs to be allowed to map a key to a particular function at any time; then later, when the key is pressed, the function will be invoked.


### Interpreter
 - A calculator program takes input from the user indicating which arithmetic operations are to be performed on which operands, and then performs the operations immediately.


### Iterator
 - Allow users to scan over and access the elements of a collection without knowing the underlying representation of the collection.
 - In a hot potato game, the potato (any random object) is passed around a group of people (seated in a circle). The potato can be passed to the person on your left or your right.
 - A TV remote control has forward and backward buttons for choosing channels. The forward button takes you to the next highernumbered channel that you can receive; the back button takes you to the closest lowernumbered channel. Pressing either button repeatedly will cycle through all the channels.


### Mediator
  - You have a traffic control system for an intersection. There are sensors in the road at each entry point to detect approaching traffic. In addition to sensors, there is also a timer that can change a light for a certain period of time, based upon information provided by the various sensors. For the traffic lights to work, all these objects have to interact using control logic.


### Memento
 - Certain characters have a special ability to warp back in time. When a player uses this ability their character travels back to the state that it was a certain number of seconds before.
 - A checkpoint in database systems is a point from which the database engine starts applying changes by reading the log files while attempting to recover after an unexpected database crash due to power outage. The Design Consultant says "The use of checkpoints by reading log files to recover"
 - Your roommate has paid rent to the property manager in time. You need to pay your share of the rent to him. You plan to transfer $400 from your account to his. Something goes wrong during the transfer and both accounts are reverted to their previous state. You have two identical computers, and need to install a few components (power supply, graphics card) in one of them. Because youre not sure that they will work together, you rearrange the components in one of the cabinets, keeping the other cabinet for reference in case you need to put the old components back into the first computer.
 - In the future, you are implementing a system for time travel. It is to allow you to travel to any era for your life, and later, you can return to the present, or to another era you have been to. Once you return, everything is as it was when you left.



### Observer
 - **MVC is made up of instances of this pattern.**
 - Consider the case of a medical-alert system that provides alerts to different types of patients. The system sends alerts via email to patients, but what if in the future this system has a requirement to send alerts to mobile devices (SMS). What type of pattern would help ease the addition of new devices with the least impact or change to the server?
 - There are random events in the game, e.g., a loot box containing medical supplies and weapons is spawned at a random location on the map. All the players currently playing the game need to be notified of any such event. 
 - Consumers who register their cars or other products online are notified in the event of a recall, or a release of a new version of the software, etc.



### State
 - A vending machine that requires a certain amount of money to be inserted before dispensing a product. 
 - The customer says, "I have a problem. We want to design an ATM machine such that, when the user clicks option 1, (s)he is prompted for the password. If the password is not strong enough, the console responds with an appropriate message, and the user has to try again. If the password is strong enough, then the machine proceeds to request for cash. If there is enough cash in ATM,the machine dispenses. If not, the machine gives a message asking the user to try another ATM machine".
 - An HVAC system is controlled by a thermostat. It can heat or cool, and the fan can be set to on or auto . If it is in heat mode, and the thermostat is changed to a temperature above the current temperature, it will turn on the furnace. If the thermostat is changed to a temperature at or below the current temperature, it will not do anything. Conversely, when it is in cooling mode and the thermostat is set to a temperature at or above the current temperature, it will not do anything. But if the thermostat is set to a lower temperature, then it will turn on the compressor. If the fan is set to auto , then it goes on only when the unit needs to raise or lower the temperature. If it is set to on , then the fan is always blowing.
 - You are developing a game, and your task is to change an actress's physical positions based on her previous conditions. For instance, If actress is standing, and user presses "Up", she should jump. If in same position user presses down she should sit. If actress is sitting, and user presses "Up", she should stand up. What design pattern should be used here.


### Strategy
 - People place an online order through a company’s website. The company wants its customers to enter the shipping option—either pickup or delivery or expedited shipping. The company processes the order according to the given shipping option, which involves procedures like notifying the shipping agent and notifying the customer of delivery.
 - The Comparator class, given that it allows different sorting policies (alphabetical, numerical, chronological etc) to be implemented by writing code to compare parameters in different ways.
 - A company ships its products the "best" way, via USPS, UPS, or FedEx depending on cost, pickup time, and delivery time. When it is communicating with USPS's web service, it knows how to query the cost, pickup, and delivery-time methods of USPS; when it contacts FedEx's web service, it knows how to query its methods, etc.
 - You want to write a numerical integration package that calculates the area under different curves. It needs to calculate the area under trigonometric functions, polynomial functions, and exponential functions, among others.
 - We are building Taypals add a payment option feature. A user can add a credit card, debit card, or bank account. The processing steps differ depending on the given payment option.


### Template method
 - **A pattern that ensures that different procedures follow the same steps in the same order.**
 - Each time that XUnit tests a class, it runs the setup method, then the tests, then the teardown method.
 - Suppose that we have a set of operations implemented differently for different kinds of objects, just like the Strategy pattern, but in this case the operations always need to be invoked in the same order, regardless of what kind of object is being worked on. Which pattern should we use?


### Visitor
 - **A pattern that involves sending messages to the parameters that were passed in another method call.**
 - You visit Chipotle and look for different menu items like tortilla or a veg bowl or a non-veg bowl. After selecting the menu, you need to select different ingredients and the quantity of each that you would want in your menu item. So, Chipotle would like its customers to know various information about each menu item and ingredient (e.g., calorie counts, presence or absence of gluten, nuts, pork, etc.) that goes into the menu.
 - Uber, given that you ask it to take it somewhere and it controls vechile and route.
 - There is a monkey named "DesignMonkey" who is responsible for counting the number of fruits on each branch in the tree. What design pattern should the DesignMonkey use? Assume that the monkey never gets tired.
 - When different kinds of Money objects (SimpleMoney, MixedMoney) are being added together, whic design pattern could be used to avoid checking the class of the object that is being added? Your answer should be the name of a design pattern; it should not involve a tree format for representing money.


