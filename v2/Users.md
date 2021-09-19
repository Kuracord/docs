# API v2

## Models

### User
```ts
{
    id: string;
    username: string;
    discriminator: string;
    avatar: string;
    email?: string;
    guilds?: Member[];
    flags: number;
    disabled?: string;
    verified?: string;
    mfa?: boolean;
    bots?: Bot[];
}
```
---
### UserUpdateParams
Should contain either `username` or `discrim`. \
`username` should be 1-32 characters long. \
`discrim` should contain only numeric characters and be 4 characters long.
```ts
{
    username?: string;
    discrim?: string;
}
```
---
### UserRegisterParams
`email` should match against
```
/(?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9]))\.){3}(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9])|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])/gm
```
regex. \
`username` should be less or equal to 17 characters long. \
`password` should be 8-33 characters long.
```ts
{
    email: string;
    username: string;
    password: string;
}
```
---
### UserLoginParams
```ts
{
    email: string;
    password: string;
}
```

---

## Endpoints

### `/users/@me`
Fetches information about current logged in user.
#### Response: `User`
---
### `/users/@me/update`
Updates `username` and `discriminator` of current logged in user.
#### Input: `UserUpdateParams`
#### Response: `User`
---
### `/users/@me/update/avatar`
Updates `avatar` of current logged in user.
#### Input: `File`
#### Response:
```json
{
    "res": "uploaded"
}
```
---
### `/users/:id`
Fetches information about specified user.
#### Response: `User`
---
### `/users/create`
Creates new user.
#### Input: `UserRegisterParams`
#### Response: `User`
---
### `/users/login`
Logs into user.
#### Input: `UserLoginParams`
#### Response: `User`
