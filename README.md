1. [GraphQL Server Basics: GraphQL Schemas, TypeDefs & Resolvers](https://www.prisma.io/blog/graphql-server-basics-the-schema-ac5e2950214e)
2. [GraphQL Server Basics: The Network Layer](https://www.prisma.io/blog/graphql-server-basics-the-network-layer-51d97d21861)

## The GraphQL schema defines the server’s API

### The Schema Definition Language(SDL)
GraphQL schemas are written in its own type language called Schema Definition Language(SDL).

Root types of GraphQL Schema are `Query`, `Mutation`, `Subscription`, which adds functionality to the API.

```
query {
  user(id: "abc") {
    id
    name
  }
}

type Query {
  user(id: ID!): User
}

type User {
  id: ID!
  name: String
}
```
`query` is valid only if the corresponding GraphQL schema defines the root `Query` type with `user` field.

`User` type simple defines the structure of a user model in the application.

GraphQL schema's root types determine the shape of the queries and mutations that will be accepted by the server.

GraphQL schema provides a clear contract for client-server communication.

### The GraphQLSchema object is the core of a GraphQL Server
