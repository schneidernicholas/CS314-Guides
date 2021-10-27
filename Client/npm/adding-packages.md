# Adding NPM Packages
NPM packages are a way of distributing libraries in the source code. However, each client will need to download these libraries, what's distributed is really just a list of packages to download.

There may be cases where you need to add a new package. For example, it could save you time to use [react-dropzone](https://react-dropzone.js.org/) to make a nice drag and drop uploader hook rather than having to make your own. Luckily, it's pretty simple to add a new package.

## Obtaining the Package Repo Name

To add a new package, first you need to get the repo name of the package you want to add. This can often be found in the package's documentation, or on its NPM page, where it will be the heading:
| <img width="600" alt="npm-package-page" src="https://user-images.githubusercontent.com/14037442/139160615-a6035b7f-9c36-4caf-a799-bb15d5741d3e.png"> |
|:--:| 
| *NPM page listing showing the package name, react-dropzone* |

| <img width="600" alt="documentation-page" src="https://user-images.githubusercontent.com/14037442/139160622-7914f8fd-6ca5-404f-aefb-c8f105d11c0b.png"> |
|:--:| 
| *Documentation showing the package name, react-dropzone* |

## Installing the Package

Once you have found the package repo name, you can now use an NPM command to install the package. To do so, you must first navigate to your client directory by doing:  
`cd client`

Now, run the command:  
`npm install <package-repo-name> --save`

The `--save` flag ensures that this is saved to our project's list of packages, so that other team members can install this package.

The package should now begin to install. If the package cannot be found, be sure that you have the correct package repo name. In our example, this command would end up looking like: `npm install react-dropzone --save`

## Merging & Adding to GitHub

When you go to merge your new feature that includes this new package into the GitHub repo, it will add the package to a list for everyone. They will need to run an NPM install command as well to obtain the package after getting the updated code that needs it.

1. Pull from GitHub to get the latest code and package list
2. `cd client`
3. `npm install`

After this completes, the project should now have the new package.

## Further Problems, Compilation Problems, etc.
After running this command, if you are still experiencing errors from the import, follow these steps:
1. `cd client`
2. `rm -r node_modules`
3. `rm package-lock.json`
4. Be sure you have pulled the latest changes from GitHub.
5. `npm install`

This clears all of your existing downloaded libraries and reinstalls them in an attempt to fix the problem.
