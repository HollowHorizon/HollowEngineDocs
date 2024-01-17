Sometimes you may need to create your own function or add some from others. But do you really want to write it all out in every script? Therefore, you can import the necessary script and use all its contents in the script you need.

To do this, simply add the annotation at the beginning of the file:
```kotlin
@file:Import("../path/to/file.kts")
```

The path in the annotation is specified as [relative](https://en.wikipedia.org/wiki/Path_(computing)), meaning it's relative to the file in which you import the script.

Note: Variables created in the script during import are created anew. In other words, you cannot, for example, create an item in `mod.kts`, then import it into `se.kts`, and use the item variable. Except for `runtime` variables (will be added in one of the next chapters).```
