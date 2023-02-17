# Refactor Widgets App

In this project, you will refactor the Class Components in an existing React
application into Function Components. By the end of the project, you should be
able to

* Use the `useState` Hook to convert state instance variables to function-based
  state variables
* Explain the use cases for the lifecycle methods `componentDidMount`,
  `componentDidUpdate`, and `componentWillUnmount`, as well as when each will
  run
* Use `useEffect` to replicate the behavior of those lifecycle methods while
  also understanding how the application of `useEffect` differs from those
  methods
* Use `useRef` to create a ref that will persist across renders
* Use React Testing Library tests running on a Jest framework to confirm the
  accuracy of your refactor

## Phase 0: Set Up

Start by cloning the Widgets application starter from the `Download` link at the
bottom of this page.

Run `npm install` to install all the packages.

To start the application, run `npm start` and open [http://localhost:3000] to
see the widgets displayed. Each section shown on the page is a different
component in the __components__ folder.

### Tests

You always want to have tests covering your code whenever you refactor,
especially when refactoring someone else's code. The tests provide you with
confidence that your refactors have not changed the code's behavior.

Fortunately, the code in this project already has good test coverage, so you
don't have to spend time writing tests before you start. Each component--i.e.,
the 4 widgets and `App`--has an associated test file in __src/\_\_tests\_\___.
(The tests for `Clock` and `ClockToggle` appear in the same file, as does their
code.)

The tests are written using React Testing Library on a Jest framework. Look
through the test files and try to understand what they are doing. **Do NOT
change any of the code in the test files.**

Run `npm test` to start the tests in watch mode. When first starting, tests will
run for any code file that has changed. Thereafter, Jest will run any test whose
corresponding code file changes. To run all tests, press `a` in the terminal
window where Jest is watching. To run the tests in a specific file, press `p`
and, at the prompt, type enough of the filename to signify which test you want
to run. (Jest will run all test files that match the regex pattern you enter.)
So, e.g., to run only the Clock tests, you could enter `Clock` (or just `Clo`,
or even just `4`) at the prompt.

Run all the tests now; everything should be green! You want to maintain that
green as you refactor. It is recommended that you just leave the tests running
in watch mode so it is easy to see if changes you make break the code.

**WARNING**  
In watch mode, Jest will run tests as soon as it recognizes that a change has
been made. **This means that it will sometimes run a test before you finish
making a change, raising the likelihood of false fails and, occasionally, false
passes.** Often, however, you will complete the change before the test
finishes. When Jest shows you code, it draws from the current file, so it can
look like the finished code produced the reported result. **To save yourself
hours of debugging non-existent bugs, always rerun a test a second time before
acting on its results.**

## Phase 1: `App`

In this first phase, you will refactor the `App` component from a Class
Component into a Function Component. The `App` component, which receives no
props, is rendered inside of the entry file (__src/index.js__) and is
responsible for rendering the different widgets.

Begin by changing the opening class declaration to a function declaration.

Next, use `useState` to convert the `showClock` state variable in the `App`
Class Component into a state variable in the `App` Function Component. (Don't
forget to update your imports!) Replace any calls to `this.setState` with calls
to the setter function returned by `useState`. Similarly, convert any instances
of `this.state.showClock` to its corresponding `showClock` variable in the
Function Component. Make sure your tests are green before continuing!

Convert the `toggleClock` instance method into a regular function. Change any
references to `this.toggleClock` simply to `toggleClock` to reflect this change.

In addition to keeping all the tests are green, you can also test your changes
in the browser. Run `npm start`. Do all the widgets still appear and work?
Congratulations! You've successfully converted your first Class Component into a
Function Component.

**Worth noting:** All the components that the `App` component renders as its
children are still Class Components, while `App` is now a Function Component.
**Class and Function Components can be used interchangeably in a React
application.**

[http://localhost:3000]: http://localhost:3000