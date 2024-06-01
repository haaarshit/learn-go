## Go Lang Notes
### Topics
- <a href="#go-compilation">Go Compilation</a>
- <a href="#memory-mangement-in-go">Memory Management</a>
- <a href="#go-basic-types">Go Types</a>
- <a href="#short-assignment-in-go">Short Assignment Operator in Go</a>
- <a href="#constants-in-go">Go Constants</a>
- <a href="#string-formatters-in-go">String Formatters</a>
- <a href="#conditionals-in-go">Conditionals in Go</a>
- <a href="#functions">Functions</a>
   - <a href="#declaration-syntax-in-go">Declaration Syntax in Go</a>
   - <a href="#passing-variable-by-value">Passing Variable By Value</a>
   - <a href="#multiple-return-values">Multiple return values</a>
   - <a href="#named-return-values">Named return values</a>

- <a href="#structs-in-go">Structs in Go</a>
  - <a href="#initiate-a-struct">Initiate a struct</a>
  - <a href="#anonymous-structs-in-go">Anonymous Structs in Go</a>
    - <a href="#nested-anonymous-struct">Nested Anonymous Structs in Go</a>
  - <a href="#embedded-structs">Embedded Structs in Go</a>
  - <a href="#struct-methods-in-go">Struct Methods in Go</a>
- <a href="#interface-in-go">Interface in Go</a>
  - <a href="#interface-implementation">Interface Implementation</a>
  - <a href="#multiple-interfaces">Multiple Interface in Go</a>
  - <a href="#type-assertions-in-go">Type Assertions in Go</a>
  - <a href="#type-switches">Type Switches</a>
  - <a href="#clean-interfaces">Clean Interfaces</a>
- <a href="#errors-in-go">Errors in Go</a>
  - <a href="#error-interface">Errors Interface in Go</a>
  - <a href="#the-errors-package">Errors Package in Go</a>
- <a href="#loops-in-go">Loops in Go</a>
  - <a href="#there-is-no-while-loop-in-go">While Loops in Go</a>
  - <a href="#modulo-operator-in-go-lang">Modulo operator </a>
  - <a href="#or--and-operator">AND & OR operator </a>
- <a href="#arrays-in-go">Array in GO</a>
  - <a href="#slices-in-array">Slices in GO</a>
  - <a href="#make-function-to-create-slice">Make function to create slice</a>
  - <a href="#length-function">Lenght function </a>
  - <a href="#capacity-function"> Capacity function</a>
  - <a href="#variadic-functions">Variadic function</a>
  - <a href="#spread-operator">Spread Operator</a>
  - <a href="#append-function">Append function</a>
  - <a href="#slice-of-slices">Slice of Slices</a>
  - <a href="#range">Range</a>
- <a href="#maps-in-go">Maps in Go</a>
  - <a href="#nested-maps">Nested Maps in Go</a>
- <a href="#advanced-functions">Advanced Functions</a>
  - <a href="#first-class-function-and-higher-order-function">First class and Higher order function</a>
  - <a href="#closures">Closures</a>
  - <a href="#anonymous-functions">Anonymous functions</a>
- <a href="#pointers">Pointers in Go</a>
- <a href="#package-naming">Package Naming</a>
  - <a href="#naming-convention">Naming Convention</a>
  - <a href="#one-package--directory">One Package / Dirctory</a>
  - <a href="#go-module">Go Module</a>
  - <a href="#custom-package-in-go">Custom package in Go</a>
- <a href="#concurrency--parallelism-in-go">Concurrency and Parallelism in Go</a>
  - <a href="#concurrency--parallelism-vs-synchronoussequential">Concurrency and Parallelism v/s Synchronous / Sequential</a>
    - <a href="#what-is-conurrency">What is Concurrency </a>
    - <a href="#how-does-concurrency-work-in-go">How does Concurrency work in Go </a>
    - <a href="#what-is-a-goroutine">What is a goroutine? </a>
- <a href="#channels">Channels in Go </a>
  - <a href="#create-channel-in-go">Create Channel in Go</a>
  - <a href="#channel-types-and-values">Create Types in Go</a>
  - <a href="#channel-operations">Channel Operations</a>
  - <a href="#range-keyword-on-channel">Range keyword on Channels</a>
  - <a href="#select-statement-in-channel">Select statment in Channels</a>
- <a href="#mutexes-in-go">Mutexes in Go</a>
  - <a href="#rw-mutex">RWMutex in Go</a>
- <a href="#generics-in-go">Generics in Go</a>
  - <a href="#constraints">Constraints</a>
    - <a href="#interface-type-list">Interface Type List</a>
    - <a href="#parametric-constraints">Parametric Constraints</a>


