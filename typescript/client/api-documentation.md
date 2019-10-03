---
id: api-documentation
title: API Documentation
---

## ConnectionManager

### `connect()`

```ts
public connect(host: string, name = "main")
```

Connect to the given connection.

#### Parameters

| Type   | Name       | Required | Description  |
| ------ | ---------- | -------- | ------------ |
| string | host       | Yes      | Node URL     |
| string | name       | No       | Network name |

#### Return Value

`Connection`

---

### `disconnect()`

```ts
public disconnect(name?: string)
```

Disconnect from the given connection.

#### Parameters

| Type   | Name       | Required | Description  |
| ------ | ---------- | -------- | ------------ |
| string | name       | No       | Network Name |

#### Return Value

`void`

---

### `connection()`

```ts
public connection(name?: string)
```

Get a connection instance.

#### Parameters

| Type   | Name       | Required | Description  |
| ------ | ---------- | -------- | ------------ |
| string | name       | No       | Network Name |

#### Return Value

`Connection`

---

### `getDefaultConnection()`

```ts
public getDefaultConnection()
```

Get the default connection name.

#### Return Value

`string`

---

### `setDefaultConnection()`

```ts
public setDefaultConnection(name: string)
```

Set the default connection name.

#### Parameters

| Type   | Name       | Required | Description  |
| ------ | ---------- | -------- | ------------ |
| string | name       | No       | Network Name |

#### Return Value

`void`

---

### `getConnections()`

```ts
public getConnections()
```

Return all of the created connections.

#### Return Value

`Record<string, Connection>`

## Connection

### `constructor()`

```ts
public constructor(private readonly host: string)
```

Create a new Connection class instance.

#### Parameters

| Type    | Name       | Required | Description |
| ------- | ---------- | -------- | ----------- |
| string  | host       | Yes      | Node URL    |

---

### `api()`

```ts
public api<T = any>(name: string)
```

Instantiate new Api.

#### Parameters

| Type   | Name       | Required | Description  |
| ------ | ---------- | -------- | ------------ |
| string | name       | Yes      | Network name |

#### Return Value

`T`

---

### `get()`

```ts
public async get<T = any>(url: string, opts?: Record<string, any>)
```

Send a GET request with query parameters.

#### Parameters

| Type                | Name       | Required | Description      |
| ------------------- | ---------- | -------- | ---------------- |
| string              | url        | Yes      | Endpoint         |
| Record<string, any> | opts?      | No       | Query parameters |

#### Return Value

`Promise<IResponse<T>>`

---

### `post()`

```ts
public async post<T = any>(url: string, opts?: Record<string, any>): Promise<IResponse<T>>
```

Send a POST request with JSON-encoded parameters.

#### Parameters

| Type                | Name       | Required | Description      |
| ------------------- | ---------- | -------- | ---------------- |
| string              | url        | Yes      | Endpoint         |
| Record<string, any> | opts?      | No       | Query parameters |

#### Return Value

`Promise<IResponse<T>>`

## RequestError

### `constructor()`

```ts
public constructor(error)
```

Create a new RequestError class instance.

#### Parameters

| Type    | Name       | Required | Description |
| ------- | ---------- | -------- | ----------- |
| string  | error      | Yes      | Error       |

## Resources\Blocks

### `all()`

```ts
public async all<T = any>(query?: Record<string, any>)
```

Get all blocks.

#### Parameters

| Type                | Name       | Required | Description      |
| ------------------- | ---------- | -------- | ---------------- |
| Record<string, any> | query      | No       | Query parameters |


#### Return Value

`Promise<IResponse<T>>`

---

### `get()`

```ts
public async get<T = any>(id: string)
```

Get a block by the given id.

#### Parameters

| Type   | Name     | Required | Description |
| ------ | -------- | -------- | ----------- |
| string | id       | Yes      | Block ID    |

#### Return Value

`Promise<IResponse<T>>`

---

### `transactions()`

```ts
public async transactions<T = any>(id: string, query?: Record<string, any>)
```

Get all transactions by the given block.

#### Parameters

| Type                | Name       | Required | Description      |
| ------------------- | ---------- | -------- | ---------------- |
| string              | id         | Yes      | Block ID         |
| Record<string, any> | query      | No       | Query parameters |

#### Return Value

`Promise<IResponse<T>>`

---

### `search()`

```ts
public async search<T = any>(payload?: Record<string, any>)
```

Filter all blocks by the given parameters.

#### Parameters

| Type                | Name       | Required | Description       |
| ------------------- | ---------- | -------- | ----------------- |
| Record<string, any> | payload    | No       | Search parameters |

#### Return Value

`Promise<IResponse<T>>`

## Resources\Delegates

### `all()`

```ts
public async all<T = any>(query?: Record<string, any>)
```

Get all accounts.

#### Parameters

| Type                | Name       | Required | Description      |
| ------------------- | ---------- | -------- | ---------------- |
| Record<string, any> | query      | No       | Query parameters |

#### Return Value

`Promise<IResponse<T>>`

---

### `get()`

```ts
public async get<T = any>(id: string)
```

Get a delegate by the given id.

#### Parameters

| Type   | Name        | Required | Description         |
| ------ | ----------- | -------- | ------------------- |
| string | id          | Yes      | Delegate identifier |

#### Return Value

`Promise<IResponse<T>>`

---

### `blocks()`

```ts
public async blocks<T = any>(id: string, query?: Record<string, any>)
```

Get all blocks for the given delegate.

#### Parameters

| Type                | Name       | Required | Description         |
| ------------------  | ---------- | -------- | ------------------- |
| string              | id         | Yes      | Delegate identifier |
| Record<string, any> | query      | No       | Query parameters    |

#### Return Value

`Promise<IResponse<T>>`

---

### `voters()`

```ts
public async voters<T = any>(id: string, query?: Record<string, any>)
```

Get all voters for the given delegate.

#### Parameters

| Type                | Name       | Required | Description         |
| ------------------  | ---------- | -------- | ------------------- |
| string              | id         | Yes      | Delegate identifier |
| Record<string, any> | query      | No       | Query parameters    |

#### Return Value

`Promise<IResponse<T>>`

## Resources\Node

### `configuration()`

```ts
public async configuration<T = any>()
```

Get the node configuration.

#### Return Value

`Promise<IResponse<T>>`

---

### `status()`

```ts
public async status<T = any>()
```

Get the node status.

#### Return Value

`Promise<IResponse<T>>`

---

### `syncing()`

```ts
public async syncing<T = any>()
```

Get the node syncing status.

#### Return Value

`Promise<IResponse<T>>`

---

### `fees()`

```ts
public async fees<T = any>(days: number)
```

Get the node fee statistics.

#### Parameters

| Type   | Name        | Required | Description |
| ------ | ----------- | -------- | ----------- |
| number | days        | Yes      | Days        |

#### Return Value

`Promise<IResponse<T>>`

## Resources\Peers

### `all()`

```ts
public async all<T = any>(query?: Record<string, any>)
```

Get all peers.

#### Parameters

| Type                | Name       | Required | Description      |
| ------------------- | ---------- | -------- | ---------------- |
| Record<string, any> | query      | No       | Query parameters |

#### Return Value

`Promise<IResponse<T>>`

---

### `get()`

```ts
public async get<T = any>(ip: string)
```

Get a peer by the given IP address.

#### Parameters

| Type   | Name | Required | Description |
| ------ | ---- | -------- | ----------- |
| string | ip   | Yes      | IP address  |

#### Return Value

`Promise<IResponse<T>>`

## Resources\Transactions

### `create()`

```ts
public async create<T = any>(payload: object[])
```

Create a new transaction.

#### Parameters

| Type     | Name         | Required | Description                 |
| -------- | ------------ | -------- | --------------------------- |
| object[] | payload      | Yes      | Transaction(s) to broadcast |

#### Return Value

`Promise<IResponse<T>>`

---

### `get()`

```ts
public async get<T = any>(id: string)
```

Get a transaction by the given id.

#### Parameters

| Type   | Name           | Required | Description    |
| ------ | -------------- | -------- | -------------- |
| string | id             | Yes      | Transaction ID |

#### Return Value

`Promise<IResponse<T>>`

---

### `all()`

```ts
public async all<T = any>(query?: Record<string, any>)
```

Get all transactions.

#### Parameters

| Type                | Name       | Required | Description      |
| ------------------- | ---------- | -------- | ---------------- |
| Record<string, any> | query      | No       | Query parameters |

#### Return Value

`Promise<IResponse<T>>`

---

### `allUnconfirmed()`

```ts
public async allUnconfirmed<T = any>(query?: Record<string, any>)
```

Get all unconfirmed transactions.

#### Parameters

| Type                | Name       | Required | Description      |
| ------------------- | ---------- | -------- | ---------------- |
| Record<string, any> | query      | No       | Query parameters |

#### Return Value

`Promise<IResponse<T>>`

---

### `getUnconfirmed()`

```ts
public async getUnconfirmed<T = any>(id: string)
```

Get an unconfirmed transaction by the given id.

#### Parameters

