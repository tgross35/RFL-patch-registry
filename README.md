# RFL Patch & Project Registry

This is an attempt to aggregate Rust abstractions for Linux that have not yet
been upstreamed, as well as some leaf drivers and some other works in
progress.

Toward the bottom, there is a list of possible projects for anyone looking to
pick something up.

PRs or issues are welcome for any additions or fixes!

## Patches

Usual status options are:
- `merged`: this patch has been merged to upstream and is usable in
  recent versions of the kernel.
- `accepted`: this has been merged to a `*-next` branch
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

Base does not take prerequisites into account, check the git history for
more accurate information. A lot of experimental patchsets are against the
`rust` branch, which has a lot of abstractions that are not yet in tree.

For your development, it is best to target `rust-next`, the `*-next`
branch of the relevant subsystem, or the latest tag at
<https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git>.

Can't find something? Drop by on Zulip, we may be able to point you in the
right direction: <https://rust-for-linux.zulipchat.com/>.

Note that things change frequently! This is a best effort list, PRs or
issues are welcome if you notice something out of sync.

| Target Area | Status | Author | Git Link | Mailing List Link | Base |
|---|---|---|---|---|---|
| AArch64 support | review | Jamie | | https://lore.kernel.org/rust-for-linux/20231020155056.3495121-1-Jamie.Cunliffe@arm.com/ | |
| Loongarch support | accepted | Rui | | https://lore.kernel.org/rust-for-linux/20240108032117.215171-1-wangrui@loongson.cn/ | |
| RISC-V support | review | Conor | | https://lore.kernel.org/rust-for-linux/20230307102441.94417-1-conor.dooley@microchip.com/ | |
| x86_64 support | merged | | | | merged |
| condvar | merged | | https://elixir.bootlin.com/linux/v6.4/source/rust/kernel/sync/condvar.rs | | merged |
| crypto | RFC | Tomo | | https://lore.kernel.org/rust-for-linux/20230615142311.4055228-1-fujita.tomonori@gmail.com/ | `rust-6.5` |
| debugfs | testing | Adam | https://github.com/Rust-for-Linux/linux/pull/885 | | `rust` |
| debugfs | experimental | Fabien | https://github.com/Rust-for-Linux/linux/pull/1041 | | `rust-next` |
| delay | testing | Tomo | https://github.com/Rust-for-Linux/linux/pull/920 | | `rust` |
| device | experimental | Gary | https://github.com/nbdd0121/linux/tree/device | | |
| debugfs | experimental | Fabien | https://github.com/Fabo/linux/tree/fparent/rust-debugfs | | |
| driver | experimental | Martin, Wedson | https://github.com/YakoYakoYokuYoku/linux/commit/36d63c70f80c1f4486423d75dcc5f4b890b10dd4 | | |
| dma | testing | Tomo | https://github.com/Rust-for-Linux/linux/pull/901 | | `rust` |
| drm | RFC | Lina | | https://lore.kernel.org/rust-for-linux/20230307-rust-drm-v1-0-917ff5bc80a8@asahilina.net/ | `6.3-rc1` + extras |
| ethernet | testing | Amélie | https://github.com/Rust-for-Linux/linux/pull/1014 | | `rust` |
| file, misc | RFC | Alice, Wedson | | https://lore.kernel.org/rust-for-linux/20230720152820.3566078-1-aliceryhl@google.com/ | `rust-next` |
| file, misc | review | Alice, Wedson | | https://lore.kernel.org/rust-for-linux/20240118-alice-file-v3-0-9694b6f9580c@google.com/ | `rust-6.8` |
| fwnode | testing | Vinay | https://github.com/Rust-for-Linux/linux/pull/925 | | `rust` |
| i2c | testing | Finn | https://github.com/Rust-for-Linux/linux/pull/946 | | `rust` |
| i2c | experimental | Fabien | https://github.com/Fabo/linux/tree/fparent/rust-i2c | | `rust-next` |
| io_pgtable | testing | Lina | https://github.com/Rust-for-Linux/linux/pull/952/commits/f476b2b052165a40eed0a8fcb86b56f794ee62d8 | | `rust-next` |
| io_resource | testing | Maciej | https://github.com/Rust-for-Linux/linux/pull/682 | | `rust` |
| ioctrl | merged | | https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/rust/kernel/ioctl.rs | | merged |
| jiffies | testing | Maria | https://github.com/Rust-for-Linux/linux/pull/982 | | `rust` |
| mm | | Alice, Wedson | https://github.com/Darksonn/linux/commit/7ba95d4fc5a8442ef5eb428b64109116717f7e47 | | |
| napi | testing | Amélie | https://github.com/Rust-for-Linux/linux/pull/1018 | | `rust` |
| net_device | RFC | Tomo | | https://lore.kernel.org/netdev/20230613045326.3938283-1-fujita.tomonori@gmail.com/ | `rust-6.5` |
| null block | RFC | Andreas | | https://lore.kernel.org/rust-for-linux/20230503090708.2524310-1-nmi@metaspace.dk/ | `rust-6.4` |
| of | experimental | AsahiLinux | https://github.com/AsahiLinux/linux/blob/gpu/rust-for-later/rust/kernel/of.rs | | |
| pci | testing | Tomo | https://github.com/Rust-for-Linux/linux/pull/856 | | `rust` |
| phy | merged | Tomo | https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/rust/kernel/net/phy.rs | https://lore.kernel.org/rust-for-linux/20231026001050.1720612-1-fujita.tomonori@gmail.com/ | merged |
| platform | testing | Rust GH | https://github.com/Rust-for-Linux/linux/blob/rust/rust/kernel/platform.rs | | `rust` |
| pm_runtime | testing | Maciej | https://github.com/Rust-for-Linux/linux/pull/700 | | `rust` |
| puzzlefs | RFC | Ariel | | https://lore.kernel.org/rust-for-linux/20230726164535.230515-1-amiculas@cisco.com/ | `puzzlefs_dependencies` |
| ramfs | abandoned | Fox | https://github.com/Rust-for-Linux/linux/pull/409 | | `rust` |
| rbtree | testing | | https://github.com/Darksonn/linux/commit/edb94cbf99f6d35bca05e052e997542f07c085ab | | |
| regmap | experimental | Fabien | https://github.com/Fabo/linux/tree/fparent/rust-regmap-dev | | |
| regulator/consumer | experimental | Fabien | https://github.com/Rust-for-Linux/linux/pull/1040 | | `rust-dev` |
| reset | testing | Nikos | https://github.com/Rust-for-Linux/linux/pull/933 | | `rust` |
| rtkit (apple) | testing | Lina | https://github.com/Rust-for-Linux/linux/pull/952/commits/f7708d02efab0d96e56f78d7e6dfa56adc948ef4 | | `rust-next` |
| scatterlist | RFC | Fox | | https://lore.kernel.org/rust-for-linux/20230610104909.3202958-1-changxian.cqs@antgroup.com/ | |
| schedule | testing | Boqun | https://github.com/Rust-for-Linux/linux/pull/861 | | `rust` |
| sk_buf | RFC | Tomo | | https://lore.kernel.org/netdev/20230613045326.3938283-1-fujita.tomonori@gmail.com/ | `rust-6.5` |
| socket | RFC | Michele | | https://lore.kernel.org/rust-for-linux/20230814092302.1903203-1-dallerivemichele@gmail.com/ | `rust-next` |
| spi | testing | Esteban | https://github.com/Rust-for-Linux/linux/pull/264 | | `rust-next` |
| sysfs | testing | Martin | https://github.com/YakoYakoYokuYoku/linux/commits/sysfs-support | | |
| tarfs | testing | Wedson | https://github.com/Rust-for-Linux/linux/pull/1037 | | `rust-next` |
| task | merged | | https://elixir.bootlin.com/linux/v6.4/source/rust/kernel/task.rs | | merged |
| timer | testing | Maria | https://github.com/Rust-for-Linux/linux/pull/982 | | `rust` |
| thread | testing | Boqun | https://github.com/Rust-for-Linux/linux/pull/109 | | `rust` |
| usb | testing | Martin | https://github.com/Rust-for-Linux/linux/pull/884 | | `rust` |
| virtio | testing | Richard | https://github.com/Rust-for-Linux/linux/pull/886 | | `rust` |
| workqueue | merged | Alice | https://elixir.bootlin.com/linux/v6.7/source/rust/kernel/workqueue.rs | https://lore.kernel.org/rust-for-linux/20230828104807.1581592-1-aliceryhl@google.com/ | merged |
| v4l2 | review | Daniel | | https://lore.kernel.org/rust-for-linux/20230406215615.122099-1-daniel.almeida@collabora.com/ | `rust` |
| vfs | RFC | Wedson | | https://lore.kernel.org/rust-for-linux/20231018122518.128049-1-wedsonaf@gmail.com/#t | |
| xarray | RFC | Maíra, Lina | | https://lore.kernel.org/rust-for-linux/ZacW_e1mnNi6hT7M@boqun-archlinux/T/#m7231cc4d238de3930f1092dd1ab123c4ffe2315a | `rust-next` |
| apple misc items | testing | Lina | https://github.com/Rust-for-Linux/linux/pull/964 | | `rust-next` |
| C+Rust kbuild system | experimental | Miguel | not yet published | | |

