# Release Process

We denote versions with x.y.z where x is the major version, y the minor version and z the revision number

1. Update ReleaseNotes.md to include the new release
	1. Release Number
	2. Date 
	3. New Feature(s) if any
	4. Bug(s) Fixed if any 
1. Check the version number in build.bat
1. Open a command line and run "build.bat". This will do the following:
	1. build the code
	2. run unit tests
	2. zip the runners
	3. create nuget and chocolatey packages 
	2. Unzip the files in the deploy folder by running "unzip x.y.z"
	3. Test the runners
		1. testRunnerCmd.cmd x.y.z
		2. testRunnerMsBuild.cmd x.y.z
		3. testRunnerPowerShell x.y.z
1. Create a [release](https://github.com/picklesdoc/pickles/releases/) on GitHub
   1. called vx.y.z 
   1. with release notes
   1. tag it with 'vx.y.z' on branch release
   1. Upload file "$/deploy/pickles-RUNNER-x.y.z.zip" for each RUNNER to the release
1. Generate outputs with new version and add to website (this is already done by the "test the runners" step)
1. Update the picklesdoc website to point to the new version
1. Push the nuget packages from myget to nuget gallery
2. Upload the chocolatey package to chocolatey
1. Make an announcement on pickles-dev group.
1. Tweet using @PicklesDoc
 