# learning-rust
Some simples programs to self-teach me the Rust Programming Language.
https://doc.rust-lang.org/book/ch01-01-installation.html


# Notes:

## rustup, rustc and cargo
* update rust `$ rustup update`
* check the version `$ rustc --version`
* check the documentation `$ rustup doc`

## writing and running an Hello World program
We must always have a `main` function, like C, and this is the first piece of code that is executed. 
```rust
// main.rs
fn main() {
    println!("Hello World!");
}
```
Compile and run the program: 
```bash
$ rustc main.rs
$ ./main
Hello World!
```
It worked! :)

It is important to note that `println!` doesn't call a function. Instead it calls a macro since we are using the `!` notation. To call the function one would write `println`. However, in this case, there is no function called `println`.

## Cargo
Acts like a makefile. It is usefull to build large projects with many crates (that is what header files are called in rust). Going to skip for now! For simple programs, `rustc` is easier.

## Guess the number game
The code can be found in the `guessing_game.rs` file.

Let's go through the program line by line:
1. `use std::io;` - includes the input/output library in the program. This comes with the standard library. By default rust includes automatically some files (see more [here](https://doc.rust-lang.org/std/prelude/index.html))
2. Next we need to store the guess from the user, so we will create a *variable* with the code `let mut guess = String::new();`. To create a new variable, we have to use the keyword `let`, eg. `let a = 5;`. In rust, by default, the variables are immutable (or `const` type in C++). If we desire to modify the value of some variable after initialization, we must add the key word `mut`. Here we declare a new variable called `guess` and assign it a value `String::new()`. `String` is a string type provided by the standard library. So, the line has created a mutable value that is bounded to an empty String.
3. To recieve user input we call the `stdin` funtion from the included library `std::io` and call the `read_line` method, this is `io::stdin().read_line()`. The `read_line` method, takes a String as an argument and appends to it what the user as written in the standard input or command line. The argument goes as follows, `&mut guess`. Here with `&` we are passing a reference for the mutable variable `guess`. When a variable is of mutable type, we need to specify `&mut guess` instead of `&guess`. The next method we call is the `expect` method. The `read_line` method returns a `io::Result` which is an *enum* type variable (these variables are often used with `match`). The `io::Result` variants are `Ok` and `Err`. If the instance of `Result` is `Err`, `expect` will chrash the program and deliver the message passed as an argument. If we don't write the `expect` method after the `read_line` method, the compiler will give us a warning.
4. We can print variables like `println!("The value of a is {}", a);`. Using the syntax `"{}"`.








