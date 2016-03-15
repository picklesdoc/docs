#Integrating Test Results From SpecFlow+ Runner

It is now possible to integrate test results from [SpecFlow+ Runner](http://www.specflow.org/plus/runner/), a test runner specifically designed for running test cases from [SpecFlow](http://www.specflow.org). This involves some manual setup work, though: SpecFlow+ Runner outputs an HTML file that is not really suitable for automatic processing. Fortunately the template that produces the HTML file can be changed.

Create a custom report file as described on the [Reports page](http://www.specflow.org/plus/documentation/Reports/) of the SpecFlow+ documentation.

Open your copy of `ReportTemplate.cshtml` and add this helper before the html element:

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

Still in your copy of `ReportTemplate.cshtml`, add this fragment before the closing /body element. For technical reasons, the xml fragment on this page starts with a line beginning with `//`. You should not include that line in the xml file.

    // copy this html fragment:
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

Congratulations! You have now modified the default SpecFlow+ Runner report template so that it includes additional information that will tell Pickles the results of the scenarios.

## Take Care When Using Scenario Outlines

You need to take special care when writing Scenario Outlines in order for Pickles to be able to match the results of the individual examples to the rows in the Examples table. There must be no repeated values in the first column of the examples table. Consider using a `description` column that gives a brief description of the purpose of the example.

This will work:

    Examples:
      | description | value 1 | value 2 | result |
      | addition    | 60      | 20      | 80     |
      | subtraction | 60      | -20     | 40     |

This will not work:

    Examples:
      | value 1 | value 2 | result |
      | 60      | 20      | 80     |
      | 60      | -20     | 40     |
