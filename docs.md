# interfaces

its a blueprint to create classes. similar to classes the interfaces can have both variables and methods
but methods can only be abstract(no body, only method signature)


# composing types
two ways :
1. union
2. genrics

## union
set ur types by using union( | ) operator

``` typescript
type MyBool = true | false;
```

its used in setting states or for a specific case where a literal can be something specific

``` typescript
type Lockstates = "locked" | "unlocked";
```

even in fuctions we can use union to let different types of parameters in

``` typescript
function getLength(obj: string | string[]) {
  return obj.length;
}
```

### typeof
can be used to find the types 

``` typescript
typeof variableName
```
## genrics

providing variable to types. without generics an array can contain anything, with this we can create array with elements of a specific type

``` typescript
type stringArray = Array<string>
type arrayOfObjects = Array<{ name: string }>;
```

# structural type system | duck typing
if two objects have same shape, they are considered to be same type

``` typescript
interface Cordinates {
    x: number,
    y: number,
}

fuction logOrdinates (p : Cordinates){
    console.log(`x:${p.x}, y:${p.y}`)
}

//eventhough "a" is not decalred type "Cordinates". but the TS compares it to Cordinates during type-check.
//they have same shape so the code passes and the method gets executed
const a = {x:84, y :46};
logOrdinates(a);
```
shape matching just requires a subset of the object's fields to match

