Create  Directory

        mkdir goplay

Export Workspace Directory

        export GOPATH=$HOME/goplay

Create Repo Source

         cd goplay
         mkdir - src/bitbucket.org/psarathy

Create A Project Folder

        cd src/bitbucket.org/psarathy
        mkdir hello
        cd hello

Create .go file and fill this with hello world programe

        vim hello.go

Create Packages And Imports

       package main
       import(
         "fmt"
         )
         here we import fmt to use it in the function main

Functions And Variables

            func add(x int, y int)int{
                  return x + y
                   }
        A function can take zero or more arguments.It should have return VALUES
           var c, python, java bool
            The var statement declares a list of variables; as in function argument lists, the type is last.

For And If Statements

                 for ; sum < 1000; {
                               sum += sum
                               }
           The init and post statement are optional in for loops.
           if v := math.Pow(x, n); v < lim {
                                   return v
                               } else {
                            fmt.Printf("%g >= %g\n", v, lim)
                                  }
          Variables declared inside an if short statement are also available inside any of the else blocks.

Structure And Arrays

                       type Vertex struct {
                                        X int
                                        Y int
                                           }
            A struct is a collection of fields.
            The type [n]T is an array of n values of type T.The expression var a [10]int declares a variable a as an array of ten integers.

Creating Slices And Apending Them

     Slices are created with the make function. It works by allocating a zeroed array and returning a slice that refers to that array:
               b := make([]int, 0, 5) // len(b)=0, cap(b)=5
               s = append(s, 0)
    The first parameter s of append is a slice of type T, and the rest are T values to append to the slice.The resulting value of append is a slice containing all the elements of the original slice plus the provided values.

Maps

       Insert or update an element in map m: m[key] = elem
       Retrieve an element: elem = m[key]
       Delete an element: delete(m, key)
       Test that a key is present with a two-value assignment: elem, ok := m[key]

Interface

        A value of interface type can hold any value that implements those methods.
        type Abser interface {
	                         Abs() float64
                            }
              func main() {
	                         var a Abser
	                         f := MyFloat(math.Sqrt2)
	                         a = f  // a MyFloat implements Abser
                         }

Errors

        Functions often return an error value, and calling code should handle errors by testing whether the error equals nil.

                  i, err := strconv.Atoi("42")
                  if err != nil {
                            fmt.Printf("couldn't convert number: %v\n", err)
                            return
                                   }
                            fmt.Println("Converted integer:", i)
                  A nil error denotes success; a non-nil error denotes failure.

Stringers

                  type Stringer interface {
                  String() string
                           }
          A Stringer is a type that can describe itself as a string. The fmt package (and many others) look for this interface to print values.

          
