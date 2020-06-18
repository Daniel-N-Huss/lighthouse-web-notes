# End-to-End Testing with Cypress

## Jest Vs Cypress:

- Jest:

  - Command line interface
  - Tests were part of the source code
  - Runs a part of our app
  - Unit/integration testing

- Cypress:

  - Runs in the browser
  - Tests are adjacent to the source (not inside /src)
  - Runs tests against a running server (Cypress won't run our code)
  - Can test any site on the net
  - Integration / E2E Testing

> Cypress tests ARE user stories!

## Cypress:

Cypress creates a folder at the root level of the app.

We get some structure from the app.

A file for fixtures.
Integration folder that holds our tests.

Mocha, Chai, jQuery, all of it is included in Cypress so we don't need to require or bring anything in.

We can get Cypress to take photos and videos during testing that we can use for marketing or documentation.

Cypress best practices are for long tests rather than lots of small tests. Big test with lots of assertions.

### Commands:

call with

```js
cy;
```

.get is a jQuery alias, so we can call things:

```js
cy.get("#id");
```

Built on mocha and chai, so we can use all the mocha and chai commands.

Configuration for Cypress in cypress.json.

### Tests:

Can do two things with Cypress:

1. A command: ie. "Go here, click that"
2. Assert things about the DOM.

We're working with promises here, so we can chain our cypress things together. Cypress handles the promise wrapping for us.

Check out Chai Chainers: chai or chai-jquery

We can use a beforeEach so that each test will visit the page, then do the rest of the test.

### Aliasing

We can store things as an alias,

```js
cy.get("something").as("inputField");

cy.get("@inputField").doStuff;
```

### Giving Commands:

We can tell .type() some commands like: {backspace}. Check cy docs for more.

### Faking API calls:

1. Set up fake web server

```js
cy.server();
```

2. load the fixture into memory (from the fixtures folder in cypress)

```js
cy.fixture('itunes.json).as('itunesData);
```

3. Fake the endpoint request

```js
cy.route({
  method: "GET",
  url: "search*",
  delay: 500,
  response: "@itunesData",
}).as("getSearch");
```

4. type into input field
5. grab the load spinner and check for visibility
   4 & 5 are similar to above

6. check to see if the data has displayed correctly (check for a particular album)
   wait for async:

```js
cy.wait("@getSearch").get("main").contains(`${albumName}`);
```

7. grab spinner again, and check for no visibility
8. untick the explicit box
9. make sure the explicit album is hidden

Cypress launches everything as a promise, all at the same time.`

No matter how we order our testing (which usually is written with a logical flow).
If we want tests to be sequential, we have to chain them. Temporal concerns need chained testing.

Check out the Cypress best practices.

Tons of plugins for testing other functionality (like social logins)