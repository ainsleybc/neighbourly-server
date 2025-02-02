# Web Socket Integration points

## All Messages

```json
{
  "name": "<message name>",
  "data": {
    "<message data>"
  }
}

```

## data structures

### Users

#### client -> server

```json
{
  "name": "user signup",
  "data": {
    "username": "<username>",
    "email": "<email>",
    "streetName": "<street name>",
    "streetNumber": "<street number>",
    "postcode": "<postcode>",
    "password": "<password>"
  }
}

{
  "name": "user login",
  "data": {
    "email": "<email>",
    "password": "<password>"
  }
}
```

#### server -> client
```json
{
  "name": "user created, logged in",
  "data": {
    "email": "<email>",
    "username": "<username>",
    "defaultFeed": "<feed id>"
  }
}

{
  "name": "login successful",
  "data": {
    "email": "<email>",
    "username": "<username>",
    "defaultFeed": "<feed id>"    
  }
}

{"name": "signup unsuccesful"}

{"name": "incorrect credentials"}

```

### Feeds

#### client -> server

```json
{
  "name": "feed add",
  "data": {
    "Address": "name"
  }
}

{
  "name": "feed subscribe"
}

{
  "name":"feedAddress add",
    "data":{
      "address":{
        "streetNumber": "<street number>",
        "streetName": "<street name>",
        "postcode": "<postcode>",
      },
      "feed":{
        "ID":"<feed id>"
      }
      }
}
```

#### server -> client

```json
{
  "name": "feed add",
  "data": {
    "ID": "<feed id>",
    "Name": "<feed name>"
  }
}
```

### Posts

#### client -> server

```json
{
  "name": "add post",
  "data": {
    "Name": "<post name>",
    "Text": "<post text>",
    "feed":{
      "id": "<feed id>"
    }
  }
}

{
  "name": "post subscribe",
  "data": {
    "feedId": "<feed id>"
    }
}

```

#### server -> client

```json
{
  "name": "add post",
  "data": {
    "ID": "<post id>",
    "CreatedAt": "<post createAt timestamp>",
    "Name": "<post name>",
    "Text": "<post text>",
    "FeedID": "<feed id>"
  }
}

```
