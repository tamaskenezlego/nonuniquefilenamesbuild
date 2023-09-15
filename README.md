Example demonstrating that Visual Studio reverts to single-processor compilation if there are multiple source files with the same filename.

`CMakeLists.txt` generates two, almost identical executable targets: `nonunique` and `unique`. They consists of many files in numbered directories. In case of `nonunique` all files are named `source.cpp` whereas for `unique` they're numbered: `source-##.cpp`.

The `/MP` compiler flag is enabled for both targets. The `unique` executable builds much faster since the compilation mode is multi-processor while for `unique` is single-processor.

![image](https://github.com/tamaskenezlego/nonuniquefilenamesbuild/assets/126668370/418fc0bc-6857-4128-9c20-733c9807176c)

