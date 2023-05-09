# vpcode

Index of [Visual Pinball](https://github.com/vpinball/vpinball) table scripts

The idea here is to extract the `vbs` files from the most popular tables and index them here so we can search through the code and compare tables / versions.

## Why?

I personally think the current way of developing visual pinball tables is suboptimal. One binary file that contains everything. No code / asset versioning, no history, sharing through public file services, ...

Would it not be better to have a directory structure whith all the files that we can put in version control? I do understand there are some copyright issues for commercail tables but those tables can then be developed privately and would still benefit from version control.

Preferably Visual pinball would then also support a folder structure next to vpx files

## Extracting the code

```
> VPinballX.exe -ExtractVBS [path to vpx file]
```
[Command line parameter docs](https://github.com/vpinball/vpinball/blob/master/txt/CommandLineParameters.txt)

This will place the `vbs` file next to the `vpx` file.

## Sidecar vbs support

Any `vbs` next to the `vpx` with the same file name will be picked up by VP as the table script
"side-car" table support.

see https://github.com/vpinball/vpinball/commit/132c72ad913441c5af5fd0ce667186e44cb904bb

## VPX Files

VPX files are using the [Compound File Binary File Format (CFBF)](https://en.wikipedia.org/wiki/Compound_File_Binary_Format)
see also [ms-cfb](https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-cfb/53989ce4-7b05-4f8d-829b-d08d6148375b?redirectedfrom=MSDN)

You can open them in 7-zip to inspect the contents

This file format can be read using .net [OpenMCDF](https://github.com/ironfede/openmcdf) (Microsoft Compound Document Format, also known as OLE structured storage)
or c++ [POLE](https://dimin.net/software/pole/)
or rust [ole](https://docs.rs/ole/latest/ole/)

c# writing https://github.com/freezy/VisualPinball.Engine/blob/ec1e9765cd4832c134e889d6e6d03320bc404bd5/VisualPinball.Engine/VPT/Table/TableWriter.cs#L44

c# reading https://github.com/freezy/VisualPinball.Engine/blob/ec1e9765cd4832c134e889d6e6d03320bc404bd5/VisualPinball.Engine/VPT/Table/TableLoader.cs#L36

c++ writing https://github.com/vpinball/vpinball/blob/c3c59e09ed56a69759280867affa1f0abf537451/pintable.cpp#L2625

c# partial read code https://github.com/stojy/ClrVpin/blob/a317f3985b77f56aac7c5109f76d541c046c87fc/ClrVpin/Shared/Utils/TableUtils.cs#LL79C11-L79C11

## Previous work

There is this repo: https://github.com/sverrewl/vpxtable_scripts
