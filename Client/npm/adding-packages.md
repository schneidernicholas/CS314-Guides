# Adding NPM Packages
NPM packages are a way of distributing libraries in the source code. However, each client will need to download these libraries, what's distributed is really just a list of packages to download.

There may be cases where you need to add a new package. For example, it could save you time to use [react-dropzone](https://react-dropzone.js.org/) to make a nice drag and drop uploader hook rather than having to make your own. Luckily, it's pretty simple to add a new package..

## Adding a Package

To add a new package, first you need to get the repo name of the package you want to add. This can often be found in the package's documentation, or on its NPM page, where it will be the heading:
