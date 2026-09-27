# xpeng 5.4.302 rebuild workspace (r7 topology)

This branch is the Motorola xpeng (Edge S30 / G200) **5.4.302** kernel source,
frozen from the configuration published as the
[`MMI-...-EdgeS30-r7`](https://github.com/paulcbfly/xpeng_kernel_susfs/releases/tag/MMI-5.4.302-S3RXC32.33-8-25-ReSukiSU-EdgeS30-r7)
release — the **last build that had working mobile data**.

| Item | Value |
|---|---|
| Kernel | `5.4.302-moto` |
| Features | SUSFS v2.2 + ReSukiSU inline hooks |
| Optional modules | none (no Re:Kernel / DroidSpaces / BBGuard / BBRv3) |
| Upstream commit | `b3ecce7eb4fc` of `paulcbfly/android_kernel_motorola_xpeng` |
| Branch | `5.4.302-s3rxc32.33-8-25-susfs` |

## Building

Use [`paulcbfly/xpeng_kernel_susfs_rebuild`](https://github.com/paulcbfly/xpeng_kernel_susfs_rebuild)
(branch `5.4.302-s3rxc32.33-8-25-ReSukiSU`). Its workflows already point at this
repository, so a `workflow_dispatch` run reproduces the r7 topology.

Do not build this tree with the workflows of the original
`xpeng_kernel_susfs` repository — those point at the other kernel repo.

## Cloning

```bash
git clone -b 5.4.302-s3rxc32.33-8-25-susfs \
  https://github.com/paulcbfly/android_kernel_motorola_xpeng_rebuild.git
```

65,103 files / ~838 MB of git objects. Mirror hosts such as `ghproxy.net`
stall at a fixed transfer size (~1.1 GB) on a single clone; if that happens,
use the tarball asset on the `r7-snapshot` release instead.

## Known issue

Mobile data is broken in every build **after** r7, including builds with all
optional modules disabled. This snapshot is the known-good baseline — diff
against it first.
