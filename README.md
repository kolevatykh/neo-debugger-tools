# NEO-dev-tools
Suite of development tools for NEO smart contracts.
Includes a cli disassembler and a GUI debugger. An helper library that helps loading .AVM files and create and load .neomap files is also included, and can be used to create other dev tools.

# Limitations
- Debugging ASM and C# only for now (see section below how to add new languages)
- Windows only for now, using .NET Framework
- Not possible yet to inspect variable values
- Most NEO syscalls/APIs not supported yet (work in progress)

# How to use

Open the .avm file in the NEO-dbg GUI application.
This will show either assembly code for the .avm or C# if a debug map file was found.
Currently the only way to generate a .neomap file is to compile the smart contracts with the modified NeoN compiler include in this repository.

# Support for other languages

NEO smart contracts can be coded in many different languages, and in theory, this compiler already supports any language as long as a .neomap file exists in the same directory as the .avm file.
However since only NeoN was modified to emit those map files during compilation, to add other languages it would be necessary to modify other compilers to emit a .neomap.
The .neomap file format is simple, for each line you need to list a starting offset, ending offset, the source line and the corresponding source file, all values separated by a comma.