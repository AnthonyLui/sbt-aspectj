# Weaving annotation-based aspects

A sample project that weaves annotation-based aspects written in Scala.

To run the sample test, call `sbt check`.


## Adding inputs

To weave annotation-based aspects, add the compiled classes as an input. There
is a helper method called `compiledClasses` for doing this:

```scala
AspectjKeys.inputs in Aspectj <+= compiledClasses
```


## Products

To use or package the compiled aspects, replace the regular compile products
with the aspectj products:

```scala
products in Compile <<= products in Aspectj
```

And to have these same products also in runtime:

```scala
products in Runtime <<= products in Compile
```
