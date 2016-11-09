### Getting two mutable references to the same vector

``` rust
fn do_stuff(v: &mut Vec<i32>) {

    let (a, b) = v.split_at_mut(1);
    let first  = &mut a[0];
    let second = &mut b[0];
    
    *first = 4;
    *second = 5;
}


fn main() {

    let mut v = vec![1, 2, 3];
    
    do_stuff(&mut v);
    
    println!("{:?}", v);
}
```
