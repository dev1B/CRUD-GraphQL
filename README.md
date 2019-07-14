# CRUD-GraphQL

[http://localhost:3500/graphql](http://localhost:3500/graphql)

```graphql
query User($userId: Int!) {
  user (id: $userId) {
    id
    name
    friends {
      id
      name
    }
  }
}

query UsersAndFriends {
  users {
    id
    name
    friends {
      id
      name
    }
  }
}

mutation CreateUser($input: CreateUserInput!) {
  createUser(input: $input) {
    id
    name
    email
    age
    friends {
      id
      name
    }
  }
}

mutation UpdateUser($id: Int!, $input: CreateUserInput!) {
  updateUser(id: $id, input: $input) {
    id
    name
    email
    age
    friends {
      id
      name
    }
  }
}

mutation DeleteUser($toRemoveId: Int!) {
  deleteUser(id: $toRemoveId) {
    id
    name
    email
    age
    friends {
      id
      name
    }
  }
}
```
### Query Variables
```json
{
  "userId": 14,
  "toRemoveId": 0,
  "id": 1,
  "input": {
    "name": "Bohdan",
    "email": "Bohdan@gmail.com",
    "age": 22,
    "friends": [ 1,2 ]
  }
}
```