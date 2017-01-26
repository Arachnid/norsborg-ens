# norsborg-ens
This repository contains code and utilities for working with ENS on the norsborg test network.

## Getting started
Documentation on ENS can be found at [docs.ens.domains](http://docs.ens.domains/en/latest/). A minimal version of ensutils.js is provided in this repository for convenience, but you may also use the public one; everything will work with the exception of the default public resolver, which is deployed at a different address; you can access it at the ENS address `resolver.test`.

Norsborg has the `.test` registrar deployed with a first-in-first-served registration scheme. After importing `ensutils.js`, you may register a .test name with:

    testRegistrar.register(web3.sha3('myname'))

if successful, you will be the owner of `myname.eth` and may configure it as described in the [ENS docs](http://docs.ens.domains/en/latest/).

There is no .eth registrar on norsborg.

## Individuality tokens

The address on your Ether Card is associated with an individuality token for this event. This token serves as an 'I was here' marker, and after the event no more tokens can be issued. These tokens are useful for developing systems such as voting or polling contracts, where it's important to be able to avoid sibyl attacks.

The token contract is available at `0xaced90c414006b622a4b1ce74fa34b1f650ab319` on both norsborg and mainnet. On norsborg, it can be reached using the ENS name `tokens.test`. The source and ABI for the token contract are available in this repository.
