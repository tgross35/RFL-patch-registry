# RFL Patch Registry

This is an attempt to aggregate Rust abstractions for Linux that have not yet
been upstreamed, as well as some leaf drivers and other implementations.

Usual status options are:
- `merged`: this patch has been merged to upstream and is usable in
  recent versions of the kernel.
- `review`: this patchset has been submitted to the mailing list and is
  in a nearly usable state, pending review or other blockers.
- `RFC`: this patchset is currently collecting feedback on the mailing
  list. It is likely not too far off from being upstream ready, but may
  be blocked on not having an in-tree usecase. (some patchsets that
  would otherwise be `review` but do not have an in-tree usecase have
  been downgraded to `RFC` even if not an `RFC patch`).
- `testing`: this patchset is generally considered good for further
  experimentation and may have RFL review, but does not have review
  by relevant maintainers.
- `experimental`: this patchset is a work in progress.

Note that things change frequently and the mailing list links may not always
be the latest.

| Target Area | Status | Author | Source Link | Mailing List Link |
|---|---|---|---|---|
| crypto | RFC | Tomo | | https://lore.kernel.org/rust-for-linux/20230615142311.4055228-1-fujita.tomonori@gmail.com/ |
| DRM | RFC | Lina | | https://lore.kernel.org/rust-for-linux/20230307-rust-drm-v1-0-917ff5bc80a8@asahilina.net/ | 
| vfs | RFC | Wedson | | https://lore.kernel.org/rust-for-linux/20231018122518.128049-1-wedsonaf@gmail.com/#t |
| files | RFC | Alice + Wedson | | https://lore.kernel.org/rust-for-linux/20230720152820.3566078-1-aliceryhl@google.com/ |
| mm | | Alice + Wedson | https://github.com/Darksonn/linux/commit/7ba95d4fc5a8442ef5eb428b64109116717f7e47 | |
| null block | RFC | Andreas | | https://lore.kernel.org/rust-for-linux/20230503090708.2524310-1-nmi@metaspace.dk/ |
| phy | review | Tomo | | https://lore.kernel.org/rust-for-linux/20231026001050.1720612-1-fujita.tomonori@gmail.com/ | 
| puzzlefs | RFC | Ariel | | https://lore.kernel.org/rust-for-linux/20230726164535.230515-1-amiculas@cisco.com/ |
| rbtree | | | https://github.com/Darksonn/linux/commit/edb94cbf99f6d35bca05e052e997542f07c085ab | |
| scatterlist | RFC | | | https://lore.kernel.org/rust-for-linux/20230610104909.3202958-1-changxian.cqs@antgroup.com/ |
| socket | RFC | Michele | | https://lore.kernel.org/rust-for-linux/20230814092302.1903203-1-dallerivemichele@gmail.com/ |
| workqueue | merged | Alice | https://elixir.bootlin.com/linux/v6.7-rc1/source/rust/kernel/workqueue.rs | https://lore.kernel.org/rust-for-linux/20230828104807.1581592-1-aliceryhl@google.com/ |
| v4l2 | review | Daniel | | https://lore.kernel.org/rust-for-linux/20230406215615.122099-1-daniel.almeida@collabora.com/ |
| xarray | RFC | Lina | | https://lore.kernel.org/rust-for-linux/20230224-rust-xarray-v3-1-04305b1173a5@asahilina.net/ |


