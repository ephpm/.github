# ePHPm

ePHPm is an all-in-one PHP application server written in Rust: it embeds PHP
via FFI into a single binary, so WordPress, Laravel, and other PHP apps run
with no external PHP-FPM. The binary also carries an embedded
SQLite-compatible database (the Turso engine), a built-in KV store, gossip
clustering, and native WebSockets. Everything here is MIT-licensed.

Docs and downloads: [ephpm.dev](https://ephpm.dev)

## The repositories

**Core**

- [ephpm](https://github.com/ephpm/ephpm) — the application server itself (flagship).
- [litewire](https://github.com/ephpm/litewire) — wire-protocol proxy (MySQL/PG/TDS/Hrana → SQLite/Turso), used by ePHPm as a library.
- [php-sdk](https://github.com/ephpm/php-sdk) — prebuilt PHP embed static libraries + headers consumed by ePHPm's build.
- [ephemerd](https://github.com/ephpm/ephemerd) — ephemeral GitHub Actions runner daemon that powers this org's CI.

**PHP packages** (Composer, installed from these repos)

- Database over the in-process bridge: [db](https://github.com/ephpm/db), [db-wordpress](https://github.com/ephpm/db-wordpress), [db-laravel](https://github.com/ephpm/db-laravel), [db-doctrine](https://github.com/ephpm/db-doctrine), [mysqli-shim](https://github.com/ephpm/mysqli-shim)
- Cache/KV: [cache](https://github.com/ephpm/cache) (PSR-6/16), [cache-symfony](https://github.com/ephpm/cache-symfony), [cache-laravel](https://github.com/ephpm/cache-laravel), [cache-wordpress](https://github.com/ephpm/cache-wordpress), [predis-connection](https://github.com/ephpm/predis-connection), [session-handler](https://github.com/ephpm/session-handler)
- Worker mode: [php-worker](https://github.com/ephpm/php-worker), [psr15-worker](https://github.com/ephpm/psr15-worker), [octane-driver](https://github.com/ephpm/octane-driver) (Laravel Octane), [wordpress-worker](https://github.com/ephpm/wordpress-worker)

**Demos and benchmarks**

- [wordpress-sample](https://github.com/ephpm/wordpress-sample) — a real WordPress on per-site Turso + KV object cache + native WebSockets.
- [wordpress-datastar](https://github.com/ephpm/wordpress-datastar) — live WordPress comments/dashboard over Datastar SSE.
- [datastar-demo](https://github.com/ephpm/datastar-demo) — Pixelboard, a multiplayer realtime demo on worker mode.
- [lab](https://github.com/ephpm/lab) — benchmark lab: ePHPm vs php-fpm/Swoole/RoadRunner.
