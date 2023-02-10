##Description
This is a clone of the AIRBnB web application which consists of of a custom command-line interface for data management, and the base classes for the storage of this data. Console commands allow the user to create, update, and destroy objects, as well as manage file storage. Using a system of JSON serialization/deserialization, storage is persistent between sessions.

##Usage
The console works both in interactive mode and non-interactive mode, much like a Unix shell. It prints a prompt (hbnb) and waits for the user for input.
Command	Example

Run the console	./console.py

Quit the console	(hbnb) quit

Display the help for a command	(hbnb) help <command>

Create an object (prints its id)	(hbnb) create <class>

Show an object	(hbnb) show <class> <id> or (hbnb) <class>.show(<id>)

Destroy an object	(hbnb) destroy <class> <id> or (hbnb) <class>.destroy(<id>)

Show all objects, or all instances of a class	(hbnb) all or (hbnb) all <class>

Update an attribute of an object	(hbnb) update <class> <id> <attribute name> "<attribute value>" or (hbnb) <class>.update(<id>, <attribute name>, "<attribute value>")

Non-interactive mode example
$ echo "help" | ./console.py

(hbnb)



Documented commands (type help <topic>):

========================================

EOF  all  count  create  destroy  help  quit  show  update

##File Storage
The folder engine manages the serialization and deserialization of all the data, following a JSON format.



A FileStorage class is defined in file_storage.py with methods to follow this flow: <object> -> to_dict() -> <dictionary> -> JSON dump -> <json string> -> FILE -> <json string> -> JSON load -> <dictionary> -> <object>



The init.py file contains the instantiation of the FileStorage class called storage, followed by a call to the method reload() on that instance. This allows the storage to be reloaded automatically at initialization, which recovers the serialized data.

*Tests*
All the code is tested with the unittest module. The test for the classes are in the test_models folder.

*Authors*
Sarafina Wanjiku Gathoni <sarah.wanjiku.gathoni@gmail.com>
Karabo Dikolomela
