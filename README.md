# riscv-instr

`riscv-instr` is a shell script which outputs  32 bit instructions from assembly source files or RISC-V 32 bit ELF binaries.

### Prerequisites
You need the GNU Compiler Toolchain for RISC-V. You can find the
toolchain [here](https://github.com/riscv/riscv-gnu-toolchain). The
basic installation instructions can also be found in the README file of 
[our RISC-V implementation](https://zenon.cs.hs-rm.de/vhdl-cpu/riscv).

After the installation you need to add the installed binaries to your `PATH``variable.

    export PATH=$PATH:/opt/riscv/bin

### Installation
Download the file `riscv-instr` and put the file somewhere in your `$PATH`.

Afterwards make the file executable:

    chmod +x /path/to/riscv-instr


### Usage

Output all instructions for the function main (default function):
   
    $ riscv-instr <executable|assembly-source>
    0x00c10093 
    0x002080b3

Output the instructions for a specified function named `func1`

    $ riscv-instr -f func1 <executable|assembly-source>
    0x00c10093 
    0x002080b3

Also add a comment line at the end of each instruction

    $ riscv-instr -c <executable|assembly-source>
    0x00c10093 -- addi ra,sp,12
    0x002080b3 -- add ra,ra,sp


### Parameters

`-f <func>` - 
Try  to disassemble the specified function and output the instructions. If this option is not passed at all, the function `main()` will get disassembled by default.

`-c` - Add a comment of the assembly code next to the instruction

`--help` - Show the parameters of the tool.



### License and Copyright
Licensed under the GNU General Public License 3.

(C) Jens Nazarenus, 2017