## Go compilation
.go file => go build => .exe file

Now you can run that .exe file anywhere without installing go on that particular machine
 
How it will look like in other languges like python

main.py => send to friend => run command python main.py
They need to install python on their machine

**In go it looks like**

main.go => compile => main.exe 
now run main.exe anywhere without the need of go installation

#### Memory Mangement in Go

In Rust/C memory management is manual.
In java it's automatic. Java uses Garbage Collector and JVM which means Java will use extra memory.

**GO** is somewhere between both, It also automated but it does not have JVM like java, Rather you get a binary or exe program, every binary that get build has runtime within it.



#### Go Basic Types

- Integer (int)
- Unsigned Integer (uint) 
- Float (float)
- Complex Number 
- Byte (byte)
- Boolean (bool)

```go
package main
import ("fmt")

func main(){
   var intval int  = 1
   var floatval float32 = 1.2
   var boolval bool = true
   var stringval string = "name"

   fmt.Printf("%v %f %v %q\n",intval,floatval,boolval,stringval)
}

```

## Short assignment in GO

Inside a function, the `:=` short assignment statement can be used in place of `var` declaration. The `:=` operator infers the new type of variable based on the value.

```go
var empty string 
```
is same as
```go
empty := ""
```

Same program using short assignment operator
```go
package main

import ("fmt")

func main(){
   intval  := 1
   floatval  := 1.2
   boolval  := true
   stringval  := "name"

   fmt.Printf("%v %f %v %q\n",intval,floatval,boolval,stringval)

}
```

#### Print type of a variable
We can use %T formatter to print the type of a variable
```go
   intval  := 1
   fmt.Printf("Type of varibale is %T\n",intval)
```

#### Declare multiple value on the same line
```go
a,b,c := 9,29,92
```

## Constants in Go 

In go every constant value must be know at compile time.
```go
  const name = "Harshit"
```

## String formatters in Go
Go offers excellent support for string formatting in the printf tradition

```go
 msg := "random message"
 fmt.Printf("The message is %v\n",msg)
```

#### Printf v/s Sprintf
We saw Printf formats the string and print it unlike Sprintf which formats the string and return it instead of printing it

```go
name := "Your name"
msg := fmt.Sprintf("The name is  %v",name)
```


## Conditionals in Go
`if` statement in Go does not use parentheses around conditions
```go
  x := 1
  if x > 0{
      fmt.Println("Hello")
   }
```

`if` `else` `else if` conditionals
```go
   x := 1

   if x > 1{
      fmt.Println("Hello")
   } else if x == 1 {
      fmt.Println("Hii")
   } else {
      fmt.Println("Why negative")
   }

```
There is another way to use variable in conditions if varibale is just only used for if statement.
We can do :
```go
if length:=getLength(email); length<1{
   fmt.Println("Email is  invalid")
}
```

# Functions
Functions in Go can take zero or more arguments.
To make Go code easier to read, the variable type comes after the variable name
```go
func sub(x int,y int) int {
   return x - y
}
```
If multiple arguments of the same type, the type only need to be declared after the last one
```go
func sub(x,y int) int {
   return x - y
}
```

## Declaration Syntax in Go
Go's declaration are clear, you just read them left to right, just like you would in English
```go
x int // x is an integer
p *int // p is a pointer to integer
a [3]int // a is an array of integer
```

## Passing Variable by Value

Varibles in Go are passed by value(except for few data  types which we will cover later)."Pass by value means when a variable is passed to a function it recives a copy of the variable. The function will not mutate the caller's data.

```go
func main(){
  x := 1
  fmt.Println(x) // will print 1
  increment(x)
  fmt.Println(x) // will print 1 again because actual value of x is not mutated, increment func got the copy of x
}

func increment(x int){
   x++
}

```

## Multiple return values
Functions in Go can have multiple return values. That caller may doesn't care about. We can explicitly ignore variable by using an underscore: `_`
```go
func main(){ 
  x,_ := point() // ignoring second return value
  fmt.Printf("x -> %v\n",x)
}

// function returning two int values
func point()(int,int){
   return 3,6
}
```
Because Go does not allow us to have unused varibale and a function may return multiple values, we need to have a way to ignore those variables

## Named return values
We can name the return values in Go.
**A return statement without argument returns named return value** 
It also called `Implicit` return.

```go
// function with named return value (x and y)
fun getCoords()(x,y int){ 
   return // returns x and y as they are the named return value
}
```

# Structs in Go
We use structs in Go to represent structured data. It's often convenient to group different types of variable together. For example, If we want to represent a car we could do the following.

```go
type car struct {
   Make string
   Model string
   Height int
   Width int
}
```

