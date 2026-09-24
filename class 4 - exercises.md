## EXERCISE 1

### The Dice Object

1. Create a Dice object
2. create a "side" property that can be changed on definition
3. create a method that rolls the dice and returns a number between 1 and the side.
4. create 2 instances of dice, one with 6 sides and one with 12 sides and run the methods on each.

```
// Option 1 - this only creates one object and updates its sides before rolling again
const Dice = {
    sides: 6,
    rollDice: function() {
        return Math.floor(this.sides * Math.random()) + 1;
   },
   checkRoll() {
        let val = this.rollDice();
        if ( val > 3 ) {
          return `You rolled a ${val}. Good job - you rolled a large number!`;
        } else {
          return `You rolled a ${val}. Too bad - try again!`;
        }
   }
}

Dice.sides = 6;
console.log( Dice.checkRoll() );

Dice.sides = 12;
console.log( Dice.checkRoll() );
```

```
// Option 2 - this approach creates a templates that can create multiple dices as needed without overwriting each other!
class Dice {
  constructor( side = 4 ) {
    this.sides = side;
  }
  rollDice() {
    return Math.floor(this.sides * Math.random()) + 1;
  }
   checkRoll() {
        let val = this.rollDice();
        if ( val > 3 ) {
          return `You rolled a ${val}. Good job - you rolled a large number!`;
        } else {
          return `You rolled a ${val}. Too bad - try again!`;
        }
   }
};
// first dice
const dice1 = new Dice( 6 );
console.log( dice1.checkRoll() );

// second dice
const dice2 = new Dice( 12 );
console.log( dice2.checkRoll() );
```


## EXERCISE 2

### The Maths Areas Calculator Object
1. Create a Shape object
2. create a "number of side" property that can be changed on definition or later.
3. create a method for areas calculation for the shape based on the number of sides provided.
4. Similarly create a method for perimeter calculation for the shape based on the number of sides provided

```
class Shape {
  constructor( side = 4, len = 1 ) {
    this.sides = side;
    this.length = len;
  }
  calcPer() {
    return (this.sides * this.length);
    return a;
  }
  calcArea() {
    // (sides x length^2) / (4 x tan(pi/sides))
    return (this.sides * this.length*this.length) / (4 * Math.tan(Math.PI/this.sides));
  }
};

// create a pantagon
const penta = new Shape( 5, 2 );
console.log( 'area is: ' + penta.calcArea() );
console.log( 'perimeter is: ' + penta.calcPer() );

// create an octagon
const octa = new Shape( 8, 2 );
console.log( 'area is: ' + octa.calcArea() );
console.log( 'perimeter is: ' + octa.calcPer() );

```

## EXERCISE 3

### The Movie Object
1. Create a few Movie objects using a constructor.
2. Create some properties to describe each movie. eg.

```
const movie1 = {
  title: "The Shawshank Redemption",
  year: 1994,
  director: "Frank Darabont",
  genre: "Drama",
};

const movie2 = {
  title: "The Lord of the Rings: The Fellowship of the Ring",
  year: 2001,
  director: "Peter Jackson",
  genre: "Fantasy",
};

const movie3 = {
  title: "Spirited Away",
  year: 2001,
  director: "Hayao Miyazaki",
  genre: "Animation",
};
```
3. Access and modify individual movie information.
4. Create a method that returns that movie's information in a formatted string. (e.g., "Title: The Shawshank Redemption, Year: 1994, Director: Frank Darabont, Genre: Drama").
5. Use a loop to iterate through the movies array and print the formatted summary for each movie.

```
class Movie {
  constructor(title, year, director, genre) {
    this.title = title;
    this.year = year;
    this.director = director;
    this.genre = genre;
  }
  getTitle() {
    return this.title;
  }
  getYear() {
    return this.year;
  }
  getDirector() {
    return this.director;
  }
  getGenre() {
    return this.genre;
  }
  getInfo() {
    return `The movie ${this.title} was directed by ${this.director} and was released in ${this.year}. It is a ${this.genre} movie.`;
  }
}

const movie1 = new Movie("The Shawshank Redemption", 1994, "Frank Darabont", "Drama");
const movie2 = new Movie("The Lord of the Rings: The Fellowship of the Ring", 2001, "Peter Jackson", "Fantasy");
const movie3 = new Movie("Spirited Away", 2001, "Hayao Miyazaki", "Animation");

console.log(movie1.getInfo());
console.log(movie2.getInfo());
console.log(movie3.getInfo());

const movies = [ movie1, movie2, movie3 ];
for (const movie of movies) {
  console.log(movie.getInfo());
}
```
