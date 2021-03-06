# JS Control Flow Challenges

## Basic Challenges
1. Which of the following are truthy values? (hint: try `if("abc"){console.log("I'm truthy!")}` in the JS console)
  * 1
  * "abc"
  * ""
  * []
  * {}
  * -1
  * (1+1)
  * 0
  * 3.14159
  * Object
2. Log to the console "This is awesome!" 25 times.
3. Create a snippet inside of developer tools. Create snippets to do the rest of the challenges.
4. In your snippet, create a new variable that is an array of 4 phrases: `Howdy there`, `OMG`, `javascript`, and `Pair Programming`.
5. Loop over the array and console log each phrase.
6. Loop over the array and log each phrase to the console if its total length is 4 or longer. Otherwise, console log that the phrase is too short.
6. Come up with three different ways to break a `for` loop that result in three different errors. What three different errors did you get?
1. Jimmy loves roller coasters, but there are a bunch of rules (ugh!) for riding:

For starters, it costs 5 tokens. Here's how we might code that:

```
var tokens = 3; // Jimmy's tokens

// Can he ride?
if ( tokens >= 5 ) {
    console.log("Step right up!");
} else {
    console.log("Sorry, you can't ride")
}
```
Edit the code above to check the following additional Requirements:

    Must be at least 4ft tall
    Must be at least 12 years old
    Replace the prevoius rule: now riders under 12 must be accompanied by an adult
    (If the boss isn't looking, you can sneak in!)
    Riders with a park pass get in free.


## Stretch Challenges

5. In a snippet, create a new variable that is an array containing 5 objects, each of which has the keys `name` and `age`. You can make up the names and ages for your objects.
6. Log to the console the name value of each object.
7. Create and log an array with the age of each object in months (assume the original ages were in years).
9. Find and log the sum of the ages.
8. Log to the console only the name of the oldest person.
9. Log to the console the index of each element in the array.
10. Create and log an array containing only the objects with an age over 20.
11. Create and log an array of all the names, in which any names that begin with a consonant are upper case.
12. Create and log an array that is the original array in a random order.
