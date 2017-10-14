# Docker image for Elixir on Ubuntu Xenial 64-bit

This contains scripts for building a Docker image that contains a lightweight
build of Erlang/OTP and Elixir based on Ubuntu Xenial 64-bit.

## Disabled Erlang apps

This build disables a lot of Erlang applications to make the final build 
smaller, so releases of the applications based on it are smaller, too. See 
[/Dockerfile](Dockerfile) for more information.

Erlang build system performs no dependency checking, but it see seems that
some of the apps have to be enabled in order to make core dependencies work
properly:

* asn1 - required by rebar,
* eunit - required by rebar3,
* common_test - required by rebar3.

## Building

If you don't want to use automated build from [Docker Hub](https://hub.docker.com/r/radiokit/elixir-light-ubuntu-xenial64)
you can type the following command in the repository's directory:

```
docker build -t radiokit/elixir-light-ubuntu-xenial64 .
```

## Versioning

The image is tagged using the following scheme:

`OTP_VERSION-ELIXIR_VERSION-REBAR_VERSION-REBAR3_VERSION-REVISION`

e.g.

`19.3.6.1-1.4.5-2.6.4-3.4.1-0`

## License

MIT

## Authors

* Marcin Lewandowski ([mspanc](https://github.com/mspanc), marcin@radiokit.org)
* Łukasz Gurdek ([ukasiu](https://github.com/ukasiu), lukasz.gurdek@swmansion.com)