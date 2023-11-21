# Activity 10

## Name

Add Your Name Here

---

During today's class session, we spent time to set up Django boilerplate code. There were specific commands that we used for this work. Below, each command is listed and you are to explain what is does and why it is necessary. You may be expected to read more about these commands at Django [website](https://www.djangoproject.com/start/) to learn more.

### Challenge Questions

#### 1
Explain what the following lines are doing in todays code

```
#!/usr/bin/env python3

# libraries 
from pymongo import MongoClient
import string

# creating connections for communicating with MongoDB
client = MongoClient('localhost:27017')
db = client.mongodemo # The name of the collection is mongodemo
 
# Define functions here!

# User Interaction

print("\t [+] Data BEFORE addition")
read() # call read function

print("\t [+] Insert some data")
insert() # call insert function()

print("\t [+] Data AFTER addition")
read() # call read function to view the changes

print("\t [+] Update Data")
update() # call update to ask for new information to replace existing

print("\t [+] Data AFTER Update")
read() # call read function to view the changes
```

Response: TODO

#### 2

Explain what the following function is doing.

```
def read():
   """ function to read records from mongo db """
   try:
      empCol = db.Employee.find()
      print("\n Found: all data from DataEmployee \n")

      for emp in empCol:
         print(f"\t [+] {emp}")

   except Exception as e:
      print(str(e))
# end of read()
```

Response: TODO

#### 3

Explain what the following function is doing.

```
def insert():
   """ Function to insert data into mongo db """
   employeeId = input('Enter Employee id :')
   employeeFirstName = input('Enter FirstName :')
   employeeLastName = input('Enter LastName :')
   employeeAge = input('Enter age :')
   employeeCountry = input('Enter Country :')

   # insert the data into the base
   try:
      db.Employee.insert_one(
      {
      "id": employeeId,
      "firstName":employeeFirstName,
      "lastName":employeeLastName,
      "age":employeeAge,
      "country":employeeCountry
      })
      print("\nInserted data successfully\n")

   except Exception as e:
      print(str(e))
# end of insert()
```

Response: TODO

#### 4

Explain what the following function is doing.

```
def update():
   """ Function to update record to mongo db """
   print("  Update:")
   try:
      employeeId = input('  Enter Employee id :')
      employeeFirstName = input('  Enter FirstName :')
      employeeLastName = input('  Enter LastName :')
      employeeAge = input('  Enter age :')
      employeeCountry = input('  Enter Country :')

      # update the record with the new information
      db.Employee.update_one(
      {"id": employeeId},
      {
      "$set": {
      "firstName":employeeFirstName,
      "lastName":employeeLastName,
      "age":employeeAge,
      "country":employeeCountry
      }})

      print("\nRecords updated successfully. \n")

   except Exception as e:
      print(str(e))
   # end of update()
```

Response: TODO

#### 5

Why is it necessary to run the `read()` function after each operation with the database?


Response: TODO


#### 6

Can you think of any applications for which this type of code would be most suitably used?

Response: TODO

--
(Did you remember to place your name at the top of this document?)
