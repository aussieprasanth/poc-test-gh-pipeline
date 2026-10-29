# Build

Use JDK 11 and Maven to build and test the application:

```shell
mvn -B clean test package
```

The build produces `target/helloworld.war`, test results in
`target/surefire-reports/`, and coverage reports in `target/site/jacoco/`.
JUnit 4.13.2 is required for compatibility with current Maven Surefire versions.
Azure Pipelines uses the POM's JaCoCo configuration and publishes its XML report
with `PublishCodeCoverageResults@2`. Keep automatic coverage instrumentation in
`Maven@4` disabled (`codeCoverageToolOption: None`) to avoid duplicate JaCoCo
plugin declarations.
The GitHub Actions build uses Ubuntu 24.04 and Node.js 24-based actions.

# Azure DevOps migration agent

The shared [ADO to GitHub Actions agent](.github/agents/ado-to-github.agent.md)
converts Azure DevOps pipelines to GitHub Actions across languages and platforms.
In VS Code Copilot Chat, select **ADO to GitHub Actions** from the agent picker,
then provide the source pipeline path or classic pipeline export, any referenced
templates, and destination requirements. For example:

> Convert azure-pipelines.yml and its templates to GitHub Actions. Preserve
> triggers, tests, artifacts, and deployment approvals. Identify required secrets
> and manual setup, and validate the build without deploying or pushing.

The agent flags unsupported features and missing configuration rather than
promising automatic conversion of every ADO feature. Commit the agent file to
share it with the team; copy it into another repository's `.github/agents/`
directory to reuse it there.

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

# Legal Notices

Microsoft and any contributors grant you a license to the Microsoft documentation and other content
in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
see the [LICENSE](LICENSE) file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the
[LICENSE-CODE](LICENSE-CODE) file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all others rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.
