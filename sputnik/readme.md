# AutoRest Sputnik Generator 

The AutoRest Sputnik generator is intended to be use from AutoRest. 

> see https://aka.ms/autorest

# Notes

Install:
- nodeJS (min 10.x better: 12.x best: 13.x latest ) -- node 13 has a lot of good perf improvements
- autorest `npm install -g autorest`
- rushjs `npm install -g @microsoft/rush'

```bash
git clone https://github.com/fearthecowboy/autorest.sputnik -b simple
rush update
rush rebuild
autorest https://github.com/Azure/azure-rest-api-specs/tree/master/specification/redis/resource-manager/readme.md --use:.
autorest https://github.com/Azure/azure-rest-api-specs/tree/master/specification/redis/resource-manager/readme.md --use:. --sputnik.debugger
```

or for a single swagger file:
```bash
autorest --input-file:foo.json --use:<path-to-the-dev-folder>  
autorest --input-file:foo.json --use:c:/work/myExtension
autorest --input-file:..  --use:@autorest/azure-functions-python 
```


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


### Autorest plugin configuration
- Please don't edit this section unless you're re-configuring how the sputnik extension plugs in to AutoRest
AutoRest needs the below config to pick this up as a plug-in - see https://github.com/Azure/autorest/blob/master/docs/developer/architecture/AutoRest-extension.md

> AutoRest configuration is stored in the 'autorest-configuation.md' file.

``` yaml 
pipeline-model: v3
require: $(this-folder)/autorest-configuration.md
```

