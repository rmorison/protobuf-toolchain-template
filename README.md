# Build template for Protobuf based applications

## Tl;dr

With [go](https://go.dev/) version >= 1.20 installed (The
[g](https://github.com/stefanmaric/g) Go version manager
recommended)...

```shell
git clone git@github.com:rmorison/protobuf-toolchain-template.git
make
./greeter_server/main &
./greeter_client/main
./greeter_client/main --name everybody
```

## Customizing for your project

1. Replace `GO_PACKAGE` in Makefile with your package path.
2. Add your `.proto` files like `proto/myproto/myproto.proto` and set
   `option go_package` appropriately. (See
   [helloworld.proto](https://github.com/rmorison/protobuf-toolchain-template/blob/main/proto/helloworld/helloworld.proto)
   for example.)
3. Update `PROTO_FILES` with a list of paths to your `.proto` files.
4. Replace `all` targets in Makefile with what you're building. [I
   like to construct CLI apps with [Cobra](https://cobra.dev/), though
   this template does not take that approach as the client and server
   code comes from the [grpc-go helloworld
   example](https://github.com/grpc/grpc-go/tree/master/examples/helloworld)].
