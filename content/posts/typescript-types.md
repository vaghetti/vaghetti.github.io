---
title: "A better mental model for reasoning about Typescript types"
date: 2022-07-16T11:16:29-03:00
draft: false
---

I work in a pretty big Typescript code base on my day job.
The one thing I see people struggling the most when learning it is the type system.

Typescript types are rather special in that _they exist during compile time but not during runtime_.
I believe it is a better mental model to think of them as type annotations than proper types like the ones you get in a language like Go or Java.

Let me give an example in Go:

```go
type MyType struct {
	A int
	B int
}

func myFunction(input MyType) {
	bytes, _ := json.Marshal(str)
	fmt.Println(string(bytes))
}
```

In the example above, the Go type system guarantees whatever is passed into your function will have the `A` and `B` fields, they'll both be integers and no other field is going to be there. Anything else simply won't compile.

For comparison, take a look at this similar piece Typescript code:

```typescript
type MyType = {
    a: number;
    b: number;
}

function myFunction(input: MyType){
    console.log(JSON.stringify(input))
}
```

If you're coming into Typescript from a strongly typed language background like me, you might assume these two pieces of code would offer similar guarantees to the `myFunction` function.
That's not always the case in Typescript.
Let's see some interesting things Typescript will allow you to do with this function:

```typescript
myFunction({ a: 1, b: 2 }); // works fine as expected, outputs {"a":1,"b":2}
myFunction({ a: 1, b: 2, c: 3 }); //  Won't compile
myFunction({ a: 1, b: 2, c: 3 } as MyType); // works fine, outputs {"a":1,"b":2,"c":3}
myFunction('im just a string!' as MyType); // Won't compile, thankfully
myFunction(('im just a string!' as unknown) as MyType); // Works fine, outputs "im just a string!", but at this point it is quite obvious we're doing something wrong
```

It really boils down to the behavior of the `as` keyword -- `as` is _not_ a cast.
You can't cast anything in Typescript because there are no Typescript types in runtime!
All `as` is doing is telling the Typescript compiler something like _"relax, compiler, I know what I'm doing."_.

Here's what the compiled Javascript code for the functions above looks like:

```javascript
myFunction({ a: 1, b: 2 }); // works fine as expected, outputs {"a":1,"b":2}
myFunction({ a: 1, b: 2, c: 3 }); //  Won't compile
myFunction({ a: 1, b: 2, c: 3 }); // works fine, outputs {"a":1,"b":2,"c":3}
myFunction('im just a string!'); // Won't compile, thankfully
myFunction('im just a string!'); // Works fine, outputs "im just a string!", but at this point it is quite obvious you're doing something wrong
```

All type annotations are simply removed in runtime.
Typescript is only there until your program is compiled.
After compilation, it is just plain old Javascript again.

Because of this, in Typescript, your type checks are as good as you make them be.
They're not a hard limitation imposed by the compiler like they are in Go.
Typescript types more like hints to the rest of the code.
At any point you can override them or simply use `any`.
They're there to help you write code that works, but they don't change the program that will be actually executed.

This is something that took me some time to wrap my head around -- __It is a better mental model to think of Typescript as a very advanced linter for Javascript with type syntax than to think of it as a proper typed language that gets compiled into Javascript__ -- Most Typescript typing code you write _does not_ get compiled into Javascript, it is just used for compilation checks and then removed. If you want to have real type checks in runtime using Typescript, you have to use [type guards](https://www.typescriptlang.org/docs/handbook/advanced-types.html#user-defined-type-guards)
