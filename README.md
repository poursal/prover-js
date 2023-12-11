# Prover JS library

A reference library for building Javascript applications using the [Prover documentation](https://github.com/poursal/prover).

## Introduction

Using this library you can respond to Proof-of-Work challenges provided by a service (ie your API).

## Installation with npm

Quick and simple:
```bash
npm install prover-js --save
```

## Usage

The following example illustrates how to use Prover. You will need also a nonce generator like the following:
- [Incremental nonce generator](https://github.com/poursal/prover-js-inonce)
- [Random nonce generator](https://github.com/poursal/prover-js-rnonce)

```javascript
const oratush = require('prover-js');
const nonce = require('prover-js-rnonce'); // We also need a nonce generator

const difficulty = 8; // This is provided by the server
const data = new Uint8Array(32); // Also provided by the server
window.crypto.getRandomValues(data);

oratush.prover.process(difficulty, data, nonce).then((value) => {
    console.log(value);
});
```

## Copyright and license

Copyright 2023 Vassilis Poursalidis. Released under Apache 2.0 - see the `LICENSE` file for details.
