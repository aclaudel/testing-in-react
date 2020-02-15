# Testing in React (WIP)

## Reasons to test React

A React application can be as complex as a backend application.

- Conditional branches
- Data processing
- Asynchronous events
- API calls
- State management

And on top of this complexity, we add another layer: the UI.

- Components
  - Interactions between components  
  - Conditional rendering
- Layout, Styling etc.
- UX

## Types of tests

### Visual tests

- Layout, Design, Styling
- UX

These tests are better when humans execute them.
Some of them can be automated, usually for a non-regression test suite.

### Non-visual tests

- Anything else 

These tests don't require humans at all, because they don't even need a UI to be executed.
Most of the code is plain Typescript and therefore can easily be unit tested.

JSX Components can give the impression that we are dealing with UI and therefore it's easier
to do visual tests.
But in the end, Components are just objects that you instantiate using a different syntax.
They could render empty divs everywhere and your tests should still pass, because you're testing
the display **logic**, not the display itself.  

## Approach when writing tests

When adding a new features, it is sometimes hard to write the test for it,
especially when the manual and visual test looks way more simpler to do.
It's easy to think that, because we are in the front-end, tests are harder to write
and should be done by humans. 

However most of the time, tests don't require manual / visual tests.
The problem is that you're likely to test many things at the same time.

### Why I can't write tests

When struggling, the question to ask is *What am I testing ?*
If the answer includes more that one of the concerns listed at the beginning,
then you are testing to many things.

When you cannot test individually each concerns, then you're doing too many things
at the same place.

### What I used to do

The easiest thing to do for the very short term is do manual testing in the UI.
It looks simple, doesn't require to write anything.

You have the sensation of being productive because it seems that you're going faster.

But the technical debts will grow extremely fast.

If tests aren't automated, you'll try to execute them as less as possible.
That means, no refactoring and further features will be painful to add.

If tests are automated (but still rely on the UI), then the tests will brake
when the UI will change, even though the logic is not changing.   

### What I do now

Single Responsibility Principle.

If I can't test, I refactor first.

## Chapters

- Conditional rendering
  - Black box with RTL
  - White box with Enzyme
- Filtering, Sorting logic
  - Classic tests with Jest
  - Mocks with ts-mockito
- State management
  - Asynchronous events
  - Class components
- Visual tests with storybook
