#Integrating Test Results From SpecFlow+ Runner

It is now possible to integrate test results from [SpecFlow+ Runner](http://www.specflow.org/plus/runner/), a test runner specifically designed for running test cases from [SpecFlow](http://www.specflow.org). This involves some manual setup work, though: SpecFlow+ Runner outputs an HTML file that is not really suitable for automatic processing. Fortunately the template that produces the HTML file can be changed.

* Download the "official" SpecFlow+ Runner template: [http://go.specflow.org/specrunreporttemplate](http://go.specflow.org/specrunreporttemplate)
* Copy the ReportTemplate.cshtml file to the directory of the Visual Studio project that contains your SpecFlow/SpecRun scenarios (next to your .srprofile file).
* Include ReportTemplate.cshtml in your Visual Studio Project and set its "Copy to Output Directory" to "Copy if newer".
* Adapt your .srprofile file by adding the reportTemplate attribute to the Settings element:

<script src="https://gist.github.com/dirkrombauts/bb6d9cb64aa4949c4dcc.js?srprofile.xml"></script>     

* Open ReportTemplate.cshtml and add this helper before the html element:

<script src="https://gist.github.com/dirkrombauts/bb6d9cb64aa4949c4dcc.js?GetResultForPickles.js"></script>     

Still in ReportTemplate.cshtml, add this fragment before the closing /body element:

    ```
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
    ```
    
Congratulations! You have now modified the default SpecFlow+ Runner report template so that it includes additional information that will tell Pickles the results of the scenarios.

## Take Care When Using Scenario Outlines

You need to take special care when writing Scenario Outlines in order for Pickles to be able to match the results of the individual examples to the rows in the Examples table. There must be no repeated values in the first column of the examples table.

This will work:

    Examples:
      | result  | a column |
      | value 1 | 60       |
      | value 2 | 60       |

This will not work:

    Examples:
      | a column | result  |
      | 60       | value 1 |
      | 60       | value 2 |
