# Midterm Kickoff

## Learning Outcomes:

* How to work on a team
  * Encounter conflicts in code
  * Merge conflict - when two or more devs touch the same file, learning how to resolve these and know this isn't the end of the world (like EDD)
* Solidify skills

* This will be a profile builder


## Steps for building a project
**Stop at EVERY point and get a mentor to review**



1. Pick An Idea! [x]
2. Check the requirements
  - Turn these requirements into "**User Stories**"
  - This project will model the real world more: you'll be given direction in a job about what to do and with what tech stack
3. Turn user stories into an ERD
4. Define our routes
5. Wireframes/Mockups
6. Look at the stack requirements
7. Decide between single or multi-page app (or a combo)
8. Git collaboration
9. Splitting up the work

### User Stories:

* Descriptions of how users interact with a product.

As a _____, I want to _____, because _______.

Example from map project:

As a user I want to see a list of available maps because I want to see where my friends like to get burgers.

Can also be negated values: 

As a non-logged in user I should not _______.

* We use the user stories to find entities - this is our pathway to tables and ERD / database desige


### ERD 

* Turn your nouns into tables
* Now we have secrets and things users want

### Routes

* Define BREAD routes to all of our resources, RESTful


### Wireframes/Mockups

ex: balsamiq, moqups as wireframe examples

* For users we want to do what works rather than overcomplicate --> unless we're working on some sort of 'mindblower' website, just steal good designs and standards :)

We develop, not design




### MVP:
* Minimum Viable Product - minimum set of features that are needed for a user to decide the product has value
  - Getting out there fast and generating some revenue allows us to start developing some more feature.

We're NOT doing anything that comes to the realm of MVP.

We're developing a **Minimum Viable Demo**
  If it's not getting demoed, don't build it!
  This will keep it tight, and avoid scope creep

**Demo what you DO build!**

### User Login:

* Don't

Andy sending us some login routing suggestion.
Andy told us 'don't waste time on user login', we already have a saved project that shows us how to do this.

### Tech Stack:

Look at the stack requirement

(For of, for in instead of for each)


If we do client side rendering, use jQuery
One or more of CSS frameworks (including flexbox)


The node skeleton uses 'database injection' style with the routes rather than requiring it into the route file


### Single Page or Multi-page app?
* Not mutually exclusive - multi-page apps that have some single page client side rendering.
* We can use both, depending on the project (or what we want to practice)


### Git

* Learning merge conflicts
* Follow git best practices
  * **Use branches** - don't ever code on MASTER
  * Build solid code and then merge it in. 
  * DON'T PUSH CODE THE MORNING OF DEMO (conversely, don't deploy on Friday afternooon in the real world)
* Merge into master locally OR on Github
* On Github? Pull Request (PR) 
  * This allows us to do a code review, and get revisions. 

DO NOT CODE ON MASTER

Feel free to talk to mentors about the workflow of push/pull

### Splitting up the work:

Three main choices

* Horizontally - both working on the same layer of the stack. IE, both doing front end, or both on database
* Vertically - one working on FE, one working on BE
* Pair Programming

Celebrating the Success and victories, no matter how small

### Kanban Boards

I.e. Trello

Columns of stickynotes - basic categories:  To-Do | In Progress | Done

GitHub Projects is a great feature, we should check out. 


### Deployment
* Do you, or don't you.
  Local? In the cloud?

When we do so, usually deploy to Heroku - a simple way for deploying a javascript app.
Another option is DigitalOcean


WE DON'T NEED TO DEPLY TO THE WEB, for midterm OR final.

If we want to, Google - "How to deploy node"



