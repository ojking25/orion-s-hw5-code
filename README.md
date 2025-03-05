# CS272-S25 HW5

In this HW, you will write functions to perform unit conversions for volumes! 

## Instructions

### 1. `getAmount`

Implement the `getAmount` function such that anytime it is called, it returns the number in the `amount` input element if it exists, otherwise it returns `null`.

**Hint:** We did something very similar in an in-class exercise!

### 2. `getFromUnit`

Implement the `getFromUnit` function such that anytime it is called, it returns string in the `op-unit-from` select element. If the select element is equal to the string `"Please specify a unit"`, you should return `null` instead.

### 3. `getToUnit`

Implement the `getToUnit` function such that anytime it is called, it returns string in the `op-unit-to` select element. If the select element is equal to the string `"Please specify a unit"`, you should return `null` instead.

**Note:** Your code for functions `getFromUnit` and `getToUnit` will be quite similar! If you want, you can create *another* function that both `getFromUnit` and `getToUnit` call, but it is *not* a requirement.

### 4. `convert`

Implement the `convert` function such that anytime it is called, it will first retrieve the "amount", "from unit", and "to unit" using the functions that you defined in steps 1-3. If any of these are `null`, you should `alert` the user to "Please complete all fields before continuing!" Furthermore, if the "amount" is negative, you should `alert` the user to "Please enter a positive amount!"

Otherwise, you should call the `getResult` function, passing along these 3 pieces of data, and `alert` the user of the result of the calculation, e.g. "2 Pint is equal to 4 Cup". You do *not* need to round any numbers.

You implement `getResult` in the next and final step.

### 5. `getResult`

In `getResult`, you will perform the conversion. To convert between these units, you should know that...
 - There are 8 fl oz in a cup
 - There are 2 cups in a pint
 - There are 2 pints in a quart
 - There are 4 quarts in a gallon.

To make your calculation simple, I would recommend using the `getUnitInFlOz` function. This function takes a unit and returns the number of fl oz in that unit.

Remember, to convert units we do *not* need dozens of `if` statements! We simply need to convert to a common unit and do the math!

```
2 pint     16 fl oz   1 cup
        *  -------- * -------- = 4 cup
           1 pint     8 fl oz
           
```

## Scenarios

These scenarios should help you test your code! Please test your code thoroughly; these are just examples to help you in your testing.

### Scenario 1

Given 2 pints and converting to cups, the `alert` should be...

"2 Pint is equal to 4 Cup"

### Scenario 2

Given 4 cups and converting to gallons, the `alert` should be...

"4 Cup is equal to 0.25 Gallon"

### Scenario 3

Given 20.5 fl oz and converting to pints, the `alert` should be...

"20.5 Fl Oz is equal to 1.28125 Pint"

You may have some rounding error; that is okay!

### Scenario 4

Given that some of the form fields are not filled out, the `alert` should be...

"Please complete all fields before continuing!"

### Scenario 5

Given that all of the form fields are filled out, but the amount is negative, the `alert` should be...

"Please enter a positive amount!"