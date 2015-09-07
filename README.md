# znc-pend
## What is it?
A ZNC module that pends private messages to an offline user.
The user is messaged when she gets online. If the user is already online, a regular `PRIVMSG` is sent.

## What isn't it?
Written. Like, at all..

## Interface
`/msg *pend new Lizard[*] I just finished Roadside Picnic, gonna start on Temeraire tonight`
`new <user>` denotes a new message to be added to the pending list. A wildcard can be used to send a message to someone that uses a nick like `Lizard-worky` or something alike. Or should I just go guns blazing with regex support? Maybe some support for a delay too? A "natural" delay too maybe? random it between 5-10s?
`I just [...]` and every other argument are concat'd together into the message to be sent.

### other commands
`/msg *pend list`
Lists all pending messages in the form of:

```
+-------+----------+---------------------------------------------------------------------+
| index | [target] | [message]                                                           |
+-------+----------+---------------------------------------------------------------------+
| 1     | Lizard   | "I just finished Roadside Picnic, gonna start on Temeraire tonight" |
+-------+----------+---------------------------------------------------------------------+
```

`/msg *pend cancel <index>`
Cancels the message with the same index.

`/msg *pend cancel-all`
Cancels all pending messages.
