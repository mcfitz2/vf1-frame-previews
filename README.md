# vf1-frame-previews

Pictures of the frames in [`mcfitz2/vf1-frame`](https://github.com/mcfitz2/vf1-frame), so that a pull request
there can show what a change did to the shape.

Nothing here is written by hand and nothing here is a source of truth. Every file is one command away:

```
make pictures        # in vf1-frame, four PNGs per document into out/
```

## Why this repository is public

`vf1-frame` is private. GitHub renders images in comments through a proxy that never authenticates, so an
image link into a private repository comes out as a broken image — for the author as much as for anybody else.
An image that a pull request comment can display has to be readable without credentials, so it lives here.

That is the whole trade, stated plainly: **the pictures are public.** They show tube geometry, and one of the
documents is a transcription of purchased plans.

## What is in here

```
main/<name>-shaded-iso.png      the view a reviewer reads first
main/<name>-shaded-plan.png     from above
main/<name>-shaded-side.png     from the left
main/<name>-shaded-front.png    from the front
pr/<number>/…                   the same four, for an open pull request
```

`<name>` is the model's own name — `vf1-kart-chassis`, `vf1-roof-rack`, `vf1-rear-a-arm`.

Every picture is shaded, and every one is read back out of the STEP file the kernel built, so what is in the
picture is the metal with its copes cut. A document that failed to build has no picture at all, because TaC
draws solids and nothing else.

No picture verifies anything, which each one says on its own face. `make build` in `vf1-frame` is what holds a
document to what it declares.

## How long a picture lasts

- `main/` — always, replaced whenever `main` moves.
- `pr/<number>/` — while the pull request is open, and for 30 days after it closes.
- Anything else — removed at the next sweep.

The sweep rewrites this repository as a single commit and force-pushes it. Deleting a file in an ordinary
commit reclaims nothing, and there is no reason to carry every picture ever made when each one is a command
away. So **this repository has no useful history**, on purpose. Links from `vf1-frame` point at a branch and
not at a commit, so they survive that.

An old pull request whose pictures have aged out will show broken images. That is the design and not a fault.
