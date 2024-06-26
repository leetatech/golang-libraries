<!-- gomarkdoc:embed:start -->

<!-- Code generated by gomarkdoc. DO NOT EDIT -->

# query

```go
import "github.com/greenbone/opensight-golang-libraries/pkg/postgres/query"
```

Package query facilitates the translation of a result selector into a PostgresSQL conditional query string, incorporating sorting and paging functionalities.

## Index

- [type Builder](<#Builder>)
  - [func NewPostgresQueryBuilder\(querySetting \*Settings\) \*Builder](<#NewPostgresQueryBuilder>)
  - [func \(qb \*Builder\) Build\(resultSelector query.ResultSelector\) \(query string, args \[\]any, err error\)](<#Builder.Build>)
  - [func \(qb \*Builder\) BuildQueryConditions\(request \*filter.Request\) \(args \[\]any, err error\)](<#Builder.BuildQueryConditions>)
- [type Settings](<#Settings>)


<a name="Builder"></a>
## type [Builder](<https://github.com/greenbone/opensight-golang-libraries/blob/main/pkg/postgres/query/builder.go#L26-L29>)

Builder represents a query builder used to construct PostgresSQL conditional query strings with sorting and paging functionalities.

```go
type Builder struct {
    // contains filtered or unexported fields
}
```

<a name="NewPostgresQueryBuilder"></a>
### func [NewPostgresQueryBuilder](<https://github.com/greenbone/opensight-golang-libraries/blob/main/pkg/postgres/query/builder.go#L32>)

```go
func NewPostgresQueryBuilder(querySetting *Settings) *Builder
```

NewPostgresQueryBuilder creates a new instance of the query builder with the provided settings.

<a name="Builder.Build"></a>
### func \(\*Builder\) [Build](<https://github.com/greenbone/opensight-golang-libraries/blob/main/pkg/postgres/query/builder.go#L118>)

```go
func (qb *Builder) Build(resultSelector query.ResultSelector) (query string, args []any, err error)
```

Build generates the complete SQL query based on the provided result selector. It constructs the query by adding filter, sorting, and paging conditions. It returns the constructed query string, and all the individual filter fields values \(args\) in a single list If any error occurs during the construction, it returns an empty string.

<a name="Builder.BuildQueryConditions"></a>
### func \(\*Builder\) [BuildQueryConditions](<https://github.com/greenbone/opensight-golang-libraries/blob/main/pkg/postgres/query/builder.go#L43>)

```go
func (qb *Builder) BuildQueryConditions(request *filter.Request) (args []any, err error)
```

BuildQueryConditions builds and appends filter conditions to the query builder based on the provided filter request. It constructs conditional clauses using the logic operator specified in the request. It uses the \`?\` query placeholder, so you can pass your parameter separately It returns all individual field values in a single list BuildQueryConditions can be used as a standalone function with Gorm

<a name="Settings"></a>
## type [Settings](<https://github.com/greenbone/opensight-golang-libraries/blob/main/pkg/postgres/query/builder.go#L20-L22>)

Settings is a configuration struct used to customize the behavior of the query builder.

```go
type Settings struct {
    FilterFieldMapping map[string]string // Mapping of filter fields for query customization
}
```

Generated by [gomarkdoc](<https://github.com/princjef/gomarkdoc>)


<!-- gomarkdoc:embed:end -->