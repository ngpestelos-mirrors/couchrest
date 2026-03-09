# CLAUDE.md

## Tech Stack

| Component | Detail |
|-----------|--------|
| Language | Ruby |
| Framework | None (standalone gem) |
| Package Manager | Bundler |
| Test Framework | RSpec (~> 2.14) |
| License | Apache License 2.0 |

## What This Is

CouchRest is a Ruby gem that wraps CouchDB's HTTP API using persistent connections (HTTPClient). It provides a simple Hash-like interface for JSON documents and serves as a base for higher-level ORMs like CouchRest Model. Version 2.0.1.

## Prerequisites

- CouchDB running locally (default: `http://localhost:5984`)
- Ruby (tested on MRI 1.9.3+, JRuby, Rubinius)

## Common Commands

| Task | Command |
|------|---------|
| Install dependencies | `bundle install` |
| Run tests | `bundle exec rake` |
| Run specs directly | `bundle exec rspec spec/` |

## Project Structure

```
lib/couchrest.rb    → Main entry point, requires all components
lib/couchrest/      → Core library code
  server.rb         → CouchDB server connection management
  database.rb       → Database operations (CRUD, bulk, views)
  document.rb       → Document class (Hash-like interface)
  design.rb         → Design document handling
  connection.rb     → HTTP connection via HTTPClient
  rest_api.rb       → Low-level REST interface (GET/PUT/POST/DELETE)
  commands/         → CouchDB admin commands
  middlewares/      → HTTP middleware
  helper/           → Utility helpers
  support/          → Support modules
spec/               → RSpec test suite
examples/           → Usage examples
utils/              → Utility scripts
```

## Key Dependencies

- `httpclient` (~> 2.8) — persistent HTTP connections
- `multi_json` (~> 1.7) — JSON parser abstraction
- `mime-types` (>= 1.15) — MIME type detection
