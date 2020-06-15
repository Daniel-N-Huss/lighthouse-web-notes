# SQL Intro

UI is a window to the data, which is where our value and service comes from. 

## Why do we need a database?

* Small datasets are all we've been using so far, scale is a problem
* Data permanence - we've been keeping everything in a volitile data state (in memory), move our data to an outside, external storage.
* Other things, from weekend work (security, ) 

## RDBMS:

Relational Database Management Server/System

This will be what we 'talk' to on the server side to hold our database. We don't talk TO the database, we talk to this managing server. 

<-----communicates with----->

Web Client <---TCP/HTTP---> Web Server <--- TCP/POSTGRES ---> RDBMS
  
  
  We don't embed credentials within Web Clients, we use our Web Server to communicate with the DB, we never let clients talk to the DB.


## Structured Data:

- Tabular format (something Javascript doesn't have)
  - Rows / Columns
    - Table represents entities (everything in the table represents one entitiy and everything on the table is a like type of entitiy)
    - Row === Entitity Instance === **record**
    - Column === adjectives (describe the entitiy) === **field**

- This structure gives us tons of power.

- Most Efficient, and best practice, means we should store the data totally agnostic to its usage.
  Example: Users = id, username, password, birthdate
    All of these data points only matter in relation to each other. 
  


NoSQL === no structure (structureless data format) - so you can just.. dump arrays and objects into memory.


## Database queries:

Declarative programming where we need to 'ask politely' for stuff, and we don't really know what's happening on the back end.

vs. JS is imperative programming (We tell Javascript exactly what to do)


```SQL
SELECT * FROM users;
```


### Schema-

Entity Relation Diagram
  What's our structure of the data?
  All our data will conform to this structure (Even if some of the values are null)

* Primary Key - ID
  - first_name
  - last_name
  - email
  - age
  - country
  - payment_due_date

Asking for all users SELECT * FROM users

SELECT COUNT(id) AS num_users  <--- Aggregation Query.

  When we set aliases with AS, think of other devs. Declare names that make sense of what you're counting!!

**SQL is case insensitive, so we write our queries with all the SQL in caps to show that's the sql code to other devs** 

WHERE statements - we can logic test and filter records

Chain where statements with AND / OR

SQL has a difference between ' ' and " "   ---> " " indicates column/field names
  When learining new languages we have to learn to read the errors


SQL doesn't store data in any particular order, so if we want it ordered we have to request that. 

Default ORDER BY is ascending (smallest to largest, a - z), we must specificy **ORDER BY age DESC** --> ASC is the default


Dates come as strings: 
```SQL 
WHERE payment_due_date < 'yy/mm/dd';
```
  This is a problem, and is a *magic string*, hard coded in. We should pull it out and make it a variable, or a function. We will have to update the query every month (or day). How do we abstract for variables?  Should be:


```SQL
WHERE payment_due_date < NOW();
-- Double hyphen is the SQL comment!
```

DISTINCT (another aggregate, only give unique values back please)
  but be careful, it might not be as intuitive as it sounds. 
  Distinct gets blown out by anything that brings in a unique query. 
  We often only use distinct for aggregate queries (like counting how many users are from a country)


### Multiple Tables:

Each table has a Primary Key, as we know.

But we can store that Primary Key in another table, which becomes a 
**Foreign Key** --> the foreign key in a table stores ALL the data from that entry on it's host table.

The more foreign keys we have, the less human readable that data becomes. However, data agnostic approach means we DON'T care about how the data is accessed (including by people scanning with their eyeballs)


In this example we don't have songs existing on multiple albums. 

JOIN tables:

```sql
SELECT * FROM albums JOIN songs;
```
 this gives us a syntax error, doesn't know what we're joined on.

 ```sql
SELECT * FROM albums JOIN songs ON id = album_id;
```
  also an error because both tables have an id, and says id is ambiguous

have to say:
 ```sql
SELECT * FROM albums JOIN songs ON albums.id = album_id;
```

Same syntax as how we grab objects

We're seeing our Songs id as default. We always use the ID from the rightmost joined table. 

GROUP BY is another aggregator.
We can collapse by album name, and count songs on each album.
Anything that's not aggregated must go into a GROUP BY, aggregation indicator. 


Look up SQL Order of Execution

HAVING is a WHERE, but for the GROUP BY parameter

JOIN --> INNER JOIN (default), only shows overlaps of both.

we can also bring in data that has no associated data on the other table with a LEFT JOIN or RIGHT JOIN (LEFT JOIN from select table, RIGHT JOIN calls the joined table)

This helps us call data when we're unsure about what data might exist in the table.

AVG brings back the full float, which we can bring in rounding ROUND()

### Sub-Query:
For comparing tables against themselves. 
Wrap sub-queries in parens. 
Subquery utilizies joins we establish in our main query

SELECT doesn't influence other parts of the SQL query, only where we need to see it. 

Subquery is somewhat rare, only used when we need 'meta' info about a table.


## SQL is heckin fast

It's backed by linear algebra and calculus, and it's amazingly fast. It's ALWAYS going to be faster than Javascript. It's better for us to use precise SQL and give Javascript EXACTLY what data you want it to use. 

Rule of thumb: for every second of wait time, 10% of your users/customers go away. So like, 10 seconds and you've lost everyone. 

Pagination
OFFSET (page.number - 1 * 10) (subtract page you're on, multiply by how many things you want to show on each page)