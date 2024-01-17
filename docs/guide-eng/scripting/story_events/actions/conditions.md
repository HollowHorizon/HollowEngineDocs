# Conditions and Branching

It is not recommended to use standard `if` and `else` within narrative scripts, at least at the [loading stage](../../story_events/#_4) of the script.

As an alternative, similar methods have been added, but with a capital letter:

```kts
If({<condition>}) {
    // Action when the condition is true
} Else {
    // Action if the condition is not true
}
```

> `<condition>` - any code returning `Boolean`. (`true` / `false`) This condition will be checked at the script execution stage, not during loading, so it is preferable to use this `If` / `Else` implementation.