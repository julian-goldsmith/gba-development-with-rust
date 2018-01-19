# 1. Environment

The environment I use is driven by a Makefile.  It compiles a few files using an arm-non-eabi GCC toolchain, processes data files, and calls xargo.

If I remember correctly, I figured out the original setup using [http://antoinealb.net/programming/2015/05/01/rust-on-arm-microcontroller.html](http://antoinealb.net/programming/2015/05/01/rust-on-arm-microcontroller.html) and [http://blog.japaric.io/quickstart/](http://blog.japaric.io/quickstart/) .

The Rust code is configured as a library, which gba\_crt0.s calls.  I'd like to look into modifying gba\_crt0.s to be Rust-specific, but that's not high-priority.

There are also a few stubs in runtime.rs, which handle language features and the like.  Right now they all just loop, but I don't expect they'll need to be changed.

## 1.1 First Rust program

This section will present a program similar to Tonc's first program.



