# eslint-config-vitest Flat Config Bug

This repo demonstrates the lack of support for Eslint's new [Flat Config](https://eslint.org/docs/latest/use/configure/configuration-files-new). https://github.com/veritem/eslint-plugin-vitest/issues/215

The repo is based on `eslint-config-vitest`'s own [fixtures project](https://github.com/veritem/eslint-plugin-vitest/tree/main/fixtures), and just updates the config to use Flat Config.  I also changed it to be an esm module, just because I prefer the authoring experience.

Running `yarn lint` produces the following error:

```bash
TypeError: Key "plugins": Key "0": Expected an object.
    at Object.validate (D:\src\ux\.yarn\cache\eslint-npm-8.45.0-bb6c5f1226-3e6dcce5cc.zip\node_modules\eslint\lib\config\flat-config-schema.js:315:23)
    at ObjectSchema.validate (D:\src\ux\.yarn\cache\@humanwhocodes-object-schema-npm-1.2.1-43b3ca2646-a824a1ec31.zip\node_modules\@humanwhocodes\object-schema\src\object-schema.js:218:35)
    at D:\src\ux\.yarn\cache\@humanwhocodes-object-schema-npm-1.2.1-43b3ca2646-a824a1ec31.zip\node_modules\@humanwhocodes\object-schema\src\object-schema.js:171:18
    at Array.reduce (<anonymous>)
    at ObjectSchema.merge (D:\src\ux\.yarn\cache\@humanwhocodes-object-schema-npm-1.2.1-43b3ca2646-a824a1ec31.zip\node_modules\@humanwhocodes\object-schema\src\object-schema.js:169:24)
    at D:\src\ux\.yarn\cache\@humanwhocodes-config-array-npm-0.11.10-33012f902e-1b1302e240.zip\node_modules\@humanwhocodes\config-array\api.js:916:42
    at Array.reduce (<anonymous>)
    at FlatConfigArray.getConfig (D:\src\ux\.yarn\cache\@humanwhocodes-config-array-npm-0.11.10-33012f902e-1b1302e240.zip\node_modules\@humanwhocodes\config-array\api.js:915:39)
    at FlatConfigArray.isFileIgnored (D:\src\ux\.yarn\cache\@humanwhocodes-config-array-npm-0.11.10-33012f902e-1b1302e240.zip\node_modules\@humanwhocodes\config-array\api.js:943:15)
    at D:\src\ux\.yarn\cache\eslint-npm-8.45.0-bb6c5f1226-3e6dcce5cc.zip\node_modules\eslint\lib\eslint\eslint-helpers.js:312:49
```

## Repro steps
1. Run `yarn`
1. Run `yarn lint`