<!-- | | | | | | | -->

If what you need still isn't listed here, take a look at these trees:

- https://github.com/AsahiLinux/linux uses Rust pretty heavily in production
- https://github.com/Rust-for-Linux/linux/tree/rust is the experimental tree
  used before merging into mainline. A lot of experimental bindings are
  available there.

# Project Board

Below is a small list of larger projects that may be wanted in-tree. Before
starting any work, drop by [on Zulip](https://rust-for-linux.zulipchat.com/)
or at the mailing list to see if anybody is working on it already.

| Area | Task | Discussion | Notes |
|---|---|---|---|
| fs | ext2 file system | https://rust-for-linux.zulipchat.com/#narrow/stream/288089-General/topic/ext2.20filesystem, https://rust-for-linux.zulipchat.com/#narrow/stream/288089-General/topic/open.20Github.20issues.20are.20nearly.20all.20merged.20and.20solved.2E, https://lwn.net/Articles/952029/ | Reply to the Zulip topic if interested, this may wind up being a collaboration |
| graphics | rewrite the Nouveau driver in Rust | https://rust-for-linux.zulipchat.com/#narrow/stream/288089-General/topic/Nouveau.20in.20LWN, https://lwn.net/Articles/953144/| Reply to the Zulip topic if interested |
| phy | Microchip VSC825{4,6,7,8} phy driver |  | Open a Zulip topic and tag Shashwat and Trevor if interested (or email the list) |
| phy | other phys |  | Any phys that are not yet supported by the kernel may be willing to accept Rust drivers |
| tc | ? |  | Traffic control expressed interest in using Rust, need to figure out exactly where... |

Aside from these larger projects, there are other ways to get involved:

- Work on issues listed in the GitHub tracker:
  <https://github.com/Rust-for-Linux/linux/issues>.
- Provide reviews on the mailing list.
- Build and test mailing list patchsets.
- Support development of ecosystem tools (rustc, rustdoc, bindgen, etc.). RFL
  tracks some wanted features in GitHub meta issues:
  <https://github.com/Rust-for-Linux/linux/issues?q=is%3Aissue+is%3Aopen+wanted+features+label%3Ameta>
- Reach out to hardware manufacturers and see if they are interested in new
  drivers.
- Help get Rust support working and tested on more platforms.
- Write about RFL. Tutorials and good documentation help lower the barrier to
  entry.
