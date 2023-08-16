# Runtime 2200 With Chopsticks Issue
start a chopsticks server
```
npx @acala-network/chopsticks@latest --version
0.7.3

npx @acala-network/chopsticks@latest -c acala.yml
```

then go the [polkadotjs UI](https://polkadot.js.org/apps/?rpc=ws%3A%2F%2F127.0.0.1%3A8000#/accounts), Alice should have 1000 ACA by sotrage override in config.

make a transfer from alice, and chopsticks will report
```
ERROR (rpc-author/37585): ExtrinsicFailed
  error: {
    "invalid": {
      "payment": null
    }
  }
```

as comparasion, the following two operations will succeed as expected:
- transfer with an account that originally has balance (not via storage override)
- change wasm override to use 2180, restart chopsticks, and transfer with alice

wasm is downloaded from [here](https://github.com/AcalaNetwork/Acala/issues/2581)https://github.com/AcalaNetwork/Acala/issues/2581
