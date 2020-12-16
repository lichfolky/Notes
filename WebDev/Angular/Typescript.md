**Tuple**
>// Declare a tuple type  
>let x: [string, number];  
>// Initialize it  
>x = ["hello", 10]; // OK  

**Array**

>let list: number[] = [1, 2, 3];  
>let list: Array<number> = [1, 2, 3];  

any  
void  
null and undefined
--strictNullChecks

Union types

**as** for type assertions

#### var -> let
IIFE - an Immediately Invoked Function Expression

for (var i = 0; i < 10; i++) {
    // capture the current state of 'i'
    // by invoking a function with its current value
    (function(i) {
        setTimeout(function() { console.log(i); }, 100 * i);
    })(i);
}

without(i) the output whould be 10, 10,....

let less permissive!

#### const
const is not re-assignable, but not immutable!


#### Destructuring

>let input = [1, 2];  
>let [first, second] = input;  
>console.log(first); // outputs 1  
>console.log(second); // outputs 2  
>[first, second] = [second, first];  
>let [first, ...rest] = [1, 2, 3, 4];  
>let [, second, , fourth] = [1, 2, 3, 4];  

#### Spreading

>let first = [1, 2];  
>let second = [3, 4];  
>let bothPlus = [0, ...first, ...second, 5];  

also with objects

>let defaults = { food: "spicy", price: "$$", ambiance: "noisy" };  
>let search = { ...defaults, food: "rich" };  

overwrites from left to right, food == "rich"
loses methods
