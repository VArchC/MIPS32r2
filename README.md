MIPS32r2 VArchC functional model
=====

This is the MIPS32r2 VArchC functional model.

Current status
--------------
This model supports quite a few MIPS32r2 instructions, enough to compile
Mibench programs and run them correctly. However, this implementation does not
feature all instructions from the ISA specification, but only those appearing in
benchmarks. If you run into an implemented instruction, you can easily expand
this model.

It is possible that your program uses an unimplemented syscall, since this is
not a system simulator, but a process simulator. If this syscall is crucial to
your program, you may need to expand ArchC to implement it.

License
-------
 - ArchC models are provided under the ArchC license.
   See [Copying](COPYING) file for details on this license.

Build
-----

You need VArchC to build and use this model. Refer to [the VArchC repository](https://github.com/VArchC/ArchC) for more information. Use *acsim* to create the simulator and build it using GNU Make.

```bash
acsim mips.ac -abi
make
```

Compile a test application
--------------------------

We recommend using the [ELLCC compiler](http://ellcc.org/) to compile applications for MIPS32r2.
Download [ELLCC v0.1.34](http://ellcc.org/releases/older-releases/ellcc-x86_64-linux-0.1.34.tgz)
and extract it to a directory. The *bin* subdirectory contains all the ELLCC executables. To compile
a "hello.c" application for MIPS, use:
```bash
ecc -target mips32r2-linux -o hello.mips hello.c
```

Our Testbench
-------------

We provide source code for test applications to be used with our CPU models,
including this MIPS model. Refer to our [Testbench repository](https://github.com/VArchC/Testbench)
for more information.
