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
- `abandoned`: not recently maintained

Note that things change frequently and the mailing list links may not always
be the latest.

| Target Area | Status | Author | Git Link | Mailing List Link |
|---|---|---|---|---|
| crypto | RFC | Tomo | | https://lore.kernel.org/rust-for-linux/20230615142311.4055228-1-fujita.tomonori@gmail.com/ |
| debugfs | testing | Adam | https://github.com/Rust-for-Linux/linux/pull/885 | |
| debugfs | experimental | Fabien | https://github.com/Rust-for-Linux/linux/pull/1041 | |
| delay | testing | Tomo | https://github.com/Rust-for-Linux/linux/pull/920 | |
| device | experimental | Gary | https://github.com/nbdd0121/linux/tree/device | |
| driver | experimental | Martin, Wedson | https://github.com/YakoYakoYokuYoku/linux/commit/36d63c70f80c1f4486423d75dcc5f4b890b10dd4 | |
| dma | testing | Tomo | https://github.com/Rust-for-Linux/linux/pull/901 | |
| drm | RFC | Lina | | https://lore.kernel.org/rust-for-linux/20230307-rust-drm-v1-0-917ff5bc80a8@asahilina.net/ |
| ethernet | testing | Amélie | https://github.com/Rust-for-Linux/linux/pull/1014 | |
| file | RFC | Alice + Wedson | | https://lore.kernel.org/rust-for-linux/20230720152820.3566078-1-aliceryhl@google.com/ |
| fwnode | testing | Vinay | https://github.com/Rust-for-Linux/linux/pull/925 | |
| i2c | testing | Finn | https://github.com/Rust-for-Linux/linux/pull/946 | |
| io_pgtable | testing | Lina | https://github.com/Rust-for-Linux/linux/pull/952/commits/f476b2b052165a40eed0a8fcb86b56f794ee62d8 | |
| io_resource | testing | Maciej | https://github.com/Rust-for-Linux/linux/pull/682 | |
| jiffies | testing | Maria | https://github.com/Rust-for-Linux/linux/pull/982 | |
| mm | | Alice, Wedson | https://github.com/Darksonn/linux/commit/7ba95d4fc5a8442ef5eb428b64109116717f7e47 | |
| napi | testing | Amélie | https://github.com/Rust-for-Linux/linux/pull/1018 | |
| net_device | RFC | Tomo | | https://lore.kernel.org/netdev/20230613045326.3938283-1-fujita.tomonori@gmail.com/ |
| null block | RFC | Andreas | | https://lore.kernel.org/rust-for-linux/20230503090708.2524310-1-nmi@metaspace.dk/ |
| pci | testing | Tomo | https://github.com/Rust-for-Linux/linux/pull/856 | |
| phy | review | Tomo | | https://lore.kernel.org/rust-for-linux/20231026001050.1720612-1-fujita.tomonori@gmail.com/ | 
| pm_runtime | testing | Maciej | https://github.com/Rust-for-Linux/linux/pull/700 | |
| puzzlefs | RFC | Ariel | | https://lore.kernel.org/rust-for-linux/20230726164535.230515-1-amiculas@cisco.com/ |
| ramfs | abandoned | Fox | https://github.com/Rust-for-Linux/linux/pull/409 | |
| rbtree | testing | | https://github.com/Darksonn/linux/commit/edb94cbf99f6d35bca05e052e997542f07c085ab | |
| regulator/consumer | experimental | Fabien | https://github.com/Rust-for-Linux/linux/pull/1040 | |
| reset | testing | Nikos | https://github.com/Rust-for-Linux/linux/pull/933 | |
| rtkit (apple) | testing | Lina | https://github.com/Rust-for-Linux/linux/pull/952/commits/f7708d02efab0d96e56f78d7e6dfa56adc948ef4 | |
| scatterlist | RFC | Fox | | https://lore.kernel.org/rust-for-linux/20230610104909.3202958-1-changxian.cqs@antgroup.com/ |
| schedule | testing | Boqun | https://github.com/Rust-for-Linux/linux/pull/861 | |
| sk_buf | RFC | Tomo | | https://lore.kernel.org/netdev/20230613045326.3938283-1-fujita.tomonori@gmail.com/ |
| socket | RFC | Michele | | https://lore.kernel.org/rust-for-linux/20230814092302.1903203-1-dallerivemichele@gmail.com/ |
| spi | testing | Esteban | https://github.com/Rust-for-Linux/linux/pull/264 | |
| tarfs | testing | Wedson | https://github.com/Rust-for-Linux/linux/pull/1037 | |
| timer | testing | Maria | https://github.com/Rust-for-Linux/linux/pull/982 | |
| thread | testing | Boqun | https://github.com/Rust-for-Linux/linux/pull/109 | |
| usb | testing | Martin | https://github.com/Rust-for-Linux/linux/pull/884 | |
| virtio | testing | Richard | https://github.com/Rust-for-Linux/linux/pull/886 | |
| workqueue | merged | Alice | https://elixir.bootlin.com/linux/v6.7-rc1/source/rust/kernel/workqueue.rs | https://lore.kernel.org/rust-for-linux/20230828104807.1581592-1-aliceryhl@google.com/ |
| v4l2 | review | Daniel | | https://lore.kernel.org/rust-for-linux/20230406215615.122099-1-daniel.almeida@collabora.com/ |
| vfs | RFC | Wedson | | https://lore.kernel.org/rust-for-linux/20231018122518.128049-1-wedsonaf@gmail.com/#t |
| xarray | RFC | Lina | | https://lore.kernel.org/rust-for-linux/20230224-rust-xarray-v3-1-04305b1173a5@asahilina.net/ |
| apple misc items | testing | Lina | https://github.com/Rust-for-Linux/linux/pull/964 | |

<!-- | | | | | | -->
