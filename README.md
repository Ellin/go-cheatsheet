# go-cheatsheet

## Arrays
### Notes
- Arrays have a fixed length, and the length is a part of its type
### Declaration
```go
var example1 [3]int

var example2 [3]int = [3]int{1, 2, 3}

example3 := [3]int{1, 2, 3}

example4 := [4]string{"Bob", "George", "Sarah", "Helen"}

```

## Slices
### Notes
- Slices act like arrays but can have variable lengths.
- Slices don't actually store any data and acts like a reference, showing a *slice* of the underlying array.
- When slicing, the lower bound is inclusive while the upper bound is exclusive.

### Declaration
```go
someArray := [4]string{"This", "is", "an", "array"}

someSlice1 := someArray[:2] // [This is]  -> a slice of an array [lowerbound : upperbound]

someSlice2 := []string{"This", "is", "a", "slice", "literal"} // like an array but without a specified length

// The make function creates a zeroed array of a specified length & capacity and returns a slice referring to that array
someSlice3 := make([]string, 4, 4) // parameters: type, length, capacity -> [0 0 0 0]
```

## Strings
### Looping over a string
#### Method 1: Loop over the runes
Note: With for range, the i increment (counter) cannot be customized
```go
str := "This is a string!"

for i, char := range str { // type of char is rune
// ...
}
```

#### Method 2: Loop over the bytes of a string
```go
str := "This is a string!"

for i := 0; i < len(str); i++ {
\\ ...
}
```

## Struct
### Define a new struct type
```go
type Person struct {
  Name string
  Age int
  IsAdult bool
} 
```

### Create a struct from the new struct type
```go
// Method 1
person1 := Person{
  Name: "Bob",
  Age: 32,
  IsAdult: true,
}

// Method 2
person1 := Person{"Bob", 32, true} // All field values need filled and in the correct order unlike in Method 1

// Method 3
person1 := Person{}
person1.Name = "Bob"
person2.Age = 32
person1.IsAdult = true

// Method 4
var person1 Person
// Initalize and then set fields later like in Method 3
```

## Resources
- [A Tour of Go](https://go.dev/tour/list)
- [Go by Example](https://gobyexample.com/)
- [Golang101](https://www.golang101.com/)
- [Go Bytes 🎥](https://www.youtube.com/playlist?list=PLQH1-k79HB3_Eh6wxZCDJDO9S9jvIjf14)