### Initiate a struct
You can intiate a struct and access it's field using  `.` operator.
```go
   carInfo := car{}
   carInfo.Make = "BMW"
   carInfo.Model = "M4"
   carInfo.Height = 124
   carInfo.Width = 27
```
or
```go
   carInfo := car{"BMW","M4",124,27}
```

### Anonymous Structs in Go
Anonymous structs is just like a normal struct, but it is defined without a name and therefore can't be reffered elsewhere in the code.
```go
 mcar := struct{
   Make string
   Model string
  }{
   Make: "BMW",
   Model: "M4",
  }
```
#### Nested Anonymous Struct
You can even nest anonymous structs as field within other structs:

```go
type car struct {
   Make string
   Model string
   Height int
   Width int
   // Wheel is a field containing an anonymous struct
   Wheel struct{
      Radius int
      Material string
   }
}
```

### Embedded Structs

Embedded structs provide kind of data only inheritance that can be useful at times. Keep in mind go doesn't support classes and inheritance in the complete sense, embedded structs are just way to elevate and share fields between struct definitions.

In embedded stuck we take a struct and embed into another struct
```go
type car struct{
   Make string
   Model string
}

type truck struct{
   car // car is embedded so truct struct now also contains all of fields of the car struct
   besize int
}
```
In the embedded stuct if we want to access the field of car via a truct struct rather that doing `truck.car.Model` we will use `truct.Model`.
Fields of `car` type is becoming top level fields of `truck` type.
```go

func main(){ 
   truckInfo := truck{}
   truckInfo.bedsize = 81
   truckInfo.Model = "Truck Model"
   truckInfo.Make = "Maker"
   fmt.Println(
      truckInfo.bedsize,
      truckInfo.Model,
      truckInfo.Make 
   )
}
type car struct {
   Make string
   Model string
}
type truck struct{
   bedsize int
   car
}
```
### Struct Methods in Go
While Go is not object oriented, it does support methods can be defined on structs. 
Methods are just functions that have a receiver. A receiver is special parameter that sytactically goes before the name of the function.
```go
type rect struct{
   width int
   height int
}

// the area function has a reciver of struct type
func (r rect) area() int{
   return r.width * r.height
}

r := rect{
   width:4,
   height:10
}

fmt.Println(r.area())
```

# Interface in Go
Interfaces are collections of method signatures. A type "implements" an interface if it has all of the methods of the given interface defined on it.

In following example, a "shape" must be able to return its area and perimeter. Both `rect` and `circle` fulfill the interface.

Using interface you can pass multiple type of argument to a function for example if a function takes a shape interface as argument so you can pass different type of arguments to it which impliments that shape interface (example below).

```go
package main
import (
   "fmt"
   "math"
)

func main(){
   r := rect{2,4}
   c := circle{3}

   // here function 'val' taking argument of two different type because its argument is interface and both type has implimented interface
   val(r)
   val(c)
}

type shape interface{
   area() float64
   perimeter() float64
}

type rect struct{
   width,height float64
}

// shape interface implimentation by rect type
func (r rect) area() float64{
   return r.width * r.height
} 

func (r rect) perimeter() float64{
   return 2*r.width+ 2*r.height
}

type circle struct{
   radius float64
}

// shape interface implimentation by cirlce type
func (c circle) area() float64{
   return math.Pi*c.radius*c.radius
} 

func (c circle) perimeter() float64{
   return 2*math.Pi*c.radius
}

// val function taking shape interface as argument
func val(i shape){
   fmt.Println("Area of shape is ",i.area())
   fmt.Println("Perimter of shape is ",i.perimeter())
}
```
### Interface implementation
A type implements an interface by implementing its methods. Unlike in many other languages , there is no explicit declaration of intent, there is no "implements" keyword.

**Interfaces are implemented implicitly**. Implicit interfaces `decouple` the defination of an interface from it's implimentation. 

### Multiple Interfaces
A type can implement any number of interfaces in Go. For Example, the empty interface,`interface{}`, is always implemented by every type because it has no requirement

### Type Assertions in Go
When working with interfaces in Go, every once-in-awhile you'll need access to the underlying type of an interface value. You can cast an iterface of its underlying type using _type assertion._ 

_Type assertions in Go help access the underlying type of an interface and remove ambiguity from an interface variable._

```go
type shape interface{
   area() float64
}

type circle struct{
   radius float64
}
// "c" is the new circle cast from "s" which is an intance of shape(which we don't know wheather a circle or not)
// "ok" is a bool that is true if s was a circle or false if s isn't a circle
c, ok := s.(circle)
```

### Type Switches

A type switch is similar to regular switch statement, but the cases specify `type` instaead if values.

