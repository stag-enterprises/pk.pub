# pk.

This contains the source for [pk.stag.lol], not including the actual content.
That can be found at [stag-enterprises/pk.pub].

## building

You will need [Bun] to run the build script.

To build:
```sh
bun install --frozen-lockfile
bun run build-ci
```

You can make a dev build with `bun run build`. Start a static server using
`bun run serve`.

The above will try to pull the private content source. To skip that, copy
`src/antora-playbook.yml` to `src/local-antora-playbook.yml` and remove the line
containing `pk.pv`.

## architecture

The default Antora UI bundle is downloaded and extracted into
`build/bundle-source/`. Then it is copied to `build/bundle/`, and `ast-grep`
is used to patch it. Finally Antora is ran with the playbook in `src/` and
supplementary UI in `src/ui/`.

[pk.stag.lol]: https://pk.stag.lol
[stag-enterprises/pk.pub]: https://github.com/stag-enterprises/pk.pub
[Bun]: https://bun.sh
