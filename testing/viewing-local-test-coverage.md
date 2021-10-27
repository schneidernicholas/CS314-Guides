# Viewing Local Test Coverage
While developing and writing tests locally, it can be helpful to view live information about each file and its test coverage.

Depending on your development environment, how you go about accessing this will differ. However, the following notes apply to everyone:
- Run the project to get an updated client and server test coverage report.
- You may need to completely stop and rerun your local build to generate a new server/client test coverage report.

## Bare Metal: Using macOS (Intel, Apple Silicon), GNU/Linux
The easiest way to access this by far is if you have your development environment on your local native OS. In this case, while the project is running, you can access the file URLs in your browser.

### Client Coverage Report
You can access the client coverage report by opening `target/coverage/client/lcov-report/index.html` with your browser. This is relative to the directory your development environment is in.

### Server Coverage Report
The server coverage report can only be accessed while the server is running. Open `target/site/jacoco/index.html` with your browser. 

## Using Docker
If you are using Docker, it is more difficult to access the test coverage because we are accessing these HTML files directly with a browser rather than through a webserver. In other words, we need a way to access the file with a browser, while the file is inside of the virtualized Docker container.

Without doing Docker filesystem mounting, the simplest way to do this is to install an extension to Visual Studio Code that will allow HTML file viewing.
[TODO: extension installation information]
[TODO: extension usage information]
### Client Coverage Report
In the tree, navigate to `target/coverage/client/lcov-report`. Now, on `index.html` [insert extension usage here]
### Server Coverage Report
In the tree, navigate to `target/site/jacoco`. Now, on `index.html` [insert extension usage here]
