The Interfaces you're most likely to implement are:  
`java.lang.Comparable`  
`java.lang.Runnable`  
`java.io.Serializable`

Interfaces that you're most likely to call methods on but not implement yourself are:  
`java.lang.Appendable` (StringBuffer / StringBuilder / Writers)  
`java.lang.CharSequence` (String / StringBuffer / StringBuilder)  
`java.lang.Iterable` (Collections, either explicitly or with `for Blah blah : List<Blah>`)  
`java.lang.Readable` (Readers)  
`java.io.Closeable` (Streams)  
`java.io.Flushable` (Streams)  
`java.util.Collection` (Collections)  
`java.util.Deque` (Collections)  
`java.util.List` (Collections)  
`java.util.Map` (Collections)  
`java.util.Set` (Collections)

Interfaces that are most likely to blow up in your face:  
`java.lang.Cloneable`

Edit: Whoops, Throwable's not an interface.

Usually, it's better to write a Copy Constructor rather than use a `clone()` method.


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIwOTE5NjYxNyw3MzA5OTgxMTZdfQ==
-->