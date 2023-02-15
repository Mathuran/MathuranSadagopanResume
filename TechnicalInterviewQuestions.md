### How to test an app?

Static Testing

- Looking over just the code for the app and checking if logically the app is sound.
- Analogous to proof reading.

Dynamic Testing 
		
- Running the code to see if everything is preforming correctly.
- There are 2 common types of Dynamic Testing 

White Box Testing

- In this type of testing you know what the code is and are testing to see if at a certain point in the code it is operating correctly. This is Analogous to testing a node in a circuit.

Black Box Testing 

- In this type of testing you don’t know what the code is and are simply testing the specifications of the application and whether they are running correctly. This type of testing often includes many different techniques, such as variation, equivalence partitioning and boundary value testing

#### How to make a better app?

Improve runtime and memory. Improve user interface and add relevant features. 

### What is an app?

An app is a piece of software built to do a certain task that is designed to run on a mobile device or PC.

#### What is an API, IDE?

API 
- application programming interface, set of functions or tools that allow you to access features of other services, be it classes, libraries, or servers.

IDE
- integrated development environment, is software that helps you develop code by providing integrated tools for the language on top of a code editor such as for debugging, build automation, serial monitor, and git integration. 

What is MS Access 
- it’s a data management system from Microsoft 

What is a Q Series Data Base

- a high performance data base used to store and process large amounts of data that is pushed into RAM for faster access than disk storage 


### What security considerations do you have when a deployment is made to a remote server?
Have one person control the deployment
Have a pipeline which is connected to the code base and ensure the main branch is always a working and running version of the app. Have signoffs on main branch to do checks 
Have multiple stages of deployment to test and check the app
How to think through scalability problem.
Scalability is usually a problem of dealing with massive amounts of data that cannot be stored on one machine or a compute process that becomes too big to handle on one CPU.
Solve problem for assuming it can be done on one computer or for a smaller scenario
Understand how much data can fit on one machine and the problems that would come from splitting up the data.
Finally attempt to solve the issue identified in step 2. Step 2 may or may not be an issue that requires you to change the solution from step one but more so alter the setup and preparation that needs to be done to solve the problem
