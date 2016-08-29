Try-With-Resources
==================

A try-with-resources statement in Java 7 is used to close resources automatically after a try code block. An object that implements the AutoCloseable interface has its `close()` method always called at the try block finalization, it is analog to the use of a finally clause calling `close()` and similar to a context manager in Python 2 where the `__enter__()` method corresponds to the Java class constructor and the `__exit__()` method corresponds to the method `close()`.

https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html

```java

class T implements AutoCloseable { /* implementation */ }
class U implements AutoCloseable { /* implementation */ }

try (T t = T(); U u = U()) {
 System.out.println(t);
 System.out.println(u);
} // finally { u.close(); t.close() }
```

```python
class T: pass
class U: pass

with T() as t:     # t.__enter__()
    with U() as u: # u.__exit__()
        print(t)
        print(u)
    # u.__exit__()
 # t.__exit__()
```

Nashorn engine
==============

The Nashorn engine that comes with Java 8 isn’t fully compliant with Javascript Harmony because multiline strings has a different syntax turning .js files incompatible with other engines. But provides some advantages integrating with the JVM or Java classes and scripting capabilities via the `-scripting` flag as the syntax to evaluate commands in back-ticks returning its output into a string (e.g. ```echo a` == "a\n"``).

http://www.oracle.com/technetwork/articles/java/jf14-nashorn-2126515.html

```javascript
#!/usr/bin/jjs -scripting
var cont = 1;
var files = `ls`.split('\n');
var map = new java.util.HashMap();

files.forEach(function (file) {
    map.put(cont++, file);
});

print(map.size());
```

Interface default methods
=========================

Java 8 finally has some sort of multiple inheritance via interface default methods (e.g. `default int m() { return 1; }`). Now classes can "inherit" concrete methods from multiple interfaces, disanbiguation is done implementing it otherwise causing a compilation error. It avoiding complex rules to determine which method implementation will be called, but the only difference from inheriting from multiple abstract classes is that interfaces can't have a constructor or a `this` reference.

https://dzone.com/articles/interface-default-methods-java
