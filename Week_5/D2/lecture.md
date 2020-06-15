# Database Design


## Some DO's and DO NOT'S


### Primary Keys / Foreign Keys

- Primary keys must be unique in the table
  - But we're also not limited to the datatype we give it, as long as it's unique (even a boolean, as long as we only have one or two, theoretically)
  - We can most often use Autoincrementing Integers
  - Data always has the potential to change - don't hang your primary key hat on given data (like emails or something), but also avoid being meta-data about the record
    - This means aboid compund keys, the combo of two or more fields forming a unique pair

- Foreign Key needs to be the same data type as the primary key! 
  - Clearly makes sense

- Chosing the right data type can happen around issues like memory size limits (possible to use smallserial): it's always possible to scale up later, and VERY difficult to go back to a smaller type


### Data Types:

Javascript is so flexible, we never need to specify what the data type we're giving it is.
Not so for databases.

- Every field NEEDS to have a data type
- On insert, a type comparison happens (and if we try to insert the wrong type it will error, type safety for data integrity!)
- For strings we use either VARCHAR(variable character, best for when we get input from users), or CHAR (fixed length, good for things we control like hashed passwords)
- What do we do with phone numbers and postal codes? Store them as strings. We can get weird behaviour from JS for things like USA postal codes (with a leading 0 that gets stripped off)


### Relationship Types
- One-to-One: 
  * one record in the first table is related to one record in the second table
  * Weird use cases.. why split exactly identical tables? Could be a data conserving measure, or something really smart. VERY rare, if this is coming up in our bootcamp TALK TO A MENTOR, DO YOU REALLY WANT THIS?
- One-to-Many
  * One record in the first table is related to 0 or more records in the second table
  * This is the most common
- Many-to-Many
  * 0 or more records in the first table are related to zero or more reconds in the second table
  * Many to many solves some interesting problems for us, which we will cover today.
  * Usually a relationship between things that have complicated data - an example being online orders, where we want to have multiple items in any customers order and catalog items can be ordered by any customer
  * Needs a junction table, or a bridge table, that hosts the foreign keys between the two
  * Created by two or more One-To-Many relationships



### Naming Conventions:
  These will change everywhere we go, DO WHAT SENIORS WANT, or what already exists in the project


**LHL Naming Conventions**
- Always use snake_case (lower case seperated by underscore)
- Table names should be plural, because they're holding multiple instances of the same entitity
- Primary Keys should usually be `id`
- Foreign Keys, append `_id` to the singular of the primary key table name
    - from users table to another table, `users.id === user_id`  (A singular instance of id)
- Please DONT use spaces in field/table names or you have to wrap every query in "" 

### Design Concepts from Andy

- Required Fields
  - We can mark fields as required. Sometimes there will be situations where we won't have the data we eventually want to fill in, based on the initial state of the record
- Default values
  - Intelligent defaults! Things like a boolean field saying if the order is still active, timestamps (Created at, edited at, are VERY common components of database records we will see a lot),
- Calculated Fields : **NO**
  - A field that the value will be calculated from one or more other fields. We don't need to calculate and store a user age from their birthdate because we can just calculate it when we need it.
  - These can often fall out of sync when the main data points, and cause us headaches. **There should only be one single source of truth for a peice of data**, one place we go look things up.
- Try not to delete anything. Ever.
  - Often there are data retention laws (around how long we need to keep records)
  - Use something like an `active` boolean instead, where we can turn off the active part, and we can sql query for active ones
- Pull repeating values out to a seperate table
  - Things like city names repeat, and get fatfingered or spelled entered differently
  - **Lookup table** for cities
  - Control users behaviour when possible. Don't make users type in city / country names
- Consider a `type` field
  - Rather than make a sales order table and a purchase order table (Which contain nearly identical information), use a type field
