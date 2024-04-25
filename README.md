# simple-node-js-react-npm-app

This repository is for the
[Build a Node.js and React app with npm](https://jenkins.io/doc/tutorials/build-a-node-js-and-react-app-with-npm/)
tutorial in the [Jenkins User Documentation](https://jenkins.io/doc/).

The repository contains a simple Node.js and React application which generates
a web page with the content "Welcome to React" and is accompanied by a test to
check that the application renders satisfactorily.

The `jenkins` directory contains an example of the `Jenkinsfile` (i.e. Pipeline)
you'll be creating yourself during the tutorial and the `scripts` subdirectory
contains shell scripts with commands that are executed when Jenkins processes
the "Test" and "Deliver" stages of your Pipeline.

## Build instructions

- setup docker agent with below properties

```
image: 'node:lts-buster-slim'
args: '-p 3001:3001'
```
- set environment variable
```
CI = 'true'
```

- Use `npm install` for build stage

- use the script `jenkins/scripts/test.sh` in test stage

- for the deliver stage, ask for manual input from user
	- script for initiating delivery `jenkins/scripts/deliver.sh`
	- message for asking `Finished using the web site? (Click "Proceed" to continue)`
	- script for completing `jenkins/scripts/kill.sh`
