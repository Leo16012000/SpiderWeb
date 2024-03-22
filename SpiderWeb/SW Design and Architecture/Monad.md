originated from a mathematical field called Category Theory
![[Pasted image 20240321092746.png]]
![[Pasted image 20240321102210.png]]
![[Pasted image 20240321102323.png]]
2 basic operations:
- _Unit_: monads represent a type that wraps a given value, and this operation is responsible for ==wrapping the value==. For example, in Java, this operation can accept values from different types just by leveraging generics 
- _Bind_: This operation allows ==transformation== to be ==executed== using the held value and returns a new monad value (a value wrap in the monad type)
- **For _Unit_ operations, Java offers different flavors like _Optional.of()_ and** _**Optional.nullable()**._ As we may imagine, one accepts _null_ values, and the other does not
- **As for the _Bind_ function, Java offers the _Optional.flatMap()_ operation**, introduced in the code examples
Nonetheless, there are some properties that a monad has to obey:

- Left identity: when applying to a monad, it should yield the ==same outcome== as applying the transformation to the held value
- Right identity: when sending a monad transformation (convert the value to a monad), the yield outcome must be the same as wrapping the value in a new monad
- Associativity: when chaining transformations, it ==should not matter how transformations are nested==