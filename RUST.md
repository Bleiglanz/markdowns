















# Rust

## General stuff

Tools: rustc, rustup, cargo, rustfmt,...

Rust uses snake_case_format

Rust uses 4-space indent

Create a new runable with `cargo new --bin name_of_prj`

Create a new library with `cargo new --lib name_of_lib`

If directory already exists, use `init` instead of `new`

`rustup update; cargo update`, important if nightly is used

`cargo run` builds an runs a binary app

shortcut `cargo b r t`...

Rust uses a simple directory layout (source files are in `src`)

Configuration is in `Cargo.toml`

Command line arguments in `std::env::args`

Results are `OK(value)` or `Err(e)`, just use `unwrap()` to panic if something is wrong

To bring names into scope, use `use`

## Variables

`let variable_name:Type = ...` is the standard way to bind a name to a value

`let mut variable_name:Type = ...` creates something mutable

## Expressions

`while` as usual

`for x in iter` as usual, for arrays create an iterator with `.iter()`

`if cond {} else {}` has no `(...)` for condition, it is an *expression* with a value

`loop` is infinite, has to have a `break`

blocks `{}` are values, the last expression should have no `;`

statements are terminated by `;`, they don't have a value

## Functions

```
fn tolstoi (arg:Type, arg2:Type) -> ResultType {

}
```
typically the last expression isn't followed by an `;`, in this case it is the result.
Think about the last semicolon in the function body!

## Macros

can be recognized by `!` at the end of the name `println!`, `assert!`

## Attributes=Annotations
```
#[test] 
fn test_this(){
    assert_eq!(1,1);
}
```
can be used, in this case a unit test (typically in the same source)
also: annotate the module ```#[cfg(test)]```
j

## Strings

```
    let mut s:String = "Hallo".to_string(); // String literals are refs, have to be converted?
    let p:&str   = "Foo";
```
Hm, String literals are ref by nature!

## Misc

`use` only brings things into scope, does not include anything

`let mut` und `let` assignment, also ownership implied, `const` for constants

`for x in coll` for loop

`std::env::args` is iterator for command line arguments

`unwrap` means just panic if not ok

`expect` also panics, but additional message

`Result` is an enum with `Ok(x)` and `Err(e)` as values

`&name` und `&mut name` just borrows, ownership untouched, deref with `*`

method calls `o.meth()` automatically derefs

raw string with `r#""#`

serialization -> serde

modules: careful `mod name` and `pub mod name`

arrays `[1,2,3,4]` fixed length (at compile time!), fixed types, on the stack

arrays index access `a[i]` is checked at runtime

array init `[0;1000]` semicolon to seperate default value

tuples `[1,"test"]` as usual, index starts with 0

one element tuple with `(1,)` because otherwise evaluation with brackets

every block has a value, if last expr doesn't have a semicolon

`for n in 0..8` has 8 elements, makes easy slicing...

`for x in xyz.iter()` often necessary

use underscore `_` for unused values

`format print write eprint` essentially the same (output varies)

casting is done via `expr as i64` -> From trait

a `?` inside a function body at a `Result<A,B>` return `Err(b)` at failure

closures syntax is `|x|{ body }`, use `move` if capture owership necessary

pattern matching in let statements `let (a,b) = fnreturnstuple();`, also for enums,..

rust allows shadowing, i.e. reassignment -> do this if type changes (unproblematic)

statement `let x=5;` has no value, contrast with expression -> a semicolon means something!

flow `loop{}` and `while cond {}` and `for x in coll {}`

slices have type `let x:&[T]=arr[0..n]`, always refs!

(index,value) pairs can be created with `...iter().enumerate()`

format for debugging with `{:?}`

use the `vec![init;len]` macro to initialize a vector

notice `&str` and `String` have no index acces (unicode), from `String` to `&str` automatically

a `&str` is a `&[u8]`, but contains only valid codepoints

collection `Vec<T>` allows slices, indexed access, etc.

also HashMap, BTreeMap, Set, ...

`coll.iter()` returns an iterator, is lazy (does nothing) - iterator has essentially one method: `next`

standard: `coll.iter().map().filter().collect()` everything is lazy, call collect at last









two spaces generate line break  
before the next line

headings #, ##, ### and so on, or underline ====

italics by `*` for example *this* is slanted

boldface by `**` for example **this** is bold

both using `***` i.e. ***very emph***

## md lists

+ using `+-*` and a blank
+ nextplus
  - deep
  - down
  - nested using two blanks
+ anotherplus

* firststar
* secondstar
* thirdstar

1. alpha numbers, just use them
1. beta
1. gamma

>quotes are done just like
>they would be in email `>` and `>>`
>>and can be nested
>>
