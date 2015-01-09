#Integrating Test Results From SpecRun

It is now possible to integrate test results from [SpecRun](http://www.specrun.com/), a test runner specifically designed for running test cases from [SpecFlow](http://www.specflow.org). This involves some manual setup work, though: SpecRun outputs an HTML file that is not really suitable for automatic processing. Fortunately the template that produces the HTML file can be changed.

* Download the "official" SpecRun template: [http://go.specflow.org/specrunreporttemplate](http://go.specflow.org/specrunreporttemplate)
* Copy the ReportTemplate.cshtml file to the directory of the Visual Studio project that contains your SpecFlow/SpecRun scenarios (next to your .srprofile file).
* Include ReportTemplate.cshtml in your Visual Studio Project and set its "Copy to Output Directory" to "Copy if newer".
* Adapt your .srprofile file by adding the reportTemplate attribute to the Settings element:


     <?xml version="1.0" encoding="utf-16"?>
     <TestProfile xmlns="http://www.specrun.com/schemas/2011/09/TestProfile">
         <Settings reportTemplate="ReportTemplate.cshtml" />
     </TestProfile>

* Open ReportTemplate.cshtml and add this helper before the html element:

   
    @helper GetResultForPickles(TestNode testNode)
    {
        var summary = GetSummary(testNode);
        if (summary.Succeeded > 0)
        {<text>Passed</text>}
        else if (summary.TotalFailure > 0)
        {<text>Failed</text>}
        else if (summary.Ignored > 0)
        {<text>Ignored</text>}
        else if (summary.Pending > 0)
        {<text>Pending</text>}
        else
        {<text>Inconclusive</text>}
    }


* Still in ReportTemplate.cshtml, add this fragment before the closing /body element:
 

    <!-- Pickles Begin
    &lt;features&gt;
    @foreach (var fixtureNode in GetTextFixtures())
    {
        <text>&lt;feature&gt;</text>
            <text>&lt;title&gt;</text>@fixtureNode.Title<text>&lt;/title&gt;</text>
            <text>&lt;scenarios&gt;</text>
    foreach (TestNode testNode in fixtureNode.SubNodes)
    {
                <text>&lt;scenario&gt;</text>
                    <text>&lt;title&gt;</text>@testNode.Title<text>&lt;/title&gt;</text>
                    <text>&lt;result&gt;</text>@GetResultForPickles(testNode)<text>&lt;/result&gt;</text>
                <text>&lt;/scenario&gt;</text>
    }
            <text>&lt;/scenarios&gt;</text>
        <text>&lt;/feature&gt;</text>
    }
    &lt;/features&gt;
    Pickles End -->

Congratulations! You have now modified the default SpecRun report template so that it includes additional information that will tell Pickles the results of the scenarios.      