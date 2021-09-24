## Building
### Build script 1

```rust
use std::env;
use std::fs;
use std::path::Path;

fn main() {
    //let out_dir = env::var_os("OUT_DIR").unwrap();
    let out_dir = "src/";
    let dest_path = Path::new(&out_dir).join("main.rs");
    fs::write(
        &dest_path,
        "fn main() { println!(\"Hello, World!\"); }"
    ).unwrap();
    println!("cargo:rerun-if-changed=build.rs");
}
```

## Modules

Create rectangle

```rust
pub fn create_rectangle() {
        crate::shapes::rectangles::Rect {
                width: 5,
                height: 5
        };

}
```

Another line

```rust
shapes::new_rect(5, 5);
```

Another file

```rust
mod temp;
```

```rust
use temp::shapes::*;
```


```rust
[dependencies]
piston_window = { version = "0.120.0", git = "https://github.com/PistonDevelopers/piston" }
rand = { git = "https://github.com/example/rand", rev = "9f35b8e" }
```

Or a local directory.

```rust
[dependencies]
piston_window = { version = "0.120.0", path = "~/github/piston" }
```

## Tests
in `tests/integration_test.rs`
```rust
#[test]
pub fn test1() {
    assert_eq!(1, 1);
}
```
