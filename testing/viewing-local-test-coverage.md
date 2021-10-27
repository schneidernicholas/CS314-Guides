# Viewing Local Test Coverage
While developing and writing tests locally, it can be helpful to view live information about each file and its test coverage.

Depending on your development environment, how you go about accessing this will differ. However, the following notes apply to everyone:
- Run the project to get an updated client and server test coverage report.
- You may need to completely stop and rerun your local build to generate a new server/client test coverage report.
- The build must be running in order for the server test coverage files to be there.

Choose the set of guide instructions below for the development environment you are using.

## Using Bare Metal: macOS (Apple Silicon, Intel), GNU/Linux
This is the easiest way to access the test coverage reports because the files are on your native OS. In this case, while the project is running, you can access the file URLs in your browser.

### Client Coverage Report
You can access the client coverage report by opening `target/coverage/client/lcov-report/index.html` with your browser. This is relative to the directory your development environment is in.

### Server Coverage Report
The server coverage report can only be accessed while the server is running. Open `target/site/jacoco/index.html` with your browser. 

## Using Docker
With Docker, it is more difficult to access the test coverage because the files are inside of a Docker container. This means that we have to find a way to access those files with a browser.

Without doing Docker filesystem mounting, the simplest way to do this is to install an extension to Visual Studio Code that will allow HTML file viewing.
[TODO: extension installation information]
[TODO: extension usage information]
### Client Coverage Report
In the tree, navigate to `target/coverage/client/lcov-report`. Now, on `index.html` [insert extension usage here]
### Server Coverage Report
In the tree, navigate to `target/site/jacoco`. Now, on `index.html` [insert extension usage here]
