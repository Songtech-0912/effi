# Effi

Effi is Project Elära's minimal library for interfacing with C functions.

## Example usage

```rs
use effi::*;

extern "C" {
    // Function signatures of all the C functions you want to call
    fn abs(n: c_int) -> c_int;
    fn sqrt(n: c_double) -> c_double;
    // ...
}

fn main() {
    unsafe {
        let n: i32 = -11;
        let n_2: f64 = 11.0;
        println!("The absolute value of {} is {}", n, abs(n as c_int));
        println!("The square root of {} is {}", n_2, sqrt(n_2 as c_double));
    }
}
```