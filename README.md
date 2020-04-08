# ECMAScript 6


###### Let's learn some of the new features of JavaScript 6 or ECMAScript 6.

### let vs const
> `let` is used to set mutable data.*
```
let fname = 'John';
let lname = 'Smith'; 
lname = 'Williams'; //lname gets overwritten
let message = `${fname} ${lname}`;
alert(message);
```
> `const` is used to set imutable data as per below.
```
let fname = 'John';
const lname = 'Smith'; 
lname = 'Williams'; //lname cannot overwrite the current value
let message = `${fname} ${lname}`;
alert(message); 
```

### Using template string

```
let fname = 'John';
let lname = 'Smith';
let age = prompt(`Guess John's age...`)

//Using template string
let message = `${fname} ${lname} is ${age} years old`; // <= this is a template string example
alert(message); 
```

### Default parameters 

> The user and message has a default value, but can accept new values.

```
function welcome(user = 'Mistery person', message = 'Goodday'){
    alert(`Hello ${user}, ${message}`);
}
welcome();
```

### Arrow Functions 

> A new feature that is sofisticated and very clear and redable
```
let gretting = (message) => alert(`${message} everyone!`);
gretting('Hello'); */
```
> Now lets create a object and add a function and call it at the end to execute.
```
let australia = {
    // add property
    beaches : ['Bondi', 'Manly', 'Coogee'],
    // add method
    printWithDash: function() {
        setTimeout( () => console.log(this.beaches.join(' - ')), 3000)
    }
};

australia.printWithDash();
```


### Destructuring object

> This is a great feature to break down big objects

```
let uniStudent = student => {
    let { name, university } = student; // At this line we are destructuring the object, which is really usiful to work with big objects.
    console.log( `${name} from ${university}` );
};

uniStudent({
    name: 'John',
    university: 'University of Sydney'
});
```
### Or
```
let uniStudent = ({name, university}) => {
    console.log( `${name} from ${university}` );
};
```

### Destructuring arrays

> At the example below we close to display the 'Kosciuszko' as we have added ',' to the firstMountain

```
let [ , firstMountain] = ['Everest' , 'Kosciuszko', 'Fish Tail'];
console.log(firstMountain);
```

### Restructuring Objects

> The same way ECMAScript 6 helps to destructuting one object, we can use to restructure on object.

```
 var name = 'Everest';
 var height = 8848;
 var output = function() { console.log(`Mt. ${this.name} is ${this.height} meter tall`); };
  
var adventures = {name, height, output} //At this line we restructure adventures.
adventures.output();
```

### Spread Operator

> The spreed oporator works to copy data to modify of create a new instance.
 
> Example one
```
 var mountains = ['Everest', 'Fish Tail', 'Kosciuszko'];
 var mountainsFromJapan  = ['Fuji'];

 var allMountains = [...mountains, ...mountainsFromJapan]
 
 console.log(allMountains);
```
> Example two
 ```
 var rivers = ['Sunkoshi', 'Tamakoshhi', 'Saptakoshi'];
 var [first, ...rest] = rivers;

 console.log(rest); // output: 'Tamakoshhi', 'Saptakoshi'
```

### Classes, constructor and super

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
```
//Sub class
class Expedition extends Holiday{

    constructor(destination, days, gear){
        super(destination,days);
        this.gear = gear;
    }

    info() {
        super.info();
        console.log(`Bring your ${this.gear.join(' and your ')}`)
    }
}
```
```
const tripWithGear = new Expedition('Everest', 15, ['Sunglasses', 'Flags', 'Camera'])
tripWithGear.info();
```
