# Rust

## General stuff

Tools: rustc, rustup, cargo, rustfmt,...

Rust uses snake_case_format

Rust uses 4-space indent

Create a new runable with `cargo new --bin name_of_prj`

Create a new library with `cargo new --lib name_of_lib`

If directory already exists, use `init` instead of `new`

`cargo run` builds an runs a binary app

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

## Strings

```
    let mut s:String = "Hallo".to_string(); // String literals are refs, have to be converted?
    let p:&str   = "Foo";
```
Hm, String literals are ref by nature!







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
