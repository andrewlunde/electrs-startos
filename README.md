# Wrapper for Electrum Rust Server (electrs)

[electrs](https://github.com/romanz/electrs) is an efficient re-implementation of Electrum Server written in Rust. This wrapper allows electrs to integrate with other services on StartOS and exposes its config in the StartOS UI.

## Dependencies

- [docker](https://docs.docker.com/get-docker)
- [docker-buildx](https://docs.docker.com/buildx/working-with-buildx/)
- [yq](https://mikefarah.gitbook.io/yq)
- [StartSDK](https://github.com/Start9Labs/start-os/blob/master/backend/install-sdk.sh)
- [make](https://www.gnu.org/software/make/)

See the [Develper Docs](https://docs.start9.com/latest/developer-docs/packaging) for more information.

## Cloning

```
git clone https://github.com/Start9Labs/electrs-startos.git
cd electrs-startos
git submodule update --init --recursive
#checkout & build the latest version of electrs (v0.10.6 as of writing):
cd electrs
git verify-tag v0.10.6 && git checkout v0.10.6
cd ..
```

## Building

```
docker run --rm --privileged multiarch/qemu-user-static --reset -p yes -c yes
make
```

## Sideload onto StartOS

Select `System > Sideload Service` from the web UI.
