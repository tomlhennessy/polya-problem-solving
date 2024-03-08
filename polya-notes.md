# Polya's Problem-Solving Steps


1. Understand the problem:
* Crucial step; don't rush.
* Restate the problem, understand all terms.
* Identify constraints and edge cases.

2. Make a plan:
* Break down the problem.
* Draw, solve simpler versions, find patterns.
* Communication is key; share your thought process

3. Carry out the plan:
* Translate plan into code.
* Syntax is simpler if steps 1 and 2 are clear.
* Execute the plan methodically:

```javascript
function moveZeroes(nums) {
    let last = nums.length - 1;
    for (let i = 0; i < last; i++) {
        if (nums[i] === 0) {
            [nums[i], nums[last]] = [nums[last], nums[i]];
            last--;
        }
    }
    return nums;
}
```

4. Look back and improve:
* Revisit code for bugs, edge cases, and optimisation.
* Verify solution against constraints.
* Identify and address potential improvements.
* Efficient solutions are valuable.

```javascript
function moveZeroes(nums) {
    let last = nums.length - 1;
    for (let i = 0; i < last; i++) {
        if (nums[i] === 0) {
            nums.splice(i, 1);
            nums.push(0);
            last--;
        }
    }
    return nums;
}
```

> Remember: if stuck, reassess understanding or plan. Consistent practice leads to mastery.


## Debugging Techniques:

1. Read the Error Message
* Error messages provide valuable hints.
* e.g. correct parameter name in a function

2. Use console.log() for Debugging
* Print information during code execution
* e.g. identify skipped items in an array removal function

3. Write tests:
* Cover common use and edge cases in your tests.
* e.g. fixing a countdown function for negative or decimal inputs

## Debugging Example

```javascript
function longestName(names) {

    // Set the first name to be the longest
    set currentLongest = names[1];

    // Check each other name in the array starting from the second
    for (let i = 2 ; i <= names.Length ; i++) {

        // If the name we're checking is longer than our
        // current longest, set that name to be the new longest
        if (names[i].Length > currentLongest.Length) {
            currentLongest = names[i];
        }

    }
```
1. Variable assignment
* Initialise 'currentLongest' with the first name, not the second

2. Loop Range and Case Sensitivity
* the loop should start from the second name in the array and use '<' instead of '<='
* JavaScript is case-sensitive, so use 'length' instead of 'Length for array length

Corrected code:

```javascript
function longestName(names) {

    // Set the first name to be the longest
    let currentLongest = names[0];

    // Check each other name in the array starting from the second
    for (let i = 1; i < names.length; i++) {

        // If the name we're checking is longer than our
        // current longest, set that name to be the new longest
        if (names[i].length > currentLongest.length) {
            currentLongest = names[i];
        }

    }

    return currentLongest;
}

testNames = ["James", "Patricia", "Michael", "Elizabeth", "Christopher",
             "Sarah", "Margaret", "Kenneth", "Stephanie", "Jonathan",
             "Jeremy", "Samantha", "Alexander", "Catherine", "Benjamin"]

console.log(longestName(testNames)); // "Christopher"
```
