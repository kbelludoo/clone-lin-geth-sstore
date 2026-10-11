# clone-lin-geth-sstore

Experimental i64-scale LIN clone of [ethereum/go-ethereum](https://github.com/ethereum/go-ethereum) tag `v1.16.9` `makeGasSStoreFunc` / EIP-3529 SSTORE (`core/vm/operations_acl.go`, LGPL-3.0).

- **LIN clone:** [`src/lin_geth_sstore.lin`](src/lin_geth_sstore.lin)
- **Proofs (results only) live in lin-open:** https://github.com/kbelludoo/lin-open/tree/master/examples/geth_sstore
- **Event receipt:** `docs/events/EVENT_GETH_SSTORE_CLONE_LIN.rulel` in lin-open

This repository is the standalone LIN copy. It is **not** a Geth node and does **not** claim Ethereum consensus or the EIP-3529 1/5 refund cap.

Canonical goldens (warm unless noted):

- first-credit cold `0->nonzero` = **22100**
- create warm = **20000**
- clean delete warm = **2900** gas + **4800** refund (`5000-2100+1900`)
- recreate original = **100** gas + **-2000** refund
- sentry `gas_left<=2300` fail-closes to **0**
