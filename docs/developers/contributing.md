# Contributing

## Where to send changes

1. Find the right repository in the [Repository map](repos.md).
2. Use its branch: `seventeen` for Android trees, the kernel version for
   kernel trees, `main` for the rest.
3. Changes to the ROM source itself go in a fork of that project in the
   organisation, with a manifest override. They never go in the device
   tree.
4. The kernel prebuilts are only made by `auto`. Do not commit to them by
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
- No "fix the fix" commits. Fold small fixes into the commit they belong
  to before you push.
- Never commit signing keys or other secrets.

!!! warning "Force-pushes"
    Cleaning up history means force-pushing. Anyone with a clone then has
    to run `git fetch && git reset --hard origin/<branch>`.

## READMEs

Every README uses the same layout:

```
# <Part> for the Xiaomi Pad 8 Pro (piano)
```

Then: what it is, where it goes in the source tree, and where it comes
from.

## This website

Pages are Markdown files in `docs/`, built with MkDocs Material. Use the
**edit** button at the top of any page to suggest a change.

To preview locally:

```
pip install mkdocs-material
mkdocs serve
```

Keep sentences short and words plain. Number every step. Put a warning
before anything that erases data or can stop the tablet from starting.
