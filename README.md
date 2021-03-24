# ClarionOS

-   Introduction: https://github.com/bytemaster/clarion/discussions/2
-   Discussions: https://github.com/bytemaster/clarion/discussions
-   Telegram: https://t.me/clarionos

## Build

Set the `WASI_SDK_PREFIX` environment variable before building (see architecture-specific instructions below). Alternatively, use cmake's `-DWASI_SDK_PREFIX=....` option. Also make sure `nodejs 14`, `npm 6.14`, and `yarn 1.22` are in your path.

```sh
git submodule update --init --recursive
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
make -j

ctest -j10
CLARION_WASM_PATH=a.wasm node dist/clariond

# to run the dev environment (it spins up and watches the PWA and ClarionD)
make dev
# open your browser on http://localhost:9025
```

