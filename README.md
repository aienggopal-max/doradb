# DoraDB

DoraDB is an experimental asynchronous Rust storage engine. It combines an in-memory row store with an on-disk column store and supports transactions, indexes, and crash recovery.

This repository is owned by [aienggopal-max](https://github.com/aienggopal-max) and is based on [jiangzhe/doradb](https://github.com/jiangzhe/doradb), created by Jiang Zhe. This README was adapted for the copy, and imported commit attribution was rewritten. The upstream repository records the original authors and contributors.

## Build from source

Use current stable Rust and Cargo on Linux with `io_uring` enabled and available to the process.

```sh
git clone https://github.com/aienggopal-max/doradb.git
cd doradb
cargo build --workspace
```

## Quick start

Run the [bundled example](doradb-storage/examples/quick_start.rs) to create a table, write and read rows in transactions, and drop the table. The example uses a temporary storage directory and prints `quick start example completed` on success.

```sh
cargo run -p doradb-storage --example quick_start
```

## Documentation

- [Public API](docs/public-api.md) and [storage architecture](docs/architecture.md)
- [Transactions](docs/transaction-system.md), [asynchronous I/O](docs/async-io.md), and [checkpoint and recovery](docs/checkpoint-and-recovery.md)
- [Benchmark tool](docs/benchmark-tool.md) and [test guide](docs/process/unit-test.md)

## License

DoraDB is available under either the [MIT License](LICENSE-MIT) or the [Apache License 2.0](LICENSE-APACHE), at your option.

Historical parser tests use SQL fixtures based on the [TPC-H specification](https://www.tpc.org/tpch/). TPC-H is a trademark of the Transaction Processing Performance Council.
