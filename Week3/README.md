## Strings

- It is a way for the program to store sequence of chars or bytes that represent chars

- Strings a immutable - big word alert.  Simply means they cannot be changed.  The variables can be reassigned a value but the string cannot be changed.

- Strings behave like an array... sort of

```
let firstName = 'Bart Simpson'

for(let i=0; i<firstName.length; i++){
  console.log(firstName[i])
}
```
There is quite a bit there that we have not covered yet
- square brackets (these => [])
- for loop
- arrays 

### String Interpolation - Remember this
```
let firstName = "Lisa"
let lastName = "Simpson"
let fullName = firstName + " " + lastName

//better way
let fullName2 = `${firstName} ${lastName}`
```

### Case sensitivity - how to avoid it with upper or lower

```
let firstName = "Homer"
let otherFirstName = "Homer";

console.log(`1. ${firstName} equals ${otherFirstName} is: `, firstName.localeCompare(otherFirstName))

otherFirstName = "homer"
console.log(`2. ${firstName} equals ${otherFirstName} is: `, firstName.localeCompare(otherFirstName))
console.log(`3. ${firstName} equals ${otherFirstName} is: `, otherFirstName.localeCompare(firstName))

let a = firstName.toLowerCase()
let b = otherFirstName.toLowerCase()

console.log(`4. ${a} equals ${b} is: `, a.localeCompare(b))

```




### Finding a substring within a string

- find the word 'apple' in 'When an apple fell on Sir Isaac Newton's head'

- split the string and find the word
- string.includes('appple')
- string.indexOf('apple')
- string.indexOf('apple', 5)
- idxOfApple = string.indexOf('apple')
- idxOfSpace = string.indexOf(' ', idxOfApple)
- let word = string.substring(idxOfApple, idxOfSpace-idxOfApple)

### Comparing Strings for equality 
if(string1.localeCompare(string2) == 0)

### Comparing Strings for lexographic order (alphabetical order)
if(string1.localeCompare(string2) > 0)

## Arrays

### basics
- Arrays are similar to strings becaue they are sequence of "things"
- Typical array has the same data types in the array
- Arrays in Javascript keep track of their length (size)
- JavaScript is not bound to the same data type... but 99% you will use it like that

```
let movies = ['The Matrix', 'King Kong', 'Jumanji', 'Secret Life of Pets']
let rankings = [1,5,7,8,10]

console.log(movies[0])   //prints the first movie
console.log(movies[1])   //prints the second movie

console.log(rankings[0])   //prints the first movie
console.log(rankings[1])   //prints the second movie

//...


```
- Arrays in JavaScript have a length property
- So... you can use that to know the right outerlimit
- For example
```
   for(let i=0; i < movies.length; i++){
       console.log(movies[i])
   }
```

### Adding and Removing Items to an array

- push
- pop
- shift
- unshift
- slice
- delete - Do not use this

### Finding Items in an array

- Use a for loop and compare using > < === for numbers or 
  localeCompare for strings
- There is a better way and accepted as best practice
- So don't do that...
- We will cover that when we get to the array methods portion

### Copying an array

- there are several ways
- Method one create a new array and use a for loop with push
- destructuring    
```
let movies = ["The Matrix", "King Kong"]

//Clones the array
let newMovies = [...movies]

//clones the array and adds a new movie at the end
let myLibrary = [...movies, "Bolt"]
```

## passing arrays around
- Arrays can be passed to functions as parameters
- they can also be returned from functions
```
function print(stringList){
    for(let i=0; i < stringList.length; i++){
        console.log(stringList[i])
    }
}

function reverse(stringList){
    let newList = []

    for(let i=stringList.length; i > 0; i--){
        newList.push(stringList[i-1])
    }

    return newList
}

function reversInPlace(stringList){
    for(let i=0; i < stringList/2; i++){
        //swap
        let temp = newList[i]
        let newList[i] = newList[string.length-(i+1)]
    }
}

let movies = ["The Matrix", "King Kong"]
print(movies);
movies = reverse(movies)
print(movies)
reverseInPlace(movies)
print(movies)


```

## Loops

- For loop
- While loop
- Do While Loop
- For in
- For of