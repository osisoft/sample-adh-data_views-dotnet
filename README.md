# Using OCS Data Views in .NET

**Version:** 1.0.0

[![Build Status](https://dev.azure.com/osieng/engineering/_apis/build/status/product-readiness/osisoft.sample-ocs-data_views-dotnet?branchName=main)](https://dev.azure.com/osieng/engineering/_build/latest?definitionId=3349&branchName=main)

The sample code in this topic demonstrates how to invoke the OCS client library. The sample demonstrates how to establish a connection to SDS, obtain an authorization token, create an SdsType and SdsStream with data (if needed), create a Data View, update it, retrieve it, and retrieve data from it in different ways. At the end of the sample, everything that was created is deleted.

When working in .NET, it is recommended that you use the OCS Client Libraries metapackage, OSIsoft.OCSClients. The metapackage is a NuGet package available from [https://api.nuget.org/v3/index.json](https://api.nuget.org/v3/index.json). The libraries offer a framework of classes that make client development easier.

[SDS documentation](https://ocs-docs.osisoft.com/Content_Portal/Documentation/SequentialDataStore/Data_Store_and_SDS.html)

Developed against DotNet 5.0.

## Running the Sample

## Getting Started

In this example we assume that you have the dotnet core CLI.

To run this example from the commandline run

```shell
cd DataViews
dotnet restore
dotnet run
```

to test this program change directories to the test and run

```shell
cd DataViewsTests
dotnet restore
dotnet test
```

## Configure constants for connecting and authentication

The sample is configured using the file [appsettings.placeholder.json](DataViews/appsettings.placeholder.json). Before editing, rename this file to `appsettings.json`. This repository's `.gitignore` rules should prevent the file from ever being checked in to any fork or branch, to ensure credentials are not compromised.

The SDS Service is secured by obtaining tokens from Azure Active Directory. Such clients provide a client application identifier and an associated secret (or key) that are authenticated against the directory. You must replace the placeholders in the `appsettings.json` file with the authentication-related values you received from OSIsoft.

```json
{
  "NamespaceId": "REPLACE_WITH_NAMESPACE_ID",
  "TenantId": "REPLACE_WITH_TENANT_ID",
  "Resource": "https://dat-b.osisoft.com",
  "ClientId": "REPLACE_WITH_APPLICATION_IDENTIFIER",
  "ClientKey": "REPLACE_WITH_APPLICATION_SECRET",
  "ApiVersion": "v1"
}
```

---

Tested against DotNet 5.0.

For the main OCS data views samples page [ReadMe](https://github.com/osisoft/OSI-Samples-OCS/blob/main/docs/DATA_VIEWS_README.md)  
For the main OCS samples page [ReadMe](https://github.com/osisoft/OSI-Samples-OCS)  
For the main OSIsoft samples page [ReadMe](https://github.com/osisoft/OSI-Samples)