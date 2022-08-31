# Protocol Buffers

## How do Protocol Buffers Work?

![Figure 1. Protocol buffers workflow](https://developers.google.com/static/protocol-buffers/docs/images/protocol-buffers-concepts.png )

Figure 1. Protocol buffers workflow

```
message Person {
  optional string name = 1;
  optional int32 id = 2;
  optional string email = 3;
}
```

```
Person john = Person.newBuilder()
    .setId(1234)
    .setName("John Doe")
    .setEmail("jdoe@example.com")
    .build();
output = new FileOutputStream(args[0]);
john.writeTo(output);
```

```
Person john;
fstream input(argv[1], ios::in | ios::binary);
john.ParseFromIstream(&input);
int id = john.id();
std::string name = john.name();
std::string email = john.email();
```

# 참고

- [https://developers.google.com/protocol-buffers](https://developers.google.com/protocol-buffers)
- [https://ko.wikipedia.org/wiki/%ED%94%84%EB%A1%9C%ED%86%A0%EC%BD%9C_%EB%B2%84%ED%8D%BC](https://ko.wikipedia.org/wiki/%ED%94%84%EB%A1%9C%ED%86%A0%EC%BD%9C_%EB%B2%84%ED%8D%BC)