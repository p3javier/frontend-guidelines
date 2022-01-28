# Testing Guidelines For React Projects

Here I will document all of the testing philosofy and practice that I would like to implement across my projects based on React.

## Introduction

I base React testing in 3 mantras:

> Many integration tests. No snapshot tests. Few unit tests. Few e2e tests.

> Try to reduce mocking to the minimal.

and,

> The more your tests resemble the way your software is used the more confidence they can give you. <br>
> *Kent C. Dodds*

### Testing Tools

I usually use the next tech stack for testing my React projects:

* Jest
* React testing Library
* Cypress

And that's all with these 3 libraries you can test almost everything in your React app.

## Testing Theory

The idea of testing in the frontend is apply **TDD** *Test Driven Development*. This means two write the tests before the actual implementation code.

### Why TDD?

With test-driven development (TDD), developers create and automate tests that validate the functionality of the software they are coding. They write only the code that gets validated in order to keep it clear and simple, eliminate bugs, and speed up the development process.

### The Process

![TDD](https://marsner.com/wp-content/uploads/test-driven-development-TDD.png)

### Types Of Testing

### Unit Testing

Unit testing is a level of software testing where individual units/components of a software are tested. In the React world this means testing an individual React Component or pure functions.

#### What To Test?

1. The first unit test of each component should be if it's render without crashing.

2. The second unit test of a component should be if it contains the right information once it is loaded.
    * You should look for specific strings or patterns.
    * Or look for things like the placeholder text of an input or a test id.
    * All of this is done in my case via [Testing Library React](https://testing-library.com/docs/react-testing-library/intro).

3. The third unit test of a component should be if the component React properly to an user interaction.
    * For example if we click a button that should make a popup to show on display test that the component is present in the tree after click the button, not before. (This sometimes is more an integration test than a unit test and the line that separate them is not always clear).

### Integration Testing

Integration tests serve a critical place in your testing plan by providing a balance between the speed of unit tests and the “real world” interactions of an end-to-end test.

### What To Test?

Here are some of the things React developers want to do when writing integration tests:

* Test application use-cases from the user’s perspective. Users access information on a web page and interact with available controls.
* Mock API calls to not depend on API availability and state for passing/failing tests.
* Mock browser APIs (for example, local storage) since they simply do not exist in test environment.
* Assert on React DOM state (browser DOM or a native mobile environment).

Now, for some things we should try to avoid when writing React app integration tests:

* Test implementation details. Implementation changes should only break a test if they indeed introduced a bug.
* Mock too much. We want to test how all the parts of the app are working together.
* Shallow render. We want to test the composition of all the components in the app down to the smallest component.
