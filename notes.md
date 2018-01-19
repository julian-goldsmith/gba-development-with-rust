The environment I use is driven by a Makefile.  It compiles a few files using an arm-non-eabi GCC toolchain, processes data files, and calls xargo.

If I remember correctly, I figured out the original setup using [http://antoinealb.net/programming/2015/05/01/rust-on-arm-microcontroller.html](http://antoinealb.net/programming/2015/05/01/rust-on-arm-microcontroller.html) and [http://blog.japaric.io/quickstart/](http://blog.japaric.io/quickstart/) .

Right now I link a static libcore.rlib from the .xargo directory.  I really need to find a better way to get libcore.

We process tiles using grit.  I've been using some ripped art from a game, but I'll create some real \(development\) art before I actually release anything.

The Rust code is configured as a library, which gba\_crt0.s calls.  I'd like to look into modifying gba\_crt0.s to be Rust-specific, but that's not high-priority.

There are also a few stubs in runtime.rs, which handle language features and the like.  Right now they all just loop, but I don't expect they'll need to be changed.

The build.rs file generates bindings to the asset .h files, allowing us to load the assets from Rust.

