A try-with-resources statement in Java 7 is used to close resources automatically after a try code block. An object that implements the AutoCloseable interface has its close() method always called at the try block finalization, it an analog way to the use of a finally clause and similar to a context manager in Python 2 where the __enter__() method corresponds to the Java class constructor and the __exit__() method corresponds to the method close().

The Nashorn engine that comes with Java 8 isn’t fully compliant with Javascript Harmony because multiline strings has a different syntax turning .js files incompatible with other engines. But provides some scripting advantages via the -scripting flag as a syntax to evaluate commands in back-ticks returning its output into a string (e.g. `echo a` == “a\n”).

Java 8 finally has some sort of multiple inheritance via interface default methods (e.g. default int m() { return 1; }). 

[1] https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html
[2] http://www.oracle.com/technetwork/articles/java/jf14-nashorn-2126515.html
[3] https://dzone.com/articles/interface-default-methods-java
