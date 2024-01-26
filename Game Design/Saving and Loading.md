Usually, games have the need to save some or the other data for players. This may range from just leader-board high-scores to fully fledged game saves that save the state of every object present in the game world. One common way is to [_serialize_](https://en.wikipedia.org/wiki/Serialization) your data. There's several ways to go about serialization, one of which is using **blobs**.

#### Blobs

> [!info] Definition
> A _blob_ is a contiguous section of memory, that is _movable, copiable and self-contained_.

We can pass the blob around, and used to build at runtime data structures that we need, even with some complexity. Essentially, we can think of a blob as some kind of a file. This may be a JSON or XML file, or just a straight up runtime array for smaller data. BLOBs may be persistent or temporary. 

There's many other ways to store data but blobs are by far the most common way. Blobs can also nest other data structures within them to make for an even efficient way of storing stuff (like dictionaries in the form of JSON). 



---
##### References
- [Serialization for games](https://jorenjoestar.github.io/post/serialization_for_games/)
- [The Blob and I](https://bitsquid.blogspot.com/2010/02/blob-and-i.html)
- [FlatBuffers](https://flatbuffers.dev/) and [ProtocolBuffers](https://protobuf.dev/) as explicit data formats.
- [Jinja](https://jinja.palletsprojects.com/en/3.1.x/) as a Code generation solution for DDLs and Schema Definitions
- [JSON to C](https://zltl.github.io/json-gen-c/)
- [ANTLR -  a powerful parser generator for reading, processing, executing, or translating structured text or binary files.](https://github.com/antlr/antlr4)
- 
