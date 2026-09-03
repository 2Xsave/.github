# 2Xsave

Rust libraries for downloading publicly accessible media from social platforms.

Each platform has its own crate with the same shape: a small async core that you can use
as a Rust library, as a command-line tool, or as a Python module through PyO3.

## Projects

| Platform | Repository | Interfaces |
| --- | --- | --- |
| TikTok — video, photo carousels, audio | [`ttsave`](https://github.com/2Xsave/ttsave) | Library · CLI · Python |
| Instagram — reels, posts, carousels | [`insave`](https://github.com/2Xsave/insave) | Library · CLI · Python |
| Threads — video, photo carousels | [`trsave`](https://github.com/2Xsave/trsave) | Library · CLI · Python |
| X (Twitter) — video, photos, text posts | [`twsave`](https://github.com/2Xsave/twsave) | Library · Python |
| SoundCloud — MP3 tracks | [`sksave`](https://github.com/2Xsave/sksave) | Library · CLI · Python |
| Shared configuration, HTTP and types | [`2xsave_common`](https://github.com/2Xsave/2xsave_common) | Library |
| Terminal UI over all five cores | [`2XsaveTUI`](https://github.com/2Xsave/2XsaveTUI) | Application |

## Status

Everything here is version `0.1.0` and nothing is published to crates.io yet. The public
API still changes between commits, so depend on the git repositories directly and pin a
revision if you need stability.

```toml
[dependencies]
ttsave_core = { git = "https://github.com/2Xsave/ttsave", rev = "..." }
```

## How the crates are put together

```
                         2xsave_common
       shared config loading, HTTP client, common types
                               |
     +------------+------------+------------+------------+
     |            |            |            |            |
ttsave_core  insave_core  trsave_core  twsave_core  sksave_core
     |            |            |            |            |
     +------------+------------+------------+------------+
                               |
                           2XsaveTUI
              terminal UI driving all five cores
```

Every core works as a Rust library and as a Python module built with maturin; all of
them except `twsave_core` also ship a CLI binary. Each one exposes the same two entry
points: `execute_download` writes files to disk, `execute_download_binary` keeps the
media in memory. Configuration comes from a JSON file and environment variables, with
environment variables taking priority.

`2xsave_common` holds what would otherwise be copied between crates: `RuntimeConfig`,
the User-Agent constants, the HTTP client builder, and the shared PyO3 boilerplate.

## Roadmap

- Apple Music (`amsave`) — researching the web player API
- Spotify (`spsave`) — metadata parsing
- A single CLI wrapper over all cores
- An optional HTTP proxy server around the cores

## Scope

These tools fetch content that is already publicly accessible, for personal and
educational use. They do not break DRM or paywalls, do not touch private accounts or
user data, and are not built for bulk scraping.

Downloading someone else's content can still violate a platform's terms of service or
local copyright law. That part is on you.

## License

MIT.
