Benchmarking
============

Groestlcoin Core has an internal benchmarking framework, with benchmarks
for cryptographic algorithms (e.g. SHA1, SHA256, SHA512, RIPEMD160, Poly1305, ChaCha20), rolling bloom filter, coins selection,
thread queue, wallet balance.

Running
---------------------

For benchmarks purposes you only need to compile `groestlcoin_bench`. Beware of configuring without `--enable-debug` as this would impact
benchmarking by unlatching log printers and lock analysis.

    make -C src groestlcoin_bench

After compiling groestlcoin-core, the benchmarks can be run with:

    src/bench/bench_groestlcoin

The output will look similar to:
```
|             ns/byte |              byte/s | error % | benchmark
|--------------------:|--------------------:|--------:|:----------------------------------------------
|               64.13 |       15,592,356.01 |    0.1% | `Base58CheckEncode`
|               24.56 |       40,722,672.68 |    0.2% | `Base58Decode`
...
```

Help
---------------------

    src/bench/bench_groestlcoin --help

To print options like scaling factor or per-benchmark filter.

Notes
---------------------
More benchmarks are needed for, in no particular order:
- Script Validation
- Coins database
- Memory pool
- Cuckoo Cache
- P2P throughput
