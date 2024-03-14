# webgraph
Webgraph++ code (http://cnets.indiana.edu/groups/nan/webgraph/)

This code worked for what I used it for, but I cannot promise it is thorougly tested and there are almost certainly some strange bugs!
Your help would be greatly appreciated in adding tests and generally cleaning it up.

I have moved on and do not have much time to answer questions about setup and compilation, so this code is provided AS-IS. With that said, I hope it is useful or at least interesting.

You will definitely need Boost (http://www.boost.org/) to make this work.

You will notice a lot of TODOs and commented-out unimplemented methods. Feel free to write them :)

## Compilation
Modify the fields ``INCLUDES`` and ``LIBS`` in ``flags.mk`` inserting the absolute path of the project.
Then
```bash
cd webgraph
make -j 12
```

## Encoding
```bash
./tests/compress_webgraph --source=./data/somegraph --dest=./data/somegraph.wbg
```

## Decoding
Firstly, compile:
```bash
cd tests
g++ -L.. -I.. -O3 print_webgraph.cpp -o print_webgraph -lwebgraph -lboost_regex -lboost_program_options -lboost_filesystem 
cd ..
```
Then, run:
```bash
tests/print_webgraph data/somegraph.wbg
```