| Type   | Name     | Required | Description    |
| ------ | -------- | -------- | -------------- |
| string | id       | Yes      | Transaction ID |

#### Return Value

`Promise<IResponse<T>>`

---

### `search()`

```ts
public async search<T = any>(payload: Record<string, any>)
```

Filter all transactions by the given parameters.

#### Parameters

| Type                | Name       | Required | Description       |
| ------------------- | ---------- | -------- | ----------------- |
| Record<string, any> | payload    | Yes      | Search parameters |

#### Return Value

`Promise<IResponse<T>>`

---

### `types()`

```ts
public async types<T = any>()
```

Get a list of valid transaction types.

#### Return Value

`Promise<IResponse<T>>`

---

### `fees()`

```ts
public async fees<T = any>(): Promise<IResponse<T>>
```

Get the node fee statistics.

#### Return Value

`Promise<IResponse<T>>`

## Resources\Votes

### `all()`

```ts
public async all<T = any>(query?: Record<string, any>)
```

Get all votes.

#### Parameters

| Type                | Name       | Required | Description      |
| ------------------- | ---------- | -------- | ---------------- |
| Record<string, any> | query      | No       | Query parameters |

#### Return Value

`Promise<IResponse<T>>`

---

### `get()`

```ts
public async get<T = any>(id: string)
```

Get a vote by the given id.

#### Parameters

| Type   | Name           | Required | Description |
| ------ | -------------- | -------- | ----------- |
| string | id             | Yes      | Vote ID     |

#### Return Value

`Promise<IResponse<T>>`

## Resources\Wallets

### `all()`

```ts
public async all<T = any>(query?: Record<string, any>)
```

Get all wallets.

#### Parameters

| Type                | Name       | Required | Description      |
| ------------------- | ---------- | -------- | ---------------- |
| Record<string, any> | query      | No       | Query parameters |

#### Return Value

`Promise<IResponse<T>>`

---

### `get()`

```ts
public async get<T = any>(id: string)
```

Get a wallet by the given id.

#### Parameters

| Type   | Name           | Required | Description       |
| ------ | -------------- | -------- | ----------------- |
| string | id             | Yes      | Wallet identifier |

#### Return Value

`Promise<IResponse<T>>`

---

### `transactions()`

```ts
public async transactions<T = any>(id: string, query?: Record<string, any>)
```

Get all transactions for the given wallet.

#### Parameters

| Type                | Name  | Required | Description       |
| ------------------- | ----- | -------- | ----------------- |
| string              | id    | Yes      | Wallet identifier |
| Record<string, any> | query | Yes      | Query parameters  |

#### Return Value

`Promise<IResponse<T>>`

---

### `transactionsReceived()`

```ts
public async transactionsReceived<T = any>(id: string, query?: Record<string, any>)
```

Get all transactions received by the given wallet.

#### Parameters

| Type                | Name  | Required | Description       |
| ------------------- | ----- | -------- | ----------------- |
| string              | id    | Yes      | Wallet identifier |
| Record<string, any> | query | Yes      | Query parameters  |

#### Return Value

`Promise<IResponse<T>>`

---

### `transactionsSent()`

```ts
public async transactionsSent<T = any>(id: string, query?: Record<string, any>)
```

Get all transactions sent by the given wallet.

#### Parameters

| Type                | Name  | Required | Description       |
| ------------------- | ----- | -------- | ----------------- |
| string              | id    | Yes      | Wallet identifier |
| Record<string, any> | query | Yes      | Query parameters  |

#### Return Value

`Promise<IResponse<T>>`

---

### `votes()`

```ts
public async votes<T = any>(id: string)
```

Get all votes by the given wallet.

#### Parameters

| Type   | Name  | Required | Description       |
| ------ | ----- | -------- | ----------------- |
| string | id    | Yes      | Wallet identifier |

#### Return Value

`Promise<IResponse<T>>`

---

### `top()`

```ts
public async top<T = any>(query?: Record<string, any>)
```

Get all wallets sorted by balance in descending order.

#### Parameters

| Type                | Name  | Required | Description       |
| ------------------- | ----- | -------- | ----------------- |
| Record<string, any> | query | Yes      | Query parameters  |

#### Return Value

`Promise<IResponse<T>>`

---

### `search()`

```ts
public async search<T = any>(payload: Record<string, any>)
```

Filter all wallets by the given parameters.

#### Parameters

| Type                | Name       | Required | Description       |
| ------------------- | ---------- | -------- | ----------------- |
| Record<string, any> | payload    | Yes      | Search parameters |

#### Return Value

`Promise<IResponse<T>>`