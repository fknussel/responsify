# responsify

Responsify Mixin for Less.

## Install

```
npm install --save-dev responsify
```

## Usage

Adjust the variables on the `src/responsify.less` file to match your design and then write your media queries on variables, like this:

```
.about {
  width: 100%;
}

@sm: {
  .about {
    width: 50%;
  }
};

@lg: {
  .about {
    display: none;
  }
};
```

Once you are done writing styles for each breakpoint, include the responsify mixin and pass in all of these variables you've just created:

```
.responsify({}, @sm, {}, @lg, {});
```

The responsify mixin expects the following arguments to get passed in:

1. `@xs`: larger than mobile
2. `@sm`: larger than phablet
3. `@md`: larger than tablet
4. `@lg`: larger than desktop
5. `@xl`: larger than desktop HD

Use `{}` if you don't have styles defined for that particular breakpoint. Note that, since this is mobile first, styles will *cascade up* if no styles get passed in for one of the breakpoints.

## Release Versions

This repo uses [grunt-bump](https://github.com/gruntjs/grunt-bump) and Semantic Versioning to version and tag releases. To release a new version, run the appropriate command:

```
grunt release:major       # bump major version, eg. 1.0.2 -> 2.0.0
grunt release:minor       # bump minor version, eg. 0.1.3 -> 0.2.0
grunt release:patch       # bump patch version, eg. 0.0.1 -> 0.0.2
grunt release:prerelease  # bump pre-release version, eg. 1.0.0 -> 1.0.0-1
```

Make sure to push tags:

```
git push --tags origin master
```

Publish the package to [npm's public registry](https://www.npmjs.com/):

```
npm publish
```

To make sure everything worked just fine, go to [http://npmjs.com/package/responsify](http://npmjs.com/package/responsify).

**Heads up!** To publish, you must have a user on the npm registry. If you don't have one, create it with `npm adduser`. If you created one on the site, use `npm login` to store the credentials on the client. You can use `npm config ls` to ensure that the credentials are stored on your client. Check that it has been added to the registry by going to [http://npmjs.com/~](http://npmjs.com/~).

## Semantic Versioning

Given a version number `MAJOR.MINOR.PATCH`, increment the:

1. `MAJOR` version when you make incompatible API changes,
2. `MINOR` version when you add functionality in a backwards-compatible manner, and
3. `PATCH` version when you make backwards-compatible bug fixes.

Additional labels for pre-release and build metadata are available as extensions to the `MAJOR.MINOR.PATCH` format.

See the [Semantic Versioning](http://semver.org/) specification for more information.

## Release History

See the [CHANGELOG](CHANGELOG.md).
