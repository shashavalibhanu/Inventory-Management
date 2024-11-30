# Inventory-Management
Exercise Learning Goals
This learning exercise helped evolve your knowledge of Dicts.

You've unlocked 5 concepts:

Se
Sets
Cl
Classes
Ge
Generators
Un
Unpacking And Multiple Assignment
Di
Dict Methods
You've unlocked 40 exercises:

Icon for exercise called Cater Waiter
Cater Waiter
Icon for exercise called Word Count
Word Count
Icon for exercise called Scrabble Score
Scrabble Score
Icon for exercise called Kindergarten Garden
Kindergarten Garden
Icon for exercise called Grade School
Grade School
Icon for exercise called Tournament
Tournament
Icon for exercise called Book Store
Book Store
Icon for exercise called Allergies
Allergies
Icon for exercise called Meetup
Meetup
Icon for exercise called Say
Say
Icon for exercise called Scale Generator
Scale Generator
Icon for exercise called ETL
ETL
Icon for exercise called Two Bucket
Two Bucket
Icon for exercise called Robot Simulator
Robot Simulator
Icon for exercise called DOT DSL
DOT DSL
Icon for exercise called Knapsack
Knapsack
Icon for exercise called Circular Buffer
Circular Buffer
Icon for exercise called Forth
Forth
Icon for exercise called Ledger
Ledger
Icon for exercise called Word Search
Word Search
Icon for exercise called Satellite
Satellite
Icon for exercise called Zipper
Zipper
Icon for exercise called POV
POV
Icon for exercise called Spiral Matrix
Spiral Matrix
Icon for exercise called Food Chain
Food Chain
Icon for exercise called Dominoes
Dominoes
Icon for exercise called REST API
REST API
Icon for exercise called Zebra Puzzle
Zebra Puzzle
Icon for exercise called PaaS I/O
PaaS I/O
Icon for exercise called Alphametics
Alphametics
Icon for exercise called D&D Character
D&D Character
Icon for exercise called Space Age
Space Age
Icon for exercise called Hangman
Hangman
Icon for exercise called SGF Parsing
SGF Parsing
Icon for exercise called Ellen's Alien Game
Ellen's Alien Game
Icon for exercise called Plane Tickets
Plane Tickets
Icon for exercise called Locomotive Engineer
Locomotive Engineer
Icon for exercise called Bottle Song
Bottle Song
Icon for exercise called Proverb
Proverb
Icon for exercise called Mecha Munch Management
Mecha Munch Management
Introduction
A dictionary (dict) in Python is a data structure that associates hashable keys to values and is known in other programming languages as a resizable hash table, hashmap, or associative array. Dictionaries are Python's only built-in mapping type.

Keys must be hashable and unique across the dictionary. Key types can include numbers, str, or tuples (of immutable values). They cannot contain mutable data structures such as lists, dicts, or sets. As of Python 3.7, dict key order is guaranteed to be the order in which entries are inserted.

values can be of any data type or structure. Values can also nest arbitrarily, so they can include lists-of-lists, sub-dictionaries, and other custom or compound data structures.

Given a key, dictionaries can retrieve a value in (on average) constant time (independent of the number of entries). Compared to searching for a value within a list or array (without knowing the index position), a dict uses significantly more memory, but has very rapid retrieval. Dictionaries are especially useful in scenarios where the collection of items is large and must be accessed and updated frequently.

Dictionary Construction
Dictionaries can be created in many ways. The two most straightforward are using the dict()constructor or declaring a dict literal.

The dict() Class Constructor
dict() (the constructor for the dictionary class) can be used with any iterable of key, value pairs or with a series of <name>=<value> arguments:

#Passing a list of key,value tuples.
>>> wombat = dict([('name', 'Wombat'),('speed', 23),('land_animal', True)])
{'name': 'Wombat', 'speed': 23, 'land_animal': True}


#Using key=value arguments.
>>> bear = dict(name="Black Bear", speed=40, land_animal=True)
{'name': 'Black Bear', 'speed': 40, 'land_animal': True}
Dictionary Literals
A dict can also be directly entered as a dictionary literal, using curly brackets ({}) enclosing key : value pairs:

>>> whale = {"name": "Blue Whale", "speed": 35, "land_animal": False}
{'name': 'Blue Whale', 'speed': 35, 'land_animal': False}
Accessing Values in a Dictionary
You can access an entry in a dictionary using a key in square ([]) brackets. If a key does not exist n the dict, a KeyError is thrown:

>>> bear["speed"]
40

>>> bear["color"]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'color'
Accessing an entry via the .get(<key>, <default value>) method can avoid the KeyError:

>>> bear.get("color", 'not found')
'not found'
Changing or Adding Dictionary Values
You can change an entry value by assigning to its key:

#Assigning the value "Grizzly Bear" to the name key.
>>> bear["name"] = "Grizzly Bear"
{'name': 'Grizzly Bear', 'speed': 40, 'land_animal': True}

>>> whale["speed"] = 25
{'name': 'Blue Whale', 'speed': 25, 'land_animal': False}
New key:value pairs can be added in the same fashion:

# Adding an new "color" key with a new "tawney" value.
>>> bear["color"] = 'tawney'
{'name': 'Grizzly Bear', 'speed': 40, 'land_animal': True, 'color': 'tawney'}

>>> whale["blowholes"] = 1
{'name': 'Blue Whale', 'speed': 25, 'land_animal': False, 'blowholes': 1}
Removing (Pop-ing) Dictionary Entries
You can use the .pop(<key>) method to delete a dictionary entry. .pop() removes the (key, value) pair and returns the value for use. Like .get(), .pop(<key>) accepts second argument (dict.pop(<key>, <default value>)) that will be returned if the key is not found. This prevents a KeyError being raised:

#Using .pop() removes both the key and value, returning the value.
>>> bear.pop("name")
'Grizzly Bear'


#The "name" key is now removed from the dictionary.
#Attempting .pop() a second time will throw a KeyError.
>>> bear.pop("name")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'name'


#Using a default argument with .pop() will prevent a KeyError from a missing key.
>>> bear.pop("name", "Unknown")
'Unknown'
Looping through/Iterating over a Dictionary
Looping through a dictionary using for item in dict or while item will iterate over only the keys by default. You can access the values within the same loop by using square brackets:

>>> for key in bear:
>>>     print((key, bear[key])) #this forms a tuple of (key, value) and prints it.
('name', 'Black Bear')
('speed', 40)
('land_animal', True)
You can also use the .items() method, which returns (key, value) tuples automatically:

#dict.items() forms (key, value tuples) that can be unpacked and iterated over.
>>> for key, value in whale.items():
>>>     print(key, ":", value)
name : Blue Whale
speed : 25
land_animal : False
blowholes : 1
Likewise, the .keys() method will return keys and the .values() method will return the values.

Instructions
In this exercise, you will be managing an inventory system.

The inventory should be organized by the item name and it should keep track of the number of items available.

You will have to handle adding items to an inventory. Each time an item appears in a given list, the item's quantity should be increased by 1 in the inventory. You will also have to handle deleting items from an inventory by decreasing quantities by 1 when requested.

Finally, you will need to implement a function that will return all the key-value pairs in a given inventory as a list of tuples.

1. Create an inventory based on a list
Implement the create_inventory(<input list>) function that creates an "inventory" from an input list of items. It should return a dict containing each item name paired with their respective quantity.

>>> create_inventory(["coal", "wood", "wood", "diamond", "diamond", "diamond"])
{"coal":1, "wood":2, "diamond":3}
2. Add items from a list to an existing dictionary
Implement the add_items(<inventory dict>, <item list>) function that adds a list of items to the passed-in inventory:

>>> add_items({"coal":1}, ["wood", "iron", "coal", "wood"])
{"coal":2, "wood":2, "iron":1}
3. Decrement items from the inventory
Implement the decrement_items(<inventory dict>, <items list>) function that takes a list of items. Your function should remove 1 from an item count for each time that item appears on the list:

>>> decrement_items({"coal":3, "diamond":1, "iron":5}, ["diamond", "coal", "iron", "iron"])
{"coal":2, "diamond":0, "iron":3}
Item counts in the inventory should not be allowed to fall below 0. If the number of times an item appears on the input list exceeds the count available, the quantity listed for that item should remain at 0. Additional requests for removing counts should be ignored once the count falls to zero.

>>> decrement_items({"coal":2, "wood":1, "diamond":2}, ["coal", "coal", "wood", "wood", "diamond"])
{"coal":0, "wood":0, "diamond":1}
4. Remove an entry entirely from the inventory
Implement the remove_item(<inventory dict>, <item>) function that removes an item and its count entirely from an inventory:

>>> remove_item({"coal":2, "wood":1, "diamond":2}, "coal")
{"wood":1, "diamond":2}
If the item is not found in the inventory, the function should return the original inventory unchanged.

>>> remove_item({"coal":2, "wood":1, "diamond":2}, "gold")
{"coal":2, "wood":1, "diamond":2}
5. Return the entire content of the inventory
Implement the list_inventory(<inventory dict>) function that takes an inventory and returns a list of (item, quantity) tuples. The list should only include the available items (with a quantity greater than zero):

>>> list_inventory({"coal":7, "wood":11, "diamond":2, "iron":7, "silver":0})
[('coal', 7), ('diamond', 2), ('iron', 7), ('wood', 11)]
