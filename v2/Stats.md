# API v2

## Endpoints

### `/stats/users`
Fetches information about count of registered users
#### Response: 
```ts
{
    count: number;
    users: number;
    bots: number;
}
```