# Console Application


The console application is very simple and takes two parameters: the feature directory and the output directory.  

## Crawling for features


	Pickles --feature-directory=c:\dev\my-project\my-features --output-directory=c:\my-features-output

This command will recursively search the directory c:\dev\my-project\my-features for feature files and render them as HTML, following the same folder structure, to c:\my-features-output with each feature generating a corresponding .xhtml file.

## Viewing Available Options


You can also call Pickles to see the available command-line parameters and their aliases like so

	Pickles --help

	Pickles -h

	Pickles -?

## Viewing Version Information

You can view what version of Pickles the console application is by typing

	Pickles --version

	Pickles -v
