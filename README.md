# Rustulator
A CLI based calculator I made to practice while learning rust
Basic addition, substraction, multiplication, division, and raising to power for now

The code file (`src/main.rs`):
```rs
use std::io;

fn main() {
    println!("Welcome to さび電卓!");
    loop {
        //入力を求める (Asking for inputs)
        println!("\nEnter 1st number:");

        let mut num1 = String::new();

        io::stdin()
            .read_line(&mut num1)
            .expect("Please enter a number");

        println!("Enter operator:");

        let mut op = String::new();

        io::stdin()
            .read_line(&mut op)
            .expect("Please enter a something");

        println!("Enter 2nd number:");

        let mut num2 = String::new();

        io::stdin()
            .read_line(&mut num2)
            .expect("Please enter a number");
        
        //入力の解析 (Parsing inputs)
        let num1: u32 = num1.trim().parse().expect("Please type a number!");
        let num2: u32 = num2.trim().parse().expect("Please type a number!");
        let op = op.trim();

        //計算 (Calculation)
        if op == "+" {
            let result: u32 = num1 + num2;
            println!("{num1} {op} {num2} = {result}");

        } else if op == "-" {
            let result: u32 = num1 - num2;
            println!("{num1} {op} {num2} = {result}");

        } else if op == "/" {
            let result: u32 = num1 / num2;
            println!("{num1} {op} {num2} = {result}");

        } else if op == "*" {
            let result: u32 = num1 * num2;
            println!("{num1} {op} {num2} = {result}");

        } else if op == "^" {
            let result = u32::pow(num1, num2);
            println!("{num1} {op} {num2} = {result}");

        } else {
            println!("Operator must be +, -, * or /");
        }
    }
}
```