```go
func printNumericValue(num interfact{}){
   switch v := num.(type)
   case int:
       fmt.Println("%T\n",v)
   case string:
       fmt.Println("%T\n",v)
   default:
       fmt.Println("%T\n",v)
}
```

### Clean Interfaces
Writing clean Interfaces is `hard`. Anytime you're dealing with abstraction in code, the simple can become comple very quickly if you're not careful. 

Some rules of thumb for keeping interface clean.

#### 1. Keep Interfaces Small
Interfaces are meant to define the minimal behaviour necessary to accurately represent an idea or concept.


#### 2. Interfaces shoud have no knowledge of satisfying type 

An interface should define what is necessary for other types to classify as a member of that interface. They shouldn't be aware of any types that happens to satisfy the interface at design time

#### 3. Interfaces are not classess

Interfaces are not classess, they define function signature not underlying behaviour.


# Errors in Go

Error handling in Go is slightly different from the languages like JS,Java or Python which uses `try-catch` paradigm to handle error here is the comparission between JS and Go code :

JS:-
```js
function main(){
   try{
      const user = getUser()
      // use user here
   }catch (err){
      console.log(err)
   }
}
```
Go:-
```go
func main(){
   user, err := getUser()
   if err != nil{
      fmt.Println(err)
      return
   }
   // use user here
}
```

Go make you hyperaware of every error and makes sure that you are handling all the errors.

### Error Interface

Go program express errors withh `error` values. An Error is any type that implements the simple built-in error interface.

```go
type error interface{
   Error() string
}
```
Because errors are just inerfaces , you can build your own custom types that implement the `error` interface. Here's an example of a `useError` struct that implements the `error` interface:

```go
type useError struct{
   name string
}

func (e useError) Error() string{
   return fmt.Sprintf("%v has a problem with his/her account",e.name)
}
```

It can be uses as an error:
```go
func sendSMS(msg,username string) error{
   if !canSendToUser(username) {
      return useError{name:username}
   }
   /*
   ...
   */
}
```

Example :-
```go
func main(){
   x,y:= 20,0
   ans,err := divide(x,y)
   if err != nil{
      fmt.Println(err)
      }else{
         fmt.Println(ans)
   }
}
// divide function
func divide(x,y int) (int,error){
   if(y == 0){
      return 0, useError{message:"Divisor cant be zero"}
   } else{
      return x/y,nil
   }
}
// custom error type
type useError struct{
   message string
}
// useError implements error interface
func (e useError) Error() string{
   return fmt.Sprintf("Error message is %v",e.message)
}
```

### The Errors Package

The Go standard library provides an `errors` package  that makes it easy to deal with errors

```go
var err error = errors.new("Something went wrong")
```

# Loops in Go

Basic loop in Go is written in standard C-like syntax:

```go
for INITIAL; CONDITION; AFTER{
   // do something
}
```

`INITIAL` is run once at the beginning of the loop and can create variables within the scope of the loop.

`CONDITION` is checked before each iteration. If the condition doesn't pass then the loop breaks.

`AFTER` os run after each iteration.

```go
for i:=0; i<10; i++{
   fmt.Println(i)
} 
```

### There is no While loop in Go

As Go allows you for the omission of section of a `for` loop, a while loop i just a `for` loop that has a Condition.

```go
for CONDITION{
   // do something
}
```
```go
i:=0
for i<10{
   fmt.Println("hello")
   i++
}
```
**Infinite loop in Go**
```go
 for {
   fmt.Println("hello")
   i++
  }
```

### Modulo(%) operator in Go lang
Modulo operator `%` returns the remainder of a devision operation.

For example on dividing 5 by 2 the remainder will be 1.

```go
modval := 5%2
fmt.Println(modval) // prints 1
ans := 5/2
fmt.Println(ans) // prints 2
```

### OR & AND operator

OR operator: returns true if any of operand is true otherwise returns false
```go
true || false // true
true || true // true
false || false // false
```
AND operator: returns true if both of operand is true
```go
true && false // false
true && true // true
false || false // false
```

# Arrays in Go
Arrays are used to store multiple values of the same type in a single variable, instead of declaring separate variables for each value.
For example storing three integers will require three different variable like:
```go
var x int
var y int
var x int
```
Instead we can store all three variable in single array variable.
Decalare array of interges of size 3
```go
var arr [3]int // array of 3 integers
```
or instead you can initialize the array
```go
arr := [3]int{1,4,6}
```
**Remember in Go arrays are of fixed size unlike js where we can dynamically add or remove element**

