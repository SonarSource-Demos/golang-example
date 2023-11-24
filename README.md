# Go Sonar scanning example project

Credits to the Go Example project <https://go.googlesource.com/example> for the example code to analyze
Please refer to the [golangci-lint documentation for](https://golangci-lint.run) for its installation

## Clone the project

``` bash
$ git clone https://github.com/sylvain-combe-sonarsource/import-golintci-lint
$ cd import-golintci-lint
```

## Run the golangci-lint too

``` bash
$ golangci-lint run
```

The provided (./.golangci.yaml) configuration file is only provided as an **example**. The file does not represent a list of linters that Sonar would recommend to use.

## Run the Sonar scanner and import the external issues

Position the SonarQube(or SonarCloud) Server URL, analysis token, and SonarCloud organization before you run the scanner command.
As described with [External analyzer reports | SonarQube Docs](https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/importing-external-issues/external-analyzer-reports/), golangci-lint is [configured](./.golangci.yaml) to output its report in CheckStyle format, and Sonar analysis is [configured](./sonar-project.properties) to pickup this output from the reports folder.

``` bash
$ export SONAR_TOKEN="YOUR-SONARQUBE-OR-SONARCLOUD-ANALYSIS-TOKEN"
$ export SONAR_URL="https://sonarqube.mycompany.com/"
$ sonar-scanner
```