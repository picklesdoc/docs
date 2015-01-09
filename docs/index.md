Welcome to Pickles!
============================

Have you had your features locked up in your code too long?  Been struggling for a way to share them with your client and use them as a reference?  Interested in starting living documentation?  If so, then Pickles is for you. What better way to preserve your cukes than to pickle them !

What does it do for me?
-----------------------

Pickles was greatly influenced by the [Specification by Example](http://specificationbyexample.com/) book from Gojko Adzic and the [Relish](http://www.relishapp.com) project.  While I love the idea behind Relish I don't use Ruby and I'm on a corporate intranet so a SaaS application that is only on the internet is useless to me.  With no alternative out there, the only real option was to build one.

Pickles is very simple at heart.  You point it to a directory tree containing your feature files and it will search that tree, cataloging each .feature file it finds and converting it to HTML, storing the HTML files in a location of your choosing.  Pickles turns the plain-text feature into easy-to-read HTML that have a table of contents included so that you can easily navigate among the features.  I have plans for other features for customising the output that you would like to see.  See the [How To Contributions](HowToContribute.md) page for some ideas.

### That's all cool, but how do I run it?

See the [Getting Started](GettingStarted.md) page for more details.

There are currently several ways of running Pickles:

- [Console Application](ConsoleApplication.md)
- GUI
- [MSBuild Task](MSBuildTask.md)
- [PowerShell commandlet](PowerShellcommandlet.md)

The console application should be easy to add into any build process and the NAnt and MSBuild runners are meant to work with the most popular build tools in the .NET space right now.

Each of the runners provides a [set of arguments](Arguments.md) to let you control the output of Pickles.

### Using the Generated output

There are a lot of options available to you here for using the generated output. Here are some ideas:

1. Deploy the static HTML to any web server and allow users to access it from there, no special plugins, mods, assemblies, etc. required
-- A variant on this idea might be to create a small HTML introduction page that links to different versions of the documentation
2. Zip up the static HTML into an archive and deploy it alongside your executable

Where did it come from?
-----------------------

When I first started doing acceptance tests, I was using [FitNesse](http://www.fitnesse.org).  That worked great for a while but the wiki syntax can be limiting and it can be a real pain to include in your continuous integration workflow, especially if you're using .NET like me.  Having to start a server whenever I wanted to run tests was a little painful.

After a while I started searching for alternatives, came across [Concordion](http://www.concordion.org) and really liked it.  I liked it so much that [I ported it to .NET](https://launchpad.net/concordion-net)!  The free-form HTML seemed kind of cool and the nice way it built up an index of pages was very handy.  I was able to write the test runner so that it was easy to run the tests from either Visual Studio or a continuous integration build quite easily.  However, the rule of one fixture per page and having to write HTML was limiting.  The developers and clients did not like the idea much, unfortunately.

Then I stumbled upon [Cucumber](http://www.cukes.info/) and [SpecFlow](http://www.specflow.org/).  SpecFlow is an excellent tool.  It integrates very well with Visual Studio, provides several different test runners and is under active development.  It uses the common and easy to understand Given-When-Then syntax and builds upon the great work done by the Cucumber people. SpecFlow uses NUnit, xUnit, etc. underneath so its easy to make part of a continuous integration build.  It does have one drawback and this is that the feature files live in your Visual Studio project in source control.  Really they are only navigable from within Visual Studio.

I built Pickles to overcome this last limitation and help make SpecFlow be part of a truly living documentation system.

Contributions
-------------

See the [How to Contribute](HowToContribute.md) page.

### Steps

1. Get a Github account
2. Fork the project
3. Make your feature addition or bugfix.
4. Send us a pull request via GitHub

Acknowledgements
----------------

If you look at the source code you'll see I'm building on the shoulders of giants!  Here is a list of projects incorporated into Pickles:

- [Autofac](http://autofac.org/)
- [ClosedXML](https://closedxml.codeplex.com/)
- [Common Service Locator](https://commonservicelocator.codeplex.com/)
- [Chocolatey](https://chocolatey.org/)
- [FAKE](http://fsharp.github.io/FAKE/)
- [Fody](https://github.com/Fody/Fody) and [Costura](https://github.com/Fody/Costura)
- [Gherkin](https://github.com/cucumber/gherkin)
- [IKVM](http://www.ikvm.net/)
- [Json.NET](http://james.newtonking.com/json)
- [MahApps.Metro](http://mahapps.com/)
- [MarkdownDeep](http://www.toptensoftware.com/markdowndeep/)
- [Moq](https://github.com/Moq/moq4)
- [MvvmLight](http://www.mvvmlight.net/)
- [NDesk.Options](http://www.ndesk.org/Options)
- [NFluent](http://www.n-fluent.net/)
- [NGenerics](https://github.com/ngenerics/ngenerics)
- [NLog](http://nlog-project.org/)
- [NlogViewer](https://github.com/erizet/NlogViewer)
- [NuGet](http://www.nuget.org)
- [NUnit](http://www.nunit.org)
- [Ookii.Dialogs](http://www.ookii.org/Software/Dialogs/)
- [OpenXml](https://www.nuget.org/packages/DocumentFormat.OpenXml/)
- [SpecFlow](http://specflow.org/)
- [System.IO.Abstractions](https://github.com/tathamoddie/System.IO.Abstractions)


A big thanks to all projects as they were extremely helpful in building this project quickly and easily.

### Influences

- [FitNesse](http://www.fitnesse.org)
- [Concordion](http://www.concordion.org)