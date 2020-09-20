# Suave GraphQL Sample using .NET 5

[Suave](https://suave.io) is a full async stand alone web server developed in [F#](https://fsharp.org).

[GraphQL](https://graphql.org) is an open-source data query and manipulation language for APIs.

This project is a sample showing how to use GraphQL on Suave using [.NET 5](https://devblogs.microsoft.com/dotnet/introducing-net-5).

## How to use?

On the terminal run with:

```
cd src/App
dotnet run
```

The server with start on the address `http://127.0.0.1:8080`.

## Queries

With a GraphQL client you can test with the follow queries:

```graphql
query {
    viewer {
      id
      name
      age
    }
}
```

Query with fragments:

```graphql
fragment userFragment on User {
    widgets(first: 10) {
        edges {
            node {
                id
                name
            }
        }
    }
}
  
query {
    viewer {
        ...userFragment
    }
}
```

## Acknowledgments

This project is based on the [FSharp.Data.GraphQL](https://github.com/fsprojects/FSharp.Data.GraphQL) samples.

