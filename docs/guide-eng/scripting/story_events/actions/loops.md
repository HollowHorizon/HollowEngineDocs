# Loops

It is not recommended to use standard `while` and `for` loops within narrative scripts, at least at the [loading stage](../../story_events/#_4) of the script.

As an alternative, a similar method has been added, but with a capital letter:

```kts
While({<condition>}) {
    // Actions performed while the condition is true
}
```

> `<condition>` - any code returning `Boolean`. (`true` / `false`) This condition will be checked at the script execution stage, not during loading, so it is preferable to use this `If` / `Else` implementation.

---

## Infinite loop

This loop will never end. The narrative event will not end either unless you stop the entire script from another script or when using it in Asynchronous Actions.
However, in the latter case, you also need to stop this action later.
```kts
While({true}) {
	// Your actions
}
```