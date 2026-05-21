 ## Man Page Syntax Notation
 
When you run `man <tool>`, the synopsis at the top tells you how to use the command. Once you learn the notation it becomes easy to read any tool's syntax.
 
## The Symbols
 
`<argument>` — Required. You must provide this.
 
`[argument]` — Optional. You can skip it.
 
`[-f value]` — Optional flag that takes a value.
 
`...` — Repeatable. You can pass this multiple times.
 
`a | b` — Or. Pick one, not both.
 
`[user@]host` — Partially optional. The `user@` part is optional but `host` is required.
 
## Example — Reading a Synopsis
 
```
smbclient [-L] [//server/share] [-U username] [-p port]
```
 
- `-L` — optional, lists shares
- `//server/share` — optional here, but required when connecting
- `-U username` — optional, specify a user
- `-p port` — optional, change port (default is 445)
```
nmap [-sV] [-p <port>] <target>
```
 
- `-sV` — optional, version detection
- `-p <port>` — optional flag but if you use `-p` you must give a port number
- `<target>` — required, the IP or hostname
```
ssh [-i identity_file] [-p port] [user@]hostname
```
 
- `-i identity_file` — optional, use a private key file
- `-p port` — optional, default is 22
- `[user@]hostname` — `hostname` is required, `user@` part is optional

## Quick Reference
 
| Notation | Meaning |
|----------|---------|
| `<value>` | Required argument |
| `[value]` | Optional argument |
| `[-f value]` | Optional flag with required value |
| `a \| b` | Choose one |
| `...` | Can repeat |
| `[user@]host` | Partially optional 
