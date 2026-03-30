# remove-dep

This reproduces a bug where:

When an installed package (in this case vite) has dependencies removed using `yarn patch` (in this case, all dependencies) they are still resolved and installed (see `yarn.lock`).

To demonstrate:

1. clone this repo
2. run `rm -rf .yarn/cache .yarn/unplugged .pnp* .yarn/install-state.gz yarn.lock`
3. run `yarn install`
4. observe dependencies present in `.yarn/cache`, `.yarn/unplugged`, `yarn.lock`. `.pnp.cjs`
