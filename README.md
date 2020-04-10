# ECMAScript 6


###### Let's learn some of the new features of JavaScript 6 or ECMAScript 6.

### let vs const
> `let` is used to set mutable data and will be accessible inside a block or class.
```
let fname = 'John';
let lname = 'Smith'; 
lname = 'Williams'; //lname gets overwritten
let message = `${fname} ${lname}`;
alert(message); // John Williams
```
> `const` is used to set immutable data as per line two below. The third line is trying to set a new value, but the compiler will throw an exception, as a const can only accept a value on its creation.
```
let fname = 'John';
const lname = 'Smith'; 
lname = 'Williams'; // <-- ERROR - lname cannot overwrite the current value 
let message = `${fname} ${lname}`;
alert(message); 
```

### Using template string

> A sophisticated way to put together complex data using '`${variable}`'.

```
let fname = 'John';
let lname = 'Smith';
let age = prompt(`Guess John's age...`)

//Using template string
let message = `${fname} ${lname} is ${age} years old`; // <= this is a template string example
alert(message);  // John Smith
```

### Default parameters 

> A value can be passed in the parameter initialization as a default value and can accept new values.

```
function welcome(user = 'Mistery person', message = 'Goodday'){
    alert(`Hello ${user}, ${message}`); // Mistery person, Goodday
}
welcome();
```

### Arrow Functions 

> A new way to create sophisticated and readable methods, as per the first example below.

```
let gretting = (message) => alert(`${message} everyone!`);
gretting('Hello'); */
```
> Now, let's create a new object and add a function to it and call it at the end to execute. Note the set timeout accepts an arrow function that executes after 3000 milliseconds.
Something else to note is 'this' is used to access beaches inside the object block within the arrow function.
```
let australia = {
    // add property
    beaches : ['Bondi', 'Manly', 'Coogee'],
    // add method
    printWithDash: function() {
        setTimeout( () => console.log( this.beaches.join(' - ')), 3000)
    }
};
australia.printWithDash();
```

### Destructuring object

> Destructuring objects is a great feature to break down big objects instead create multiple variables and accessing its properties with '.' dot.

```
let uniStudent = student => {
    let { name, university } = student; // destructuring student object
    console.log( `${name} from ${university}` );
};

uniStudent({
    name: 'John',
    university: 'University of Sydney'
});
```
### Or
> Destructuring the object in the parameter, which will shrink the solution.
```
let uniStudent = ({name, university}) => {
    console.log( `${name} from ${university}` );
};
```

### Destructuring arrays

> The same solution can be applied to arrays. The example below displays the 'Kosciuszko' in the console with simply add ',' to the firstMountain in the new array.

```
let [ , firstMountain] = ['Everest' , 'Kosciuszko', 'Fish Tail'];
console.log(firstMountain);
```

### Restructuring Objects

> The same way ECMAScript 6 helps to destructuring one object, it can be used to restructure an object.

```
 var name = 'Everest';
 var height = 8848;
 var output = function() { console.log(`Mt. ${this.name} is ${this.height} meter tall`); };
  
var adventures = {name, height, output} // This line restructure adventures as an object.
adventures.output();
```

### Spread Operator

> The spread operator creates a new instance of copy data. It is used to union data from arrays or objects.
 
> Example one
```
 var mountains = ['Everest', 'Fish Tail', 'Kosciuszko'];
 var mountainsFromJapan  = ['Fuji'];

 var allMountains = [...mountains, ...mountainsFromJapan]; // Join arrays
 
 console.log(allMountains); // 'Everest', 'Fish Tail', 'Kosciuszko', 'Fuji'
```
> Example two first will get assigned the value of 'Everest', but the spread operator '...rest', will take all the rest of the data into it.
 ```
 var rivers = ['Sunkoshi', 'Tamakoshhi', 'Saptakoshi'];
 var [first, ...rest] = rivers;

 console.log(rest); // 'Tamakoshhi', 'Saptakoshi'
```

### Classes, constructor and super

> The base class is defined with a set of properties when instantiated in the constructor.

```
//Super class
class Holiday {

    constructor(destination, days){
        this.destination = destination;
        this.days = days;
    }

    info() {
        console.log(`${this.destination} will take ${this.days} days.`);
    }
}
```
> The sub-class needs to pass to the constructor the base parameters, plus the new parameters of the sub-class, followed by the 'super()', which will set the values to the base class.
```
//Sub class
class Expedition extends Holiday{

    constructor(destination, days, gear){
        super(destination, days);
        this.gear = gear;
    }

    info() {
        super.info();
        console.log(`Bring your ${this.gear.join(' and your ')}`);
    }
}
```
```
const tripWithGear = new Expedition('Everest', 15, ['Sunglasses', 'Flags', 'Camera']);
tripWithGear.info();

// output:
// Everest will take 15 days.
// Bring your Sunglasses and your Flags and your Camera

```
