


Hafiz briefly spoke about the benefits of error driven development again. The 'happy path' of other online tutorials and stuff, while real development is a massive percentage biased towards solving errors.


Recognizing patterns early is key. 
Get lots of mentorship now; the expectation of how much help we need should be going down.



Pair programming- focused on Katas and problem solving. 

Good code - low WTF per min. lol

# Day 2 Lecture

## Reading Code

Read the way JS will read. 
  Defined functions. (But doesn't care).
  
From first execution point to definition

Poke holes in the cheese with console logs to see what's happening. 

We have to intuit based on variable names (unlike the JS interpreter).

## Code

### Arrays:

Resolve indexes in your mind to


Two indexs can point to the same 'address' - 

Primitive behaviour vs non-primitive - Strings can be changed individually, whereas 

sub array points outside the array. 

Array - Non-primitive
Primitive - string, boolean, number

Primitives are copied by value, non-primitives are copied by reference.

Pass by value, pass by reference

Good for one class of data (a list of people, or flavours, or something)

### Objects

Key - Value data structure. Data with labels

Utilize explainer variables (`const name = instructors[0];`)

Arrays can be useful but also tie us to index reliance.

Key-Value pairs can be thought of like a two column excel table

Better for a variety of info classes (Info about a person)

Getters & Setters.

Getters: hs.name

Setters: hs.name = 'Daniel'


### Methods in Objects

Stored functions can be shown (their structure) without executing
  What's the difference between calling the function and calling the structure?


**Avoid calling external variables when possible.**

function property is the name for stored function (Method is another name for a function stored in an object)

`this` key word is possible. `this` is set by executing 


[Breakout notes](https://gist.github.com/hafbau/ffc28b276c621127c4c6b80e51e86e69):

q0:

x: 5
y:5

x:5
y:6

x:6
y:6

q1:

'person: {person object: age - 30;}

'person: {person object: age 31};


q2:

A - all the keys
Object iteration - 

C: - error, because for...of is for iterable objects (like arrays);


q3: indexs returned: 0, 1, 2, 3;


q4:  

'Do yoga' 'Take out garbage' 'Dry clothes' 'undefined'

q5: 
First- it's not actually calling the function (needs brackets)
Reference error - object undefined 

add a this. keyword



For...in - works on objects and arrays

and for...of ... arrays only. Objects are not iterable (objects have no .length property. Strings work here)