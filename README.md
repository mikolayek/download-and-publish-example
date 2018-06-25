# Hybris Version Download and Publish

This example shows how to use the commerce gradle plugin to download a new version
from the SAP Support portal and then publish it to an internal maven respository
using the [maven-publish][publish] plugin that's part of gradle.

A sample command line call looks like this:

```bash
gradle downloadCommerce publishMavenPublicationToMavenRepository \
    -PhybrisVersion="6.7.0.2" \
    -PdownloadUrl="https://launchpad.support.sap.com/#/softwarecenter/template/products/_APP=00200682500000001943..." \
    -PexpectedHash="bb457a376bf8c456064a237ef3d61432"
```

One could leverage [parameterized Jenkins builds][jenkinsfile-param] to build a semi-automatic tool-chain
to publish new releases.

[publish]: https://docs.gradle.org/current/userguide/publishing_maven.html
[jenkinsfile-param]: https://jenkins.io/doc/book/pipeline/jenkinsfile/#handling-parameters