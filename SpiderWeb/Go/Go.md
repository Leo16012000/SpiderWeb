# {{date:2024-07-04}}
compiler, static typed, concurrency, garbage collector 
[[Concurrency]]
Goroutine, Channel, deadlock, race condition

[[Structure]]
go.mod dependency management(name,version)
fmt I/O string (format)
--------------------------------------------------

tên export viết hoa
[[Funtion]]
param same type, shortened
multilple results
named return values, "naked" return
type after variable's name

[[Declaration]]
var 1/many, =, :=
int, uint, 8, 64, rune (int32), byte(int8), uintptr(), float32, float64, complex64, complex128
bool ==
string immutable
[[Important]]
default value: number -> 0; bool->false; string -> "", pointer -> nil, nil slice -> length 0, capacity 0
cast: type(value)
const: no :=
[[for]]
init & post optional
[[for, if]] no need (); {}
[[if]] init, also avai in else
[[switch case]] auto break, no need const, switch true,
[[defer]] stack, resource clean
[[pointer]] &, \*p
[[struct]] . access
type Vertex struct {
	X int,
	Y int
}
[[nil]] pointer, slice, map, channel, function, interface
[[null Java]] any var (reference type), not primitives
[[Pointers to structs]] 
```go
p:=&v 
p.X = 3 //íntead of (*p).X = 3 shortened
```
[[Arr]] [size]T
[[Slice]] []T 
dependent on array, mảng nền
```go
primes := [6]{1,2,3,4,5,6}
var s []int = primes[1:4] -> 2,3,4
s[0] = 100 -> primes[1] = 100
```
pointer, length & capacity, capacity only change when starting index change, make function
```go
a := make(int[], 5) -> len(a)=5
b := make(int[],0 ,5) -> len(0), cap(b)=5
```
loop slice, 0->len(slice)
[[Slice literals]] same arr, no fix length
[[Slice default]] = nil; len = cap = 0, no underlying arr
[[map]] map[keyType]valueType
[[2024-07-05]]
:= cannot use outside function
[[2024-07-16]]
why need make?
<mark style="background: #FF5582A6;">range</mark> i,v 
[[2024-07-17]] 
<mark style="background: #FF5582A6;">Access modifier golang</mark>
exported & unexported
[[2024-07-23]]
# Goroutine vs thread
less memory, go keyword
* Go fix thread problem: dynamic allocate(start with 2-4KB instead of 1-2MB; max size could reach to 1 GB) -> use thousands of goroutines
[[OS#Thread]]

\

