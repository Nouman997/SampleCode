# dashboard

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## After cloning locally

In the project directory, you can run:

### `yarn`

Installs all dependencies.

### `yarn start`

Runs the app in the development mode.\
Open [http://localhost:9000](http://localhost:9000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `yarn build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.

## Local dependency development

We're using [relative-deps](https://github.com/mweststrate/relative-deps) to aid in local package development.

Clone the [packages](https://github.com/orgs/xyz/repositories?q=utils) you want to work on.

Add a `relativeDependencies` section to package.json and link to your local copies.
```
"relativeDependencies": {
  "@xyz/utils": "../packages/utils",
  "@xyz/settings": "../packages/ettings"
}
```

### `yarn prepare`

This will install the local version in the app.

When you are done with development of the local package, bump the version of the package and run:
### `npm publish`

from the local package directory.


## Pro-tip
node modules get cached. So when you make a change to a relative dep, delete `node_modules/.cache`
and run `yarn prepare` again


## Working with github packages
each dev will need a `~/.npmrc` with the contents:
```
//npm.pkg.github.com/:_authToken={your_github_token}
```

You can create this token [here](https://github.com/settings/tokens).
