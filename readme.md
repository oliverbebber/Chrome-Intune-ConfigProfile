# Google Chrome Intune Configuration Profile

When uploading the Chrome Policy templates and Update management templates to Microsoft Intune from https://chromeenterprise.google/browser/download/#manage-policies-tab, the following error occurred: 

```ADMX file referenced not found NamespaceMissing:Microsoft.Policies.Windows. Please upload it first.```

Removing the following from `GoogleUpdate.admx` resolved the error:

```xml
<using prefix="windows" namespace="Microsoft.Policies.Windows" /> 
```

Removing the following from `Chrome.admx` resolved the error:

```xml
<using namespace="Microsoft.Policies.Windows" prefix="windows"/>
```