# vpcode

Index of visual pinball table scripts

The idea here is to extract the `vbs` files from the most popular tables and index them here so we can search through the code and compare tables / versions.

## Extracting the code

```
> VPinballX.exe -ExtractVBS [path to vpx file]
```
[Command line parameter docs](https://github.com/vpinball/vpinball/blob/master/txt/CommandLineParameters.txt)

This will place the `vbs` file next to the `vpx` file.

## VPX Files

VPX files are using the [Compound File Binary File Format (CFBF)](https://en.wikipedia.org/wiki/Compound_File_Binary_Format)
see also [ms-cfb](https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-cfb/53989ce4-7b05-4f8d-829b-d08d6148375b?redirectedfrom=MSDN)

You can open them in 7-zip to inspect the contents

This file format can be read using [OpenMCDF](https://github.com/ironfede/openmcdf) (Microsoft Compound Document Format, also known as OLE structured storage)

c# writing https://github.com/freezy/VisualPinball.Engine/blob/ec1e9765cd4832c134e889d6e6d03320bc404bd5/VisualPinball.Engine/VPT/Table/TableWriter.cs#L44

c# reading https://github.com/freezy/VisualPinball.Engine/blob/ec1e9765cd4832c134e889d6e6d03320bc404bd5/VisualPinball.Engine/VPT/Table/TableLoader.cs#L36

c++ writing https://github.com/vpinball/vpinball/blob/c3c59e09ed56a69759280867affa1f0abf537451/pintable.cpp#L2625

c# partial read code https://github.com/stojy/ClrVpin/blob/a317f3985b77f56aac7c5109f76d541c046c87fc/ClrVpin/Shared/Utils/TableUtils.cs#LL79C11-L79C11

