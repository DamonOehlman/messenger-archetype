# The `messenger` Archetype

A messenger is simply a function that can be called to create a [`pull-stream`](https://github.com/dominictarr/pull-stream) `Source` and/or `Sink`.  This source and sink can subsequently be used to send and/or receive messages.  It's very simple.

A messenger function has the following signature:

```
fn(callback)
```

and the callback when executed has the following signature:

```
fn(err, source, sink)
```

The idea being that when you require the ability to send and/or receive messages you call the messenger function which initialises and creates a new messenging channel.  In general, you shouldn't care too much about whether the messenger closes and can simply buffer outgoing messages using something like [`pull-pushable`](https://github.com/dominictarr/pull-pushable).  In the event that messenger is closed (you will be able to detect this in both the source and the sink), you simply want to call the messenger function again to reopen the connection.

## Known Implementations

### Complete

- None yet.

### Proposed / In Progress

- [`messenger-memory`](https://github.com/DamonOehlman/messenger-memory) (requires refactoring to match the archetype).
- `messenger-ws` - Will provide a messager via web sockets.
