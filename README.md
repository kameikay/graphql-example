# GraphQL Example

## GraphQL Example with Go (gqlgen)

This is a simple example project showcasing the use of GraphQL in Go, specifically utilizing the gqlgen package. In this example, we focus on creating and managing courses and categories while establishing relationships between them.

## Features

- **GraphQL Implementation:** Utilizes gqlgen for efficient GraphQL implementation in Go.
- **Course Creation:** Allows for the creation of courses with relevant details.
- **Category Management:** Enables the creation of categories to organize courses effectively.
- **Relationships:** Establishes relationships between courses and their respective categories.

## Prerequisites

Before you begin, ensure you have the following dependencies installed:

- Go: [Install Go](https://golang.org/doc/install)
- gqlgen: [Install gqlgen](https://gqlgen.com/getting-started/)

## Getting Started

1. Clone the repository:

   ```bash
   git clone https://github.com/kameikay/graphql-example.git
   cd graphql-example
   ```

2. Install dependencies:

   ```bash
   go mod tidy
   ```

3. Run the GraphQL server:

   ```bash
   go run cmd/server/server.go
   ```

4. Open the GraphQL Playground:

   Navigate to [http://localhost:8080](http://localhost:8080) in your web browser to access the GraphQL Playground.

## Usage

### Creating a Course

```graphql
mutation {
  createCourse(course: {
    name: "Introduction to Go Programming"
    description: "Learn the basics of Go programming language."
    categoryId: "<category-id>"
  }) {
    id
    name
    description
    category {
      id
      name
    }
  }
}
```

### Creating a Category

```graphql
mutation {
  createCategory(category: {
    name: "Programming"
    description: "Learn how to program."
  }) {
    id
    name
    description
  }
}
```

### Querying Courses

```graphql
query {
  courses {
    id
    name
    description
    category {
      id
      name
      description
    }
  }
}
```

### Querying Categories

```graphql
query {
  categories {
    id
    name
    description
    courses {
      id
      name
      description
    }
  }
}
```

---

**Note:** Make sure to replace `<category-id>` with the actual ID of the category when creating a course.
