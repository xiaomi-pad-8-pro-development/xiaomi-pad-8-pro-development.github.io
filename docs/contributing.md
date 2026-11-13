# Contributing

## Where to send changes

- Each part has its own repository. See [Repositories](repos.md).
- Android trees use the branch `seventeen`. Kernel trees are named after
  the kernel version (`6.6`, `6.12`).
- Changes to the ROM source itself go in a fork of that project in the
  organisation, not in the device tree.
- The kernel prebuilts are only made by `auto`. Do not commit to them by
  hand.

## Commit style

Use the LineageOS style: a short subject that starts with the part you
change.

```
piano: Add the FourSemi speaker calibration library
sm8750-common: Drop an unused service
README: Add OrangeFox and the tree path
```

- One commit per logical change.
- No "fix the fix" commits: fold small fixes into the commit they belong
  to before you push.
- Never commit signing keys or other secrets.

## READMEs

Every README follows the same layout:

```
# <Part> for the Xiaomi Pad 8 Pro (piano)
```

then what it is, where it goes in the source tree, and where it comes
from.
