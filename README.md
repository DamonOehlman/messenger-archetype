# The `messenger` Archetype

A messenger is simply a function that can be called to create a [`pull-stream`](https://github.com/dominictarr/pull-stream) `Source` and/or `Sink`.  This source and sink can subsequently be used to send and/or receive messages.  It's very simple.

A messenger function has the following signature:

```
fn(opts?, callback)
```

and the callback when executed has the following signature:

```
fn(err, source, sink)
```

## Known Implementations

### Complete

- None yet.

### Proposed / In Progress

- [`messenger-memory`](https://github.com/DamonOehlman/messenger-memory) (requires refactoring to match the archetype).
- `messenger-ws` - Will provide a messager via web sockets.