To access the elements of array we use indexs which start from 0 to size of array - 1.
```go
arr := [3]int{1,4,6}
fmt.Println(arr[0]) // prints 1
fmt.Println(arr[1]) // prints 4
fmt.Println(arr[2]) // prints 6
```

### Slices in array
An array has a fixed size. A slice, on the other hand, is a dynamically-sized, flexible view into the elements of an array. In practice, slices are much more common than arrays.
A slice is formed by specifying two indices, a low and high bound seprated by colon
```go
a[low:high]
```
```go
func main() {
	primes := [6]int{2, 3, 5, 7, 11, 13}

	var s []int = primes[1:4]
	fmt.Println(s)
}
```
**Slices are built on top of array**, slices hold `refrences` to an underlying array and if assing one slice to other they both refrence to same array. If a function takes a slice argument, changes it makes to the elements of the slice _will be visible to the caller_, analogous to passing `a pointer` to the underlying array.
```go
func main(){
   arr := [4]int{1,3,5,8}
   s := arr[:] 
   changeVal(s)
   fmt.Println("this is slice: ",s)
   fmt.Println("this is arr: ",arr) // changeVal function will also change the value of arr as slice s refrence to array arr
}

func changeVal( arr []int){
   arr[0] = 199
}
```
### MAKE function to create slice
We can create a new slice using `make` function:
```go
// func make([]T,len,cap) []T
mySlice := make([]int,5,10) // slice of type int with size 5 and capacity 10 
mySlice := make([]int,5) // slice of type int with size 5 and without capacity 
```
Slices creates with `make` will be filled with zero value of the type.

If we want to create a slice with a specific set of values, we can use a slice literal:
```go
mySlice := []string{"I","Love","Golang"}
```
**Here we don't have size 3 inside array bracker if we did, we'd have an array instead of slice**

### LENGTH function 
The length of a slice is number of elements it contains. It is accessed using built-in `len()` function
```go
mySlice := []string{"I","Love","Golang"}
fmt.Println(len(mySlice)) // 3
```
### CAPACITY function
Capacity of a slice is the number of elements in the underlying array, counting from the first element in the slice. It is accessed using built-in `cap()` function:
```go
mySlice := []string{"I","Love","Golang"}
fmt.Println(cap(mySlice)) // 3
```

### VARIADIC Functions

Variadic functions receives the variable arguments as a slice.

```go
func main(){
   total := sum(1,2,4,5,7)
   fmt.Println(total)
}
// variadic function
func sum(num ... int) int{
   ans := 0
   for i :=0 ; i < len(num);i++{
      ans+=num[i]
   }
   return ans
}
```

### SPREAD Operator

Spread operator allows us to pass a slice into a variadic function. The spread operator consists of three dots following the slice in the function call.
```go
func printString(strings ...string){
   for i := 0; i< len(strings);i++{
      fmt.Println(strings[i])
   }
}

func main(){
   names := []string{"Alpha","Bravo","Charlie"}
   printStrings(names...)
}
``` 

### APPEND function

The built in append function is used to dynamically add elements to a slice:

```go
func append(slice []type,elem ... type)
```
Notice that `append()` is variadic, the following are all valid:
```go
slice = append(slice,onThing)
slice = append(slice,firstthing,secondthing)
slice = append(slice,anotherSlice)
```

### Slice of Slices

Slices can hold other slices, effectively creating a `matrix` or 2D slice.

```go
rows := [][]int{}
```

```go
func main(){
   matrix := createMatrix(10,10)
   for i := 0; i < len(matrix); i++{
      fmt.Println(matrix[i])
   }
}

// program to create a 2d slice
func createMatrix(rows ,cols int) [][]int{
   matrix := make([][]int,0)
   for i:=0; i<rows;i++{
      row := make([]int,0)
      for j:=0; j<cols;j++{
         row = append(row,i*j)
      }
      matrix = append(matrix,row)
   }
   return matrix
}
```

**The `append()` function changes the underlying array of its parameter AND returns new slice. This means that using `append()` on anything other than itself is usually a BAD idea** 
```go
// don't do this
someSlice = append(otherSlice,element)
```

### RANGE

Go provides syntactic sugar to iterate easily over slice:
```go
for INDEX,ELEMENT := range SLICE{
}
``` 

# MAPS in Go

Maps in go are similar to JS objects, Python dictonaries and Ruby and Java's hashmaps. Maps are a data structure that provide key->value mapping.

The zero value of a map is `nil`.

We can create a map by using a literal or by using the `make()` function:
```go
ages := make(map[string]int)
```

```go
   ages := map[string]int{
      "John":32,
      "James":29,
   }

   fmt.Println(ages["John"])
   fmt.Println(ages["James"])
```

**Using struct as key**
```go

func main(){
   
   hits := make(map[key]int)

   hits[key{"/doc","val"}] = 1
   hits[key{"/lib","val"}] = 2

   fmt.Println(hits[key{"/doc","val"}])
}

type key struct{
   path,value string
}
```

## Nested Maps

Maps can contain maps, creating a nested structure. For example:

```go
map[string]map[string]int // mapping string to a map string -> [string -> int]
```

```go
  // nested map
   nested := map[string]map[string]int{
      "first":{
         "value":192,
      },
   }
   nested["second"] =  map[string]int{"value":13} // 
   fmt.Println("first:[value:",nested["first"]["value"],"]")
   fmt.Println("second:[value:",nested["second"]["value"],"]")
```

# Advanced Functions

**Higher order Functions** are the functions that take another function as argument.
```go
func add(x,y int) int{
   return x + y
}

// aggregate applies the given math function tpo the first 3 inputs
func aggregate(a,b,c int,arithmetic func(int,int) int) int{
   return arthimetic(arithmetic(a,b),c)
}

func main(){
   fmt.Println(aggregate(2,3,4,add))
}
```

### First class function and Higher order function
Go has the concept of **First-class functions**, which means functions can be assigned to variables, passed as arguments to other functions, and returned as values from other functions.
```go
func add(x int, y int) int {
    return x + y
}

func main() {
    // Assign the function to a variable
    addFunc := add
    fmt.Println(addFunc(2, 3)) // Output: 5
}
```

**Higher-order functions** in Golang are functions that either accept a function as an argument or return a function as output. 

```go
func getAreaFunc() func(int, int) int {
    return func(x, y int) int {
        return x * y
    }
}
func print(x, y int, area func(int, int) int) {
    fmt.Printf("Area is: %d\n", area(x, y))
}

func main() {
    areaF := getAreaFunc()
    print(3, 4, areaF)
}
```

## Currying

Function currying is the practice of writing a function that takes a function(or functions) as input, and returns a new function.
**So currying is a process of disassembling existing multi-arg function into chain of one-arg functions.**

```go
func curry(f func(int, int) int, a int) func(int) int {
	return func(b int) int {
		return f(a, b)
	}
}
```

## Closures

A closure is a function that refrences variable from outsite its own function body. The function may access and assign to the refrenced variables.

In this example, the `concatter()` function returns a function that has refrence to an _enclosed_ `doc` value.

```go
func concatter() func(string) string{
   doc := ""
   return func(word string) string{
      doc += word + ""
      return doc
   }
}
```

## Anonymous functions

Anonymous functions are the functions with no name.

```go
func doMath(f func(int) int, x int)int{
   return f(x)
}

func main(){
   x := doMath(func(x int) int{ // anonymous function
      return x*x
   }, 5)
   fmt.Println(x) // 25
}
```

# Pointers

Go has pointers. A pointer holds the memory address of a value. In short pointers are the varibale that holds the address of another variable.

```go
var p *int
i := 42
p = &i
fmt.Println(*p)
```

# Package Naming

## Naming Convention

By `convention`, a package's name is the same as the last element of its import path. For instance the `math/rand` comprises files that begin with:
```go
package rand
```
That said, package names aren't required to match their import path. For example, I could write a new package with the path `github.com/username/rand` and name the package random:
```go
package random
```
While the above is possible, it is dicouraged for the sake of consistency.

## One Package / Directory
A directory of Go code can have at most one package. All `.go` files in a single directory must all belong to the same package. If they don't an error will be thrown by the compiler. This is true for main and library package alike.

## Go module

**A GO REPOSITORY TYPICALLY CONTAINS ONLY ONE MODULE, LOCATED AT THE ROOT OF THE REPOSITORY**

A file named `go.mod` at the root og a project declares the module. It contains:
- The module path
- The version of the Go language your project requires
- Optionally, any external package dependencies your project has

The module path is just the import path prefix for all packages within the module. Here's an example of a `go.mod` file:
 
```go
module github.com/devprofile/exampleproject

go 1.20

require github.com/google/examplepackage v1.3.0
```

## Custom Package in Go

Let's write a package to import and use

Create a directory :
```bash
mkdir mystrings
cd mystrings
```

initialize a module :
```bash
go mod init {REMOTE}/{USERNAME}/mystrings
```
Then create a new file `mystring.go` in that directory and paste the following code.
```go
package mystrings

func Reverse(s string) string{
   result := ""
   for _,v := range s{
      result = string(v) + result
   }
   return result
}
``` 

**NOTE: Lowercase names aren't exported for external use form the package**

**Replace a url with local file system in you `go.mod` file**
```go
replace github.com/devid/packagename v0.0.0 => ../localfilename 
```

# Concurrency / Parallelism in Go
## Concurrency / Parallelism vs Synchronous/Sequential
Concurrency is a core feature, and Goroutines provide a lightweight way to achieve asynchronous and parallel execution **In summary, concurrency is about managing and overlapping the execution of multiple tasks, often on a single processor, to enhance efficiency and responsiveness.**. Synchronous: Unlike concurrency in synchronous one task executes at a time, the next starts when the current is done.
### What is Conurrency 
Concurreny is ability to perform multiple tasks at the same time. Typically, our code is executed on line at a time, one after the other. This is called `Sequential Execution or Synchronous Execution`

### How does Concurrency work in Go
Go was designed to be conurrent, which is a trait `fairly` unique to Go. It excels at performing many tasks simultaniously safely using a simple syntax.

Concurrency is as simple as using `go` keyword when calling a function:
```go
go doSomething()
```
In the example code `doSomething()` will be executed cocurrently with the rest of the code in the function. Th `go` keyword is used to span a new <a href="#what-is-a-goroutine">goroutine</a>

## What is a goroutine?

A goroutine is a lightweight execution thread in the Go programming language and a function that executes concurrently with the rest of the program.

Goroutines are incredibly cheap when compared to traditional threads as the overhead of creating a goroutine is very low. Therefore, they are widely used in Go for concurrent programming.

To invoke a function as a goroutine, use the go keyword

**When we use `go` keyword we are not able to capture any return value from that function call** Because we are moving on rather than waiting for the function to response.

# Channels

Channel is an important built-in feature in Go. **Channels are a way to communicate  between different goroutines and send data to each other**. It is one of the features that makes Go unique. Along with another unique feature, goroutine, channel makes concurrent programming convenient, fun and lowers the difficulties of concurrent programming.

One suggestion for concurrent programming is don't `communicate by sharing memory`,let them `share memory by communicating` (through channels). 

Communicating by sharing memory and sharing memory by communicating are two programming manners in concurrent programming. When goroutines communicate by sharing memory, we use traditional concurrency synchronization techniques, such as mutex locks, to protect the shared memory to prevent data races. **We can use channels to implement sharing memory by communicating**.

**We can view a channel as an internal FIFO (first in, first out) queue within a program. Some goroutines send values to the queue (the channel) and some other goroutines receive values from the queue.**

## Channel Types and Values
Channel types can be bi-directional or single-directional. Assume T is an arbitrary type,

`chan T` denotes a bidirectional channel type. Compilers allow both receiving values from and sending values to bidirectional channels.

`chan<- T` denotes a send-only channel type. Compilers don't allow receiving values from send-only channels.

`<-chan T` denotes a receive-only channel type. Compilers don't allow sending values to receive-only channels.

## Create Channel in Go
In Go, we use the make() function to create a channel. For example,
```go
channelName := make(chan int)
```
Here
- channelName - name of the channel
- (chan int) - indicates that the channel is of integer type

## Channel Operations
**1. Send data to the channel**

The syntax to send data to the channel is
```go
channelName <- data
```
```go
// send integer data to channel
number <- 15
// send string data
message <- "Learning Go Channel"
```
**2. Receive data from the channel**

The syntax to receive data from the channel is:
```go
<- channelName
```
```go
<- number
<- message
```
**Channel Operation Example**

```go
package main
import "fmt"

func main() {
  // create channel
  number := make(chan int)
  message := make(chan string)

  // function call with goroutine
  go channelData(number, message)

  // retrieve channel data
  fmt.Println("Channel Data:", <-number)
  fmt.Println("Channel Data:", <-message)
}

func channelData(number chan int, message chan string) {
  // send data into channel
  number <- 15
  message <- "Learning Go channel"
}
```

### RANGE keyword on channel

Similar to slices and maps, channels can be ranged over.
```go
for item := range ch{
   // item is the next value received from the channel
}
```
### SELECT statement in channel
Sometimes we have a single goroutine listening to multiple channels and want to process data in the order it comes through each channel.

A `select` statement is used to listen to multiple channels at the same time. It is similar to a `switch` statement but for channels.

```go
select {
   case i,ok := <- chInt:
       fmt.Println(i)
   case s,ok := <- chString:
       fmt.Println(s)
}
```

# Mutexes in Go
Mutexes allow you to `lock` access to data. This allow us which goroutine can access certain data at which time.

**A Mutex is used to provide a locking mechanism to ensure that only one Goroutine is running the critical section of code at any point in time to prevent race conditions(two goroutines running to access the same resource) from happening.**

Go's standard library provides a built-in implementation of a mutex with the `sync.Mutex` type and its two methods:
- .Lock()
- .Unlock()

We can protect a block of code by surrounding it with a call to `Lock` and `Unlock`.

Its good practice to structure the protected code within a function so that `defer` can be used to ensure that we never forget to unlock the mutex.

```go
func protected(){

   mux.Lock()
   defer mux.Unlock()

}
```
**Any code present between a call to Lock and Unlock will be executed by only one Goroutine.**
```go
mux.Lock() 
x = x + 1 // this statement be executed
          // by only one Goroutine 
          // at any point of time  
mux.Unlock()
```
## RW Mutex
Standard library also exposes the `sync.RWMutex`

Maps are safe for concurrent read access, just not concurrent read/write or write/write access. A read/write mutex allows all the readers to access the map at the same time, but a writer will lock out everyone else.

**An RWMutex (Read-Write Mutex) is a reader/writer mutual exclusion lock that allows concurrent read-only access while maintaining exclusive access for writes.**

In addition to these methods
- .Lock()
- .Unlock()

The `sync.RWMutex` also has these methods:
- RLock()
- RUnlock()

**So How many writers can access a RWMutex at once?**
- Answer is 1

**How many readers can access a RWMutex at once?**
- Answer is infinite

**No one can use Mutex if its being written**

# Generics in Go

As Go does not support object oriented programming, that meant for long time that Go code could't easily be reused in many circumstances. For example, some code split a slice into equal 2 parts. The code that splits the slice doesn't really care about the values forteds stored in the slice. But in Go we would need to type same code multiple time for different types. Why is un-DRY(Don't repeat yourself to do) thing to do.

**Type Parameter**
Put simply, generics allow us to use variable to refer to specific types. This is an amazing feature because it allows us to write abstract functions that drastically reduce code duplication.

```go
func splitSlice[T any](s []T) ([]T,[]T){
   mid := len(s)/2
   return s[:mid],s[mid:]
}
```
In this example above , `T` is the name of the type parameter for the `splitAnySlice` function, and we've said that it must match `any` constraint, which means it can be anything.
```go
	sl1 := []int{1,3,54,6,7,8}
	sl2 := []string{"he","her","they","their","when","who"}
	fmt.Println(splitSlice(sl1)) 
	fmt.Println(splitSlice(sl2)) 
```
## Constraints
Sometimes you need the logic in your generic function to know something about the types it operatos on. In above example we used `any` **constraint** because we didn't need to know anything about the types in the slice.

**A type constraint is an interface that defines the set of permissible type arguments for the respective type parameter and controls the opera tions supported by values of that type parameter**

`OR`

**Constraints are essentially rules or conditions that a type must satisfy to be used as a type parameter in a generic function or type**


**Creating a custom Constraint**

A `concat` function takes a slice  values and concates the values into a string.
```go
type stringer interface{
   String() string
}

func concat()[T stringer](val []T) string{
   result := ""
   for _,v := range val{
      resule += v.String()
   }
   return result  
}
```

### Interface type list
 
When generics was realeased, a new way of writing interfaces was also released at the same time!

We can now simply list a bunch of types to get a new interface/contraints.
```go
type Ordered interface{
   ~int | ~int8 | ~int16 | ~int32 | ~int64 |
        | ~uint | ~uint8 | ~uint16 | ~uint32 | ~uint64 | ~uintptr |
        ~float32 | ~float64 |
        ~string
}
```
**The Ordered interface is a constraint that specifies the types that are allowed.**

Example :-
```go
package main

import (
	"fmt"
)

// Define the Ordered interface
type Ordered interface {
	~int | ~int8 | ~int16 | ~int32 | ~int64 |
	~uint | ~uint8 | ~uint16 | ~uint32 | ~uint64 | ~uintptr |
	~float32 | ~float64 |
	~string
}

// Min function to find the minimum value in a slice of Ordered types
func Min[T Ordered](slice []T) T {
	if len(slice) == 0 {
		panic("cannot find the minimum of an empty slice")
	}
	min := slice[0]
	for _, v := range slice {
		if v < min {
			min = v
		}
	}
	return min
}

func main() {
	ints := []int{4, 2, 3, 1}
	floats := []float64{4.4, 2.2, 3.3, 1.1}
	strings := []string{"delta", "alpha", "charlie", "bravo"}

	fmt.Println("Min of ints:", Min(ints))
	fmt.Println("Min of floats:", Min(floats))
	fmt.Println("Min of strings:", Min(strings))
}

```

### Parametric Constraints
Your interface definitions, which can later be used as constraints, can accept type parameters as well.

```go
type store[P product] interface{
   Sell(P)
}
type product interface{
   Price() float64
   Name() float64
}

```
