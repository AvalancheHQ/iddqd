# iddqd-benches

Benchmarks for iddqd.

## Running the benchmarks

Locally, with criterion:

```
cargo bench -p iddqd-benches
```

The benchmarks use [`codspeed-criterion-compat`], which is a drop-in
replacement for criterion: outside of a CodSpeed run it behaves exactly like
upstream criterion.

In CI, the same benchmarks are measured by [CodSpeed] with the CPU simulation
instrument, which produces low-variance, hardware-independent results. To
reproduce a CodSpeed run locally:

```
cargo codspeed build -p iddqd-benches
codspeed run -m simulation -- cargo codspeed run -p iddqd-benches
```

This requires [`cargo-codspeed`] and the CodSpeed CLI.

[CodSpeed]: https://app.codspeed.io/AvalancheHQ/iddqd
[`codspeed-criterion-compat`]: https://crates.io/crates/codspeed-criterion-compat
[`cargo-codspeed`]: https://crates.io/crates/cargo-codspeed
