# Issue 398

When running with Apex build 0.8.0, this project fails due to a relative symlink not being followable for an ```Open``` command.

```bash
ThinMint:apex tobyjoe$ apex deploy issue-398 --profile ixni -l debug
   • loading functions in functions
   • loading function in functions/issue-398
   • inferring runtime         function=issue-398
   • inferred runtime          function=issue-398 runtime=nodejs4.3
   • deploying 1 functions
   • deploying                 function=issue-398
   • creating build            function=issue-398
   • injecting prelude         function=issue-398
   • hook                      command=npm install function=issue-398 hook=build
   • adding env                env=map[APEX_FUNCTION_NAME:issue-398 LAMBDA_FUNCTION_NAME:Examples_issue-398] function=issue-398
   • add file to zip           file=index.js function=issue-398
   • add file to zip           file=node_modules/.bin/har-validator function=issue-398
   ⨯ Error: function issue-398: open functions/har-validator/lib/bin.js: no such file or directory

```

After upgrading to the build with the ```tobyjoe:fixes-398-symlinks-on-deploy``` branch, we get the following (ignore the error at the end):

```bash
ThinMint:apex tobyjoe$ apex deploy issue-398 --profile ixni -l debug
   • loading functions in functions
   • loading function in functions/issue-398
   • inferring runtime         function=issue-398
   • inferred runtime          function=issue-398 runtime=nodejs4.3
   • deploying 1 functions
   • deploying                 function=issue-398
   • creating build            function=issue-398
   • injecting prelude         function=issue-398
   • hook                      command=npm install function=issue-398 hook=build
   • adding env                env=map[LAMBDA_FUNCTION_NAME:Examples_issue-398 APEX_FUNCTION_NAME:issue-398] function=issue-398
   • add file to zip           file=README.md function=issue-398
   • add file to zip           file=index.js function=issue-398
   • add file to zip           file=node_modules/.bin/har-validator function=issue-398
   • add file to zip           file=node_modules/ansi-regex/index.js function=issue-398
   • add file to zip           file=node_modules/ansi-regex/license function=issue-398
   • add file to zip           file=node_modules/ansi-regex/package.json function=issue-398
   • add file to zip           file=node_modules/ansi-regex/readme.md function=issue-398
   • add file to zip           file=node_modules/ansi-styles/index.js function=issue-398
   • add file to zip           file=node_modules/ansi-styles/license function=issue-398
   • add file to zip           file=node_modules/ansi-styles/package.json function=issue-398
   • add file to zip           file=node_modules/ansi-styles/readme.md function=issue-398
   • add file to zip           file=node_modules/chalk/index.js function=issue-398
   • add file to zip           file=node_modules/chalk/license function=issue-398
   • add file to zip           file=node_modules/chalk/package.json function=issue-398
   • add file to zip           file=node_modules/chalk/readme.md function=issue-398
   • add file to zip           file=node_modules/commander/History.md function=issue-398
   • add file to zip           file=node_modules/commander/LICENSE function=issue-398
   • add file to zip           file=node_modules/commander/Readme.md function=issue-398
   • add file to zip           file=node_modules/commander/index.js function=issue-398
   • add file to zip           file=node_modules/commander/package.json function=issue-398
   • add file to zip           file=node_modules/escape-string-regexp/index.js function=issue-398
   • add file to zip           file=node_modules/escape-string-regexp/license function=issue-398
   • add file to zip           file=node_modules/escape-string-regexp/package.json function=issue-398
   • add file to zip           file=node_modules/escape-string-regexp/readme.md function=issue-398
   • add file to zip           file=node_modules/generate-function/.npmignore function=issue-398
   • add file to zip           file=node_modules/generate-function/.travis.yml function=issue-398
   • add file to zip           file=node_modules/generate-function/README.md function=issue-398
   • add file to zip           file=node_modules/generate-function/example.js function=issue-398
   • add file to zip           file=node_modules/generate-function/index.js function=issue-398
   • add file to zip           file=node_modules/generate-function/package.json function=issue-398
   • add file to zip           file=node_modules/generate-function/test.js function=issue-398
   • add file to zip           file=node_modules/generate-object-property/.npmignore function=issue-398
   • add file to zip           file=node_modules/generate-object-property/.travis.yml function=issue-398
   • add file to zip           file=node_modules/generate-object-property/LICENSE function=issue-398
   • add file to zip           file=node_modules/generate-object-property/README.md function=issue-398
   • add file to zip           file=node_modules/generate-object-property/index.js function=issue-398
   • add file to zip           file=node_modules/generate-object-property/package.json function=issue-398
   • add file to zip           file=node_modules/generate-object-property/test.js function=issue-398
   • add file to zip           file=node_modules/graceful-readlink/.npmignore function=issue-398
   • add file to zip           file=node_modules/graceful-readlink/.travis.yml function=issue-398
   • add file to zip           file=node_modules/graceful-readlink/LICENSE function=issue-398
   • add file to zip           file=node_modules/graceful-readlink/README.md function=issue-398
   • add file to zip           file=node_modules/graceful-readlink/index.js function=issue-398
   • add file to zip           file=node_modules/graceful-readlink/package.json function=issue-398
   • add file to zip           file=node_modules/har-validator/LICENSE function=issue-398
   • add file to zip           file=node_modules/har-validator/README.md function=issue-398
   • add file to zip           file=node_modules/har-validator/lib/async.js function=issue-398
   • add file to zip           file=node_modules/har-validator/lib/bin.js function=issue-398
   • add file to zip           file=node_modules/har-validator/lib/error.js function=issue-398
   • add file to zip           file=node_modules/har-validator/lib/promise.js function=issue-398
   • add file to zip           file=node_modules/har-validator/lib/schemas.js function=issue-398
   • add file to zip           file=node_modules/har-validator/package.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/cache.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/cacheEntry.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/content.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/cookie.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/creator.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/entry.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/har.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/log.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/page.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/pageTimings.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/postData.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/record.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/request.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/response.json function=issue-398
   • add file to zip           file=node_modules/har-validator/schemas/timings.json function=issue-398
   • add file to zip           file=node_modules/har-validator/src/async.js function=issue-398
   • add file to zip           file=node_modules/har-validator/src/bin.js function=issue-398
   • add file to zip           file=node_modules/har-validator/src/error.js function=issue-398
   • add file to zip           file=node_modules/har-validator/src/promise.js function=issue-398
   • add file to zip           file=node_modules/har-validator/src/schemas.js function=issue-398
   • add file to zip           file=node_modules/has-ansi/index.js function=issue-398
   • add file to zip           file=node_modules/has-ansi/license function=issue-398
   • add file to zip           file=node_modules/has-ansi/package.json function=issue-398
   • add file to zip           file=node_modules/has-ansi/readme.md function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/.npmignore function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/.travis.yml function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/LICENSE function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/README.md function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/example.js function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/formats.js function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/index.js function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/package.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/require.js function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/fixtures/cosmic.js function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/additionalItems.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/additionalProperties.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/allOf.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/anyOf.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/bignum.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/default.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/definitions.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/dependencies.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/enum.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/format.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/items.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/maxItems.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/maxLength.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/maxProperties.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/maximum.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/minItems.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/minLength.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/minProperties.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/minimum.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/multipleOf.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/not.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/nullAndFormat.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/nullAndObject.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/oneOf.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/pattern.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/patternProperties.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/properties.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/ref.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/refRemote.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/required.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/type.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema-draft4/uniqueItems.json function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/json-schema.js function=issue-398
   • add file to zip           file=node_modules/is-my-json-valid/test/misc.js function=issue-398
   • add file to zip           file=node_modules/is-property/.npmignore function=issue-398
   • add file to zip           file=node_modules/is-property/LICENSE function=issue-398
   • add file to zip           file=node_modules/is-property/README.md function=issue-398
   • add file to zip           file=node_modules/is-property/is-property.js function=issue-398
   • add file to zip           file=node_modules/is-property/package.json function=issue-398
   • add file to zip           file=node_modules/jsonpointer/.travis.yml function=issue-398
   • add file to zip           file=node_modules/jsonpointer/README.md function=issue-398
   • add file to zip           file=node_modules/jsonpointer/jsonpointer.js function=issue-398
   • add file to zip           file=node_modules/jsonpointer/package.json function=issue-398
   • add file to zip           file=node_modules/jsonpointer/test.js function=issue-398
   • add file to zip           file=node_modules/strip-ansi/index.js function=issue-398
   • add file to zip           file=node_modules/strip-ansi/license function=issue-398
   • add file to zip           file=node_modules/strip-ansi/package.json function=issue-398
   • add file to zip           file=node_modules/strip-ansi/readme.md function=issue-398
   • add file to zip           file=node_modules/supports-color/index.js function=issue-398
   • add file to zip           file=node_modules/supports-color/license function=issue-398
   • add file to zip           file=node_modules/supports-color/package.json function=issue-398
   • add file to zip           file=node_modules/supports-color/readme.md function=issue-398
   • add file to zip           file=node_modules/xtend/.jshintrc function=issue-398
   • add file to zip           file=node_modules/xtend/.npmignore function=issue-398
   • add file to zip           file=node_modules/xtend/LICENCE function=issue-398
   • add file to zip           file=node_modules/xtend/Makefile function=issue-398
   • add file to zip           file=node_modules/xtend/README.md function=issue-398
   • add file to zip           file=node_modules/xtend/immutable.js function=issue-398
   • add file to zip           file=node_modules/xtend/mutable.js function=issue-398
   • add file to zip           file=node_modules/xtend/package.json function=issue-398
   • add file to zip           file=node_modules/xtend/test.js function=issue-398
   • add file to zip           file=package.json function=issue-398
   • created build (114 kB)    function=issue-398
   • fetching config           function=issue-398
   • creating function         function=issue-398
   ⨯ Error: function issue-398: ValidationException: 1 validation error detected: Value 'YO_ROLE_GOES_HERRRR' at 'role' failed to satisfy constraint: Member must satisfy regular expression pattern: arn:aws:iam::\d{12}:role/?[a-zA-Z_0-9+=,.@\-_/]+
	status code: 400, request id: 4c97db71-13a9-11e6-941a-877e0c216591

```