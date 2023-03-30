# Yew - Axum Fullstack Web App

## Get Both Projects Running

```bash
mkdir axum-yew
cd axum-yew

# Edit Cargo.toml to have workspace with frontend, backend, and possibly common

# Create backend
cargo new backend

# Create frontend installing tools if necessary
# From yew docs example. https://yew.rs/docs/getting-started/build-a-sample-app
rustup target add wasm32-unknown-unknown
cargo install --locked trunk

# name app Frontend
cd axum
# Will print hello world
```

## Make Frontend Yew App Work

This is from the yew tutorial: https://yew.rs/docs/getting-started/build-a-sample-app.

I had to run `cargo update` and then delete `Cargo.lock` for `trunk serve` to work.
There was a version conflict.

```bash
# from workspace root
cargo generate --git https://github.com/yewstack/yew-trunk-minimal-template
cd [project name] 
trunk serve
```

Add a Trunk.toml to set port. See https://github.com/thedodd/trunk/blob/master/Trunk.toml

You should now have a working yew app with a default page.

## Make Backend Axum REST Server Work

Most of this is from https://carlosmv.hashnode.dev/creating-a-rest-api-with-axum-sqlx-rust

```bash
cargo add axum tokio serde tracing tracing-subscriber sqlx anyhow serde_json tower_http
```
