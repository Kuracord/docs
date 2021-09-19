# Gateway

## Gateway Payload structure

```js
 { 
    op: opcode,
    t: type,
    d: data
 }
```

## Opcodes

| code    | Name                             |
|---------|----------------------------------|
| 1       | IDENTIFY                         |
| 2       | DISPATCH                         |

## Actions

| Action               | description                           |
|----------------------|---------------------------------------|
| MESSAGE_CREATE       | Message create                        |
| MESSAGE_DELETE       | Message delete                        |
| USER_UPDATE          | Action that dispatches on user update |
