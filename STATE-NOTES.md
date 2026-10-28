# State notes — ffmpeg-rockchip (updated 2026-10-28)

## Lines
- Local `master` (tip 129a3cf0d7) = working line based on origin/8.1 (b187bf5276),
  ~592 local commits on top. Contains rkmpp EOS fixes. Installed to
  /usr/local/lib (libavcodec.so.62.28.103). Production apps link against this.
  Do NOT rebase/delete without a plan.
- Fork branch `xdc-rkmpp-eos-fixes-v2` (a9f8736d02) = nyanmisaka master
  + 2 cherry-picked EOS commits. PR #273 -> nyanmisaka/ffmpeg-rockchip,
  mergeable: clean. Built in-tree only for tests (LD_LIBRARY_PATH).
- `backup-old-master` (897b4e6f62) = safety snapshot. Keep.

## Installs
- /usr/local/lib/libavcodec.so.62.28.103 (2026-10-28 11:44) — 8.1.3 line.
  Stale .102 removed same day.
- In-tree builds are never installed without explicit decision.

## App
- ~/Projects/light/light_ai rebuilt against installed .103 (pkg-config
  shows libavcodec 62.28.103). ldd confirms /usr/local/lib/libavcodec.so.62.

## TODO
- Re-evaluate which of the ~592 local master commits are already covered by
  upstream fixes; plan rebase of the 8.1.3 line onto a newer base.
- Decide when/whether to move system install from 8.1.3 line to
  nyanmisaka master line (PR #273 outcome is the reference).
- Note: myfork/master currently also points at 129a3cf0d7 (pushed during
  EOS-fix session); keep in mind when comparing remotes.
