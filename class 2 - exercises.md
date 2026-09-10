## EXERCISE 1

### Condition odd or even
Define a number variable (can be random) and then create a condition to check if that variable  is odd or even

```
let my_num = Math.random() * 20;
my_num = Math.floor( my_num );

console.log( "Randomly generated number is ", my_num);

if ( my_num % 2 === 0 ) {
  console.log(" my_num is an even number" );
} else {
  console.log( "my_num is an odd number" );
}
```

Here's an alternative approach using division, instead of modulus!
```
let my_num = Math.random() * 20;
my_num = Math.floor( my_num );

console.log( "Randomly generated number is ", my_num);

// divide by two
let divided_num = my_num / 2;

if ( Number.isInteger( divided_num ) === true ) {
  console.log( "my_num is an even number" );
} else {
  console.log( "my_num is an odd number" );
}
```

## EXERCISE 2

### Using switch for multiple conditions
Use the below rolling dice generator to create a random number between 1 and 6.
Then write a condition to check that number and do something for each check eg. return the value back to console using console.log(...).
Consider using the switch operator for it - see below for an interesting use of skipping the break expression!

```
let number = Math.ceil(Math.random() * 6);
console.log( "Randomly generated number is ", number );

if ( number === 4 ) {
  console.log( 'You rolled a fantastic four' );
} else if ( number === 5 ) {
  console.log( 'You rolled a sturdy five' );
} else if( number === 6 ){
  console.log( 'You rolled a lucky six' );
} else {
  console.log( 'Too bad, You rolled a number less than four' );
}
```

Here's an alternative approach using division, instead of modulus!
```
// alternative - using switch - cleaner syntax
let number = Math.ceil(Math.random() * 6);
console.log( "Randomly generated number is ", number );

switch (number) {
  case (4):
    console.log( 'You rolled a fantastic four' );
    break;
  case (5):
    console.log( 'You rolled a sturdy five' );
    break;
  case (6):
    console.log( 'You rolled a lucky six' );
    break;
  default:
    console.log( 'Too bad, You rolled a number less than four' );
    break;
}
```

