# Graphite regression corpus

Documents and the images they must render, for `cargo run regression check` in the Graphite repository.

To add documents, put `.gdd` files in `ingest/` and run this from a Graphite checkout:

```sh
cargo run regression --corpus <this directory> ingest
```

Each one moves to `documents/` with new references under `references/`, and gets an entry in `corpus.json`. Commit the result. A document renders once at time zero unless a `<name>.json` next to it says otherwise, for example `{ "times": [0, 0.5, 1], "scale": 2 }`.

Old documents are the point of this repository, because they prove that migrations still reach them. Don't upgrade or replace a document here. When a change to how documents look is intended, run `bless` and commit the new references.
