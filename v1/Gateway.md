# Gateway v1

## Gateway Payload structure

```ts
 { 
    action: string;
    token: string;
    ...params: any;
 }
```

## Actions

| Action               | description                           |
|----------------------|---------------------------------------|
| message.system.ping  | Ping message answer                   |
| disconnect           | Disconnect from gateway               |
| message.user         | Send message to chat                  |
| message.user.receive | Receive message from chat             |
| ping                 | Request the server ping               |

## Action Payload structure

```ts
// Action: message.system.ping
{
    action: "message.system.ping";
    time: Date
}
// Action: disconnect
{
    action: "disconnect";
}
// Action: message.user
{
    action: "message.user";
    token: "user token here";
    content: "some random message";
    time: Date;
    username: "Kurays"; // WARNING: Unused field, not required.
}
// Action: message.user.receive
{
    action: "message.user.receive";
    msg_id: "snowflake id";
    username: "Gateway";
    user_id: "snowflake id";
    avatar: "https://example.com/example.png";
    content: "What?";
    time: Date;
    flags: 11; // Bitfield
}
// Action: ping
{
    action: "ping"
}
```