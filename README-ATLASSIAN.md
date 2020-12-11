## Atlassian fork of yarn

This fork contains some fixes we're using at Atlassian, on the `releases/atlassian` branch.

Yarn supports putting a bundled Yarn into your repo, and this is the recommended approach. To build
a bundled version you can clone this repo and just:

```
/usr/local/bin/yarn  # otherwise it'll try and use the currently non-existent ./lib/cli/index.js
/usr/local/bin/yarn build # builds src -> lib
yarn build-bundle # builds src -> artifacts
```

There should be a fat bundle using the version number in `package.json` in `artifacts/yarn-x.y.z.js`.

## Debugging

The easiest way to debug is to do a local build (`yarn build`) and then in your repo just `node --inspect-brk /path/to/yarn/lib/cli/index.js` - if you have a `.yarnrc` with a `yarn-path` make sure you comment that out.