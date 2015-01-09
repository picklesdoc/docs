# How To Contribute

If you like Pickles and want to contribute by all means fork the project and send me a pull request!

## Ideas


- I'm no visual designer!  What CSS layout is provided in the rendered HTML files is cobbled together from small CSS tutorials I could find on the interwebs.  If there's a CSS designer out there willing to donate some time to help improve the theme of the rendered HTML files, or even create a set of themes that the user can choose from that would be greatly appreciated.

- Additional documentation builders would be great.  I plan to add the .docx format as an output in the future and perhaps .pdf as well.  If there are other formats you would like to see the features rendered in then by all means create one and send me a pull request or add an issue on the issues page.

- Tasks for other build tools would be a great addition.
	- Rake
	- Psake
	- Others?

- Mono support so that we can run on Linux and Mac systems.

- NuGet package
	- I guess this could use the MSBuild test runner to integrate Pickles into the build process as a post-build step that has some pre-defined parameters (output folder is bin\Debug\docs, features folder is .\Features, etc.)

- Chocolatey nuget package (to install the command-line executable)

- Nice installer package that installs the console app, MSBuild task, NAnt task and some example projects.