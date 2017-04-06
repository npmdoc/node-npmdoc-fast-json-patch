# api documentation for  [fast-json-patch (v1.1.8)](https://github.com/Starcounter-Jack/JSON-Patch)  [![npm package](https://img.shields.io/npm/v/npmdoc-fast-json-patch.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-fast-json-patch) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-fast-json-patch.svg)](https://travis-ci.org/npmdoc/node-npmdoc-fast-json-patch)
#### Fast implementation of JSON-Patch (RFC-6902) with duplex (observe changes) capabilities

[![NPM](https://nodei.co/npm/fast-json-patch.png?downloads=true)](https://www.npmjs.com/package/fast-json-patch)

[![apidoc](https://npmdoc.github.io/node-npmdoc-fast-json-patch/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-fast-json-patch_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-fast-json-patch/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-fast-json-patch/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-fast-json-patch/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Joachim Wester",
        "email": "joachimwester@me.com",
        "url": "http://www.starcounter.com/"
    },
    "bugs": {
        "url": "https://github.com/Starcounter-Jack/JSON-Patch/issues"
    },
    "dependencies": {},
    "description": "Fast implementation of JSON-Patch (RFC-6902) with duplex (observe changes) capabilities",
    "devDependencies": {
        "benchmark": "^2.1.2",
        "chalk": "^1.1.3",
        "grunt": "^0.4.5",
        "grunt-bump": "^0.3.0",
        "grunt-contrib-uglify": "~0.5.0",
        "jasmine": "^2.5.1",
        "jsdom": "^9.5.0",
        "jsonfile": "^2.3.1",
        "typescript": "~2.0.0",
        "underscore": "^1.8.3"
    },
    "directories": {},
    "dist": {
        "shasum": "8db58c9d12c3ff9c23456ee812cc29fac722b772",
        "tarball": "https://registry.npmjs.org/fast-json-patch/-/fast-json-patch-1.1.8.tgz"
    },
    "engines": {
        "node": ">= 0.4.0"
    },
    "gitHead": "4a788782e209723ff8d1b31f978eb824eb9ecf57",
    "homepage": "https://github.com/Starcounter-Jack/JSON-Patch",
    "keywords": [
        "json",
        "patch",
        "http",
        "rest"
    ],
    "license": "MIT",
    "main": "src/json-patch-duplex.js",
    "maintainers": [
        {
            "name": "warpech",
            "email": "warpech@gmail.com"
        },
        {
            "name": "tomalec",
            "email": "tomalecwp@gmail.com"
        }
    ],
    "name": "fast-json-patch",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/Starcounter-Jack/JSON-Patch.git"
    },
    "scripts": {
        "bench": "npm run bench-core && npm run bench-duplex",
        "bench-core": "node test/spec/coreBenchmark.js",
        "bench-duplex": "node test/spec/coreBenchmark.js DUPLEX=yes && node test/spec/duplexBenchmark.js",
        "bench-duplex-only": "node test/spec/duplexBenchmark.js",
        "test": "npm run test-core && npm run test-duplex",
        "test-core": "jasmine  DUPLEX=no JASMINE_CONFIG_PATH=test/jasmine.json test/spec/jsonPatchTestsSpec.js test/spec/coreSpec.js test/spec/validateSpec.js",
        "test-duplex": "jasmine DUPLEX=yes JASMINE_CONFIG_PATH=test/jasmine.json",
        "tsc": "tsc",
        "tsc-watch": "tsc -w",
        "uglify": "grunt uglify"
    },
    "typings": "src/json-patch-duplex.d.ts",
    "version": "1.1.8"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module fast-json-patch](#apidoc.module.fast-json-patch)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.</span>JsonPatchError (message, name, index, operation, tree)](#apidoc.element.fast-json-patch.JsonPatchError)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.</span>apply (tree, patches, validate)](#apidoc.element.fast-json-patch.apply)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.</span>compare (tree1, tree2)](#apidoc.element.fast-json-patch.compare)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.</span>generate (observer)](#apidoc.element.fast-json-patch.generate)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.</span>observe (obj, callback)](#apidoc.element.fast-json-patch.observe)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.</span>unobserve (root, observer)](#apidoc.element.fast-json-patch.unobserve)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.</span>validate (sequence, tree)](#apidoc.element.fast-json-patch.validate)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.</span>validator (operation, index, tree, existingPathFragment)](#apidoc.element.fast-json-patch.validator)
1.  object <span class="apidocSignatureSpan">fast-json-patch.</span>JsonPatchError.prototype
1.  object <span class="apidocSignatureSpan">fast-json-patch.</span>default
1.  object <span class="apidocSignatureSpan">fast-json-patch.</span>json_patch

#### [module fast-json-patch.JsonPatchError](#apidoc.module.fast-json-patch.JsonPatchError)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.</span>JsonPatchError (message, name, index, operation, tree)](#apidoc.element.fast-json-patch.JsonPatchError.JsonPatchError)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.JsonPatchError.</span>captureStackTrace ()](#apidoc.element.fast-json-patch.JsonPatchError.captureStackTrace)
1.  number <span class="apidocSignatureSpan">fast-json-patch.JsonPatchError.</span>stackTraceLimit

#### [module fast-json-patch.JsonPatchError.prototype](#apidoc.module.fast-json-patch.JsonPatchError.prototype)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.JsonPatchError.prototype.</span>constructor (message, name, index, operation, tree)](#apidoc.element.fast-json-patch.JsonPatchError.prototype.constructor)

#### [module fast-json-patch.default](#apidoc.module.fast-json-patch.default)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.default.</span>JsonPatchError (message, name, index, operation, tree)](#apidoc.element.fast-json-patch.default.JsonPatchError)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.default.</span>apply (tree, patches, validate)](#apidoc.element.fast-json-patch.default.apply)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.default.</span>compare (tree1, tree2)](#apidoc.element.fast-json-patch.default.compare)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.default.</span>generate (observer)](#apidoc.element.fast-json-patch.default.generate)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.default.</span>observe (obj, callback)](#apidoc.element.fast-json-patch.default.observe)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.default.</span>unobserve (root, observer)](#apidoc.element.fast-json-patch.default.unobserve)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.default.</span>validate (sequence, tree)](#apidoc.element.fast-json-patch.default.validate)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.default.</span>validator (operation, index, tree, existingPathFragment)](#apidoc.element.fast-json-patch.default.validator)

#### [module fast-json-patch.json_patch](#apidoc.module.fast-json-patch.json_patch)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.json_patch.</span>JsonPatchError (message, name, index, operation, tree)](#apidoc.element.fast-json-patch.json_patch.JsonPatchError)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.json_patch.</span>apply (tree, patches, validate)](#apidoc.element.fast-json-patch.json_patch.apply)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.json_patch.</span>validate (sequence, tree)](#apidoc.element.fast-json-patch.json_patch.validate)
1.  [function <span class="apidocSignatureSpan">fast-json-patch.json_patch.</span>validator (operation, index, tree, existingPathFragment)](#apidoc.element.fast-json-patch.json_patch.validator)
1.  object <span class="apidocSignatureSpan">fast-json-patch.json_patch.</span>default



# <a name="apidoc.module.fast-json-patch"></a>[module fast-json-patch](#apidoc.module.fast-json-patch)

#### <a name="apidoc.element.fast-json-patch.JsonPatchError"></a>[function <span class="apidocSignatureSpan">fast-json-patch.</span>JsonPatchError (message, name, index, operation, tree)](#apidoc.element.fast-json-patch.JsonPatchError)
- description and source-code
```javascript
function JsonPatchError(message, name, index, operation, tree) {
    _super.call(this, message);
    this.message = message;
    this.name = name;
    this.index = index;
    this.operation = operation;
    this.tree = tree;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.fast-json-patch.apply"></a>[function <span class="apidocSignatureSpan">fast-json-patch.</span>apply (tree, patches, validate)](#apidoc.element.fast-json-patch.apply)
- description and source-code
```javascript
function apply(tree, patches, validate) {
    var results = [], p = 0, plen = patches.length, patch, key;
    while (p < plen) {
        patch = patches[p];
        p++;
        // Find the object
        var path = patch.path || "";
        var keys = path.split('/');
        var obj = tree;
        var t = 1; //skip empty element - http://jsperf.com/to-shift-or-not-to-shift
        var len = keys.length;
        var existingPathFragment = undefined;
        while (true) {
            key = keys[t];
            if (validate) {
                if (existingPathFragment === undefined) {
                    if (obj[key] === undefined) {
                        existingPathFragment = keys.slice(0, t).join('/');
                    }
                    else if (t == len - 1) {
                        existingPathFragment = patch.path;
                    }
                    if (existingPathFragment !== undefined) {
                        this.validator(patch, p - 1, tree, existingPathFragment);
                    }
                }
            }
            t++;
            if (key === undefined) {
                if (t >= len) {
                    results.push(rootOps[patch.op].call(patch, obj, key, tree)); // Apply patch
                    break;
                }
            }
            if (_isArray(obj)) {
                if (key === '-') {
                    key = obj.length;
                }
                else {
                    if (validate && !isInteger(key)) {
                        throw new JsonPatchError("Expected an unsigned base-10 integer value, making the new referenced value the
 array element with the zero-based index", "OPERATION_PATH_ILLEGAL_ARRAY_INDEX", p - 1, patch.path, patch);
                    }
                    key = parseInt(key, 10);
                }
                if (t >= len) {
                    if (validate && patch.op === "add" && key > obj.length) {
                        throw new JsonPatchError("The specified index MUST NOT be greater than the number of elements in the array
", "OPERATION_VALUE_OUT_OF_BOUNDS", p - 1, patch.path, patch);
                    }
                    results.push(arrOps[patch.op].call(patch, obj, key, tree)); // Apply patch
                    break;
                }
            }
            else {
                if (key && key.indexOf('~') != -1)
                    key = key.replace(/~1/g, '/').replace(/~0/g, '~'); // escape chars
                if (t >= len) {
                    results.push(objOps[patch.op].call(patch, obj, key, tree)); // Apply patch
                    break;
                }
            }
            obj = obj[key];
        }
    }
    return results;
}
```
- example usage
```shell
...
'''js
var myobj = { firstName:"Albert", contactDetails: { phoneNumbers: [ ] } };
var patches = [
   {op:"replace", path:"/firstName", value:"Joachim" },
   {op:"add", path:"/lastName", value:"Wester" },
   {op:"add", path:"/contactDetails/phoneNumbers/0", value:{ number:"555-123" }  }
   ];
jsonpatch.apply( myobj, patches );
// myobj == { firstName:"Joachim", lastName:"Wester", contactDetails:{ phoneNumbers[ {number:"555-123"} ] } };
'''
Generating patches:

'''js
var myobj = { firstName:"Joachim", lastName:"Wester", contactDetails: { phoneNumbers: [ { number:"555-123" }] } };
observer = jsonpatch.observe( myobj );
...
```

#### <a name="apidoc.element.fast-json-patch.compare"></a>[function <span class="apidocSignatureSpan">fast-json-patch.</span>compare (tree1, tree2)](#apidoc.element.fast-json-patch.compare)
- description and source-code
```javascript
function compare(tree1, tree2) {
    var patches = [];
    _generate(tree1, tree2, patches, '');
    return patches;
}
```
- example usage
```shell
...
//   { op:"add", path="/contactDetails/phoneNumbers/1", value:{number:"456"}}];
'''
Comparing two object trees:

'''js
var objA = {user: {firstName: "Albert", lastName: "Einstein"}};
var objB = {user: {firstName: "Albert", lastName: "Collins"}};
var diff = jsonpatch.compare(objA, objB));
//diff == [{op: "replace", path: "/user/lastName", value: "Collins"}]
'''

Validating a sequence of patches:

'''js
var obj = {user: {firstName: "Albert"}};
...
```

#### <a name="apidoc.element.fast-json-patch.generate"></a>[function <span class="apidocSignatureSpan">fast-json-patch.</span>generate (observer)](#apidoc.element.fast-json-patch.generate)
- description and source-code
```javascript
function generate(observer) {
    var mirror;
    for (var i = 0, ilen = beforeDict.length; i < ilen; i++) {
        if (beforeDict[i].obj === observer.object) {
            mirror = beforeDict[i];
            break;
        }
    }
    _generate(mirror.value, observer.object, observer.patches, "");
    if (observer.patches.length) {
        apply(mirror.value, observer.patches);
    }
    var temp = observer.patches;
    if (temp.length > 0) {
        observer.patches = [];
        if (observer.callback) {
            observer.callback(temp);
        }
    }
    return temp;
}
```
- example usage
```shell
...

'''js
var myobj = { firstName:"Joachim", lastName:"Wester", contactDetails: { phoneNumbers: [ { number:"555-123" }] } };
observer = jsonpatch.observe( myobj );
myobj.firstName = "Albert";
myobj.contactDetails.phoneNumbers[0].number = "123";
myobj.contactDetails.phoneNumbers.push({number:"456"});
var patches = jsonpatch.generate(observer);
// patches  == [
//   { op:"replace", path="/firstName", value:"Albert"},
//   { op:"replace", path="/contactDetails/phoneNumbers/0/number", value:"123"},
//   { op:"add", path="/contactDetails/phoneNumbers/1", value:{number:"456"}}];
'''
Comparing two object trees:
...
```

#### <a name="apidoc.element.fast-json-patch.observe"></a>[function <span class="apidocSignatureSpan">fast-json-patch.</span>observe (obj, callback)](#apidoc.element.fast-json-patch.observe)
- description and source-code
```javascript
function observe(obj, callback) {
    var patches = [];
    var root = obj;
    var observer;
    var mirror = getMirror(obj);
    if (!mirror) {
        mirror = new Mirror(obj);
        beforeDict.push(mirror);
    }
    else {
        observer = getObserverFromMirror(mirror, callback);
    }
    if (observer) {
        return observer;
    }
    observer = {};
    mirror.value = deepClone(obj);
    if (callback) {
        observer.callback = callback;
        observer.next = null;
        var dirtyCheck = function () {
            generate(observer);
        };
        var fastCheck = function () {
            clearTimeout(observer.next);
            observer.next = setTimeout(dirtyCheck);
        };
        if (typeof window !== 'undefined') {
            if (window.addEventListener) {
                window.addEventListener('mouseup', fastCheck);
                window.addEventListener('keyup', fastCheck);
                window.addEventListener('mousedown', fastCheck);
                window.addEventListener('keydown', fastCheck);
                window.addEventListener('change', fastCheck);
            }
            else {
                document.documentElement.attachEvent('onmouseup', fastCheck);
                document.documentElement.attachEvent('onkeyup', fastCheck);
                document.documentElement.attachEvent('onmousedown', fastCheck);
                document.documentElement.attachEvent('onkeydown', fastCheck);
                document.documentElement.attachEvent('onchange', fastCheck);
            }
        }
    }
    observer.patches = patches;
    observer.object = obj;
    observer.unobserve = function () {
        generate(observer);
        clearTimeout(observer.next);
        removeObserverFromMirror(mirror, observer);
        if (typeof window !== 'undefined') {
            if (window.removeEventListener) {
                window.removeEventListener('mouseup', fastCheck);
                window.removeEventListener('keyup', fastCheck);
                window.removeEventListener('mousedown', fastCheck);
                window.removeEventListener('keydown', fastCheck);
            }
            else {
                document.documentElement.detachEvent('onmouseup', fastCheck);
                document.documentElement.detachEvent('onkeyup', fastCheck);
                document.documentElement.detachEvent('onmousedown', fastCheck);
                document.documentElement.detachEvent('onkeydown', fastCheck);
            }
        }
    };
    mirror.observers.push(new ObserverInfo(callback, observer));
    return observer;
}
```
- example usage
```shell
...
jsonpatch.apply( myobj, patches );
// myobj == { firstName:"Joachim", lastName:"Wester", contactDetails:{ phoneNumbers[ {number:"555-123"} ] } };
'''
Generating patches:

'''js
var myobj = { firstName:"Joachim", lastName:"Wester", contactDetails: { phoneNumbers: [ { number:"555-123" }] } };
observer = jsonpatch.observe( myobj );
myobj.firstName = "Albert";
myobj.contactDetails.phoneNumbers[0].number = "123";
myobj.contactDetails.phoneNumbers.push({number:"456"});
var patches = jsonpatch.generate(observer);
// patches  == [
//   { op:"replace", path="/firstName", value:"Albert"},
//   { op:"replace", path="/contactDetails/phoneNumbers/0/number", value:"123"},
...
```

#### <a name="apidoc.element.fast-json-patch.unobserve"></a>[function <span class="apidocSignatureSpan">fast-json-patch.</span>unobserve (root, observer)](#apidoc.element.fast-json-patch.unobserve)
- description and source-code
```javascript
function unobserve(root, observer) {
    observer.unobserve();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.fast-json-patch.validate"></a>[function <span class="apidocSignatureSpan">fast-json-patch.</span>validate (sequence, tree)](#apidoc.element.fast-json-patch.validate)
- description and source-code
```javascript
function validate(sequence, tree) {
    try {
        if (!_isArray(sequence)) {
            throw new JsonPatchError('Patch sequence must be an array', 'SEQUENCE_NOT_AN_ARRAY');
        }
        if (tree) {
            tree = JSON.parse(JSON.stringify(tree)); //clone tree so that we can safely try applying operations
            apply.call(this, tree, sequence, true);
        }
        else {
            for (var i = 0; i < sequence.length; i++) {
                this.validator(sequence[i], i);
            }
        }
    }
    catch (e) {
        if (e instanceof JsonPatchError) {
            return e;
        }
        else {
            throw e;
        }
    }
}
```
- example usage
```shell
...
'''

Validating a sequence of patches:

'''js
var obj = {user: {firstName: "Albert"}};
var patches = [{op: "replace", path: "/user/firstName", value: "Albert"}, {op: "replace", path: "/user/lastName", value: "Einstein
"}];
var errors = jsonpatch.validate(patches, obj);
if (errors.length == 0) {
 //there are no errors!
}
else {
for (var i=0; i < errors.length; i++) {
  if (!errors[i]) {
    console.log("Valid patch at index", i, patches[i]);
...
```

#### <a name="apidoc.element.fast-json-patch.validator"></a>[function <span class="apidocSignatureSpan">fast-json-patch.</span>validator (operation, index, tree, existingPathFragment)](#apidoc.element.fast-json-patch.validator)
- description and source-code
```javascript
function validator(operation, index, tree, existingPathFragment) {
    if (typeof operation !== 'object' || operation === null || _isArray(operation)) {
        throw new JsonPatchError('Operation is not an object', 'OPERATION_NOT_AN_OBJECT', index, operation, tree);
    }
    else if (!objOps[operation.op]) {
        throw new JsonPatchError('Operation 'op' property is not one of operations defined in RFC-6902', 'OPERATION_OP_INVALID',
index, operation, tree);
    }
    else if (typeof operation.path !== 'string') {
        throw new JsonPatchError('Operation 'path' property is not a string', 'OPERATION_PATH_INVALID', index, operation, tree);
    }
    else if (operation.path.indexOf('/') !== 0 && operation.path.length > 0) {
        // paths that aren't emptystring should start with "/"
        throw new JsonPatchError('Operation 'path' property must start with "/"', 'OPERATION_PATH_INVALID', index, operation, tree
);
    }
    else if ((operation.op === 'move' || operation.op === 'copy') && typeof operation.from !== 'string') {
        throw new JsonPatchError('Operation 'from' property is not present (applicable in 'move' and 'copy' operations)', 'OPERATION_FROM_REQUIRED
', index, operation, tree);
    }
    else if ((operation.op === 'add' || operation.op === 'replace' || operation.op === 'test') && operation.value === undefined) {
        throw new JsonPatchError('Operation 'value' property is not present (applicable in 'add', 'replace' and 'test' operations
)', 'OPERATION_VALUE_REQUIRED', index, operation, tree);
    }
    else if ((operation.op === 'add' || operation.op === 'replace' || operation.op === 'test') && hasUndefined(operation.value)) {
        throw new JsonPatchError('Operation 'value' property is not present (applicable in 'add', 'replace' and 'test' operations
)', 'OPERATION_VALUE_CANNOT_CONTAIN_UNDEFINED', index, operation, tree);
    }
    else if (tree) {
        if (operation.op == "add") {
            var pathLen = operation.path.split("/").length;
            var existingPathLen = existingPathFragment.split("/").length;
            if (pathLen !== existingPathLen + 1 && pathLen !== existingPathLen) {
                throw new JsonPatchError('Cannot perform an 'add' operation at the desired path', 'OPERATION_PATH_CANNOT_ADD', index
, operation, tree);
            }
        }
        else if (operation.op === 'replace' || operation.op === 'remove' || operation.op === '_get') {
            if (operation.path !== existingPathFragment) {
                throw new JsonPatchError('Cannot perform the operation at a path that does not exist', 'OPERATION_PATH_UNRESOLVABLE
', index, operation, tree);
            }
        }
        else if (operation.op === 'move' || operation.op === 'copy') {
            var existingValue = { op: "_get", path: operation.from, value: undefined };
            var error = jsonpatch.validate([existingValue], tree);
            if (error && error.name === 'OPERATION_PATH_UNRESOLVABLE') {
                throw new JsonPatchError('Cannot perform the operation from a path that does not exist', 'OPERATION_FROM_UNRESOLVABLE
', index, operation, tree);
            }
        }
    }
}
```
- example usage
```shell
...
        if (obj[key] === undefined) {
            existingPathFragment = keys.slice(0, t).join('/');
        }
        else if (t == len - 1) {
            existingPathFragment = patch.path;
        }
        if (existingPathFragment !== undefined) {
            this.validator(patch, p - 1, tree, existingPathFragment);
        }
    }
}
t++;
if (key === undefined) {
    if (t >= len) {
        results[p - 1] = rootOps[patch.op].call(patch, obj, key, tree); // Apply patch
...
```



# <a name="apidoc.module.fast-json-patch.JsonPatchError"></a>[module fast-json-patch.JsonPatchError](#apidoc.module.fast-json-patch.JsonPatchError)

#### <a name="apidoc.element.fast-json-patch.JsonPatchError.JsonPatchError"></a>[function <span class="apidocSignatureSpan">fast-json-patch.</span>JsonPatchError (message, name, index, operation, tree)](#apidoc.element.fast-json-patch.JsonPatchError.JsonPatchError)
- description and source-code
```javascript
function JsonPatchError(message, name, index, operation, tree) {
    _super.call(this, message);
    this.message = message;
    this.name = name;
    this.index = index;
    this.operation = operation;
    this.tree = tree;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.fast-json-patch.JsonPatchError.captureStackTrace"></a>[function <span class="apidocSignatureSpan">fast-json-patch.JsonPatchError.</span>captureStackTrace ()](#apidoc.element.fast-json-patch.JsonPatchError.captureStackTrace)
- description and source-code
```javascript
function captureStackTrace() { [native code] }
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.fast-json-patch.JsonPatchError.prototype"></a>[module fast-json-patch.JsonPatchError.prototype](#apidoc.module.fast-json-patch.JsonPatchError.prototype)

#### <a name="apidoc.element.fast-json-patch.JsonPatchError.prototype.constructor"></a>[function <span class="apidocSignatureSpan">fast-json-patch.JsonPatchError.prototype.</span>constructor (message, name, index, operation, tree)](#apidoc.element.fast-json-patch.JsonPatchError.prototype.constructor)
- description and source-code
```javascript
function JsonPatchError(message, name, index, operation, tree) {
    _super.call(this, message);
    this.message = message;
    this.name = name;
    this.index = index;
    this.operation = operation;
    this.tree = tree;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.fast-json-patch.default"></a>[module fast-json-patch.default](#apidoc.module.fast-json-patch.default)

#### <a name="apidoc.element.fast-json-patch.default.JsonPatchError"></a>[function <span class="apidocSignatureSpan">fast-json-patch.default.</span>JsonPatchError (message, name, index, operation, tree)](#apidoc.element.fast-json-patch.default.JsonPatchError)
- description and source-code
```javascript
function JsonPatchError(message, name, index, operation, tree) {
    _super.call(this, message);
    this.message = message;
    this.name = name;
    this.index = index;
    this.operation = operation;
    this.tree = tree;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.fast-json-patch.default.apply"></a>[function <span class="apidocSignatureSpan">fast-json-patch.default.</span>apply (tree, patches, validate)](#apidoc.element.fast-json-patch.default.apply)
- description and source-code
```javascript
function apply(tree, patches, validate) {
    var results = [], p = 0, plen = patches.length, patch, key;
    while (p < plen) {
        patch = patches[p];
        p++;
        // Find the object
        var path = patch.path || "";
        var keys = path.split('/');
        var obj = tree;
        var t = 1; //skip empty element - http://jsperf.com/to-shift-or-not-to-shift
        var len = keys.length;
        var existingPathFragment = undefined;
        while (true) {
            key = keys[t];
            if (validate) {
                if (existingPathFragment === undefined) {
                    if (obj[key] === undefined) {
                        existingPathFragment = keys.slice(0, t).join('/');
                    }
                    else if (t == len - 1) {
                        existingPathFragment = patch.path;
                    }
                    if (existingPathFragment !== undefined) {
                        this.validator(patch, p - 1, tree, existingPathFragment);
                    }
                }
            }
            t++;
            if (key === undefined) {
                if (t >= len) {
                    results.push(rootOps[patch.op].call(patch, obj, key, tree)); // Apply patch
                    break;
                }
            }
            if (_isArray(obj)) {
                if (key === '-') {
                    key = obj.length;
                }
                else {
                    if (validate && !isInteger(key)) {
                        throw new JsonPatchError("Expected an unsigned base-10 integer value, making the new referenced value the
 array element with the zero-based index", "OPERATION_PATH_ILLEGAL_ARRAY_INDEX", p - 1, patch.path, patch);
                    }
                    key = parseInt(key, 10);
                }
                if (t >= len) {
                    if (validate && patch.op === "add" && key > obj.length) {
                        throw new JsonPatchError("The specified index MUST NOT be greater than the number of elements in the array
", "OPERATION_VALUE_OUT_OF_BOUNDS", p - 1, patch.path, patch);
                    }
                    results.push(arrOps[patch.op].call(patch, obj, key, tree)); // Apply patch
                    break;
                }
            }
            else {
                if (key && key.indexOf('~') != -1)
                    key = key.replace(/~1/g, '/').replace(/~0/g, '~'); // escape chars
                if (t >= len) {
                    results.push(objOps[patch.op].call(patch, obj, key, tree)); // Apply patch
                    break;
                }
            }
            obj = obj[key];
        }
    }
    return results;
}
```
- example usage
```shell
...
'''js
var myobj = { firstName:"Albert", contactDetails: { phoneNumbers: [ ] } };
var patches = [
   {op:"replace", path:"/firstName", value:"Joachim" },
   {op:"add", path:"/lastName", value:"Wester" },
   {op:"add", path:"/contactDetails/phoneNumbers/0", value:{ number:"555-123" }  }
   ];
jsonpatch.apply( myobj, patches );
// myobj == { firstName:"Joachim", lastName:"Wester", contactDetails:{ phoneNumbers[ {number:"555-123"} ] } };
'''
Generating patches:

'''js
var myobj = { firstName:"Joachim", lastName:"Wester", contactDetails: { phoneNumbers: [ { number:"555-123" }] } };
observer = jsonpatch.observe( myobj );
...
```

#### <a name="apidoc.element.fast-json-patch.default.compare"></a>[function <span class="apidocSignatureSpan">fast-json-patch.default.</span>compare (tree1, tree2)](#apidoc.element.fast-json-patch.default.compare)
- description and source-code
```javascript
function compare(tree1, tree2) {
    var patches = [];
    _generate(tree1, tree2, patches, '');
    return patches;
}
```
- example usage
```shell
...
//   { op:"add", path="/contactDetails/phoneNumbers/1", value:{number:"456"}}];
'''
Comparing two object trees:

'''js
var objA = {user: {firstName: "Albert", lastName: "Einstein"}};
var objB = {user: {firstName: "Albert", lastName: "Collins"}};
var diff = jsonpatch.compare(objA, objB));
//diff == [{op: "replace", path: "/user/lastName", value: "Collins"}]
'''

Validating a sequence of patches:

'''js
var obj = {user: {firstName: "Albert"}};
...
```

#### <a name="apidoc.element.fast-json-patch.default.generate"></a>[function <span class="apidocSignatureSpan">fast-json-patch.default.</span>generate (observer)](#apidoc.element.fast-json-patch.default.generate)
- description and source-code
```javascript
function generate(observer) {
    var mirror;
    for (var i = 0, ilen = beforeDict.length; i < ilen; i++) {
        if (beforeDict[i].obj === observer.object) {
            mirror = beforeDict[i];
            break;
        }
    }
    _generate(mirror.value, observer.object, observer.patches, "");
    if (observer.patches.length) {
        apply(mirror.value, observer.patches);
    }
    var temp = observer.patches;
    if (temp.length > 0) {
        observer.patches = [];
        if (observer.callback) {
            observer.callback(temp);
        }
    }
    return temp;
}
```
- example usage
```shell
...

'''js
var myobj = { firstName:"Joachim", lastName:"Wester", contactDetails: { phoneNumbers: [ { number:"555-123" }] } };
observer = jsonpatch.observe( myobj );
myobj.firstName = "Albert";
myobj.contactDetails.phoneNumbers[0].number = "123";
myobj.contactDetails.phoneNumbers.push({number:"456"});
var patches = jsonpatch.generate(observer);
// patches  == [
//   { op:"replace", path="/firstName", value:"Albert"},
//   { op:"replace", path="/contactDetails/phoneNumbers/0/number", value:"123"},
//   { op:"add", path="/contactDetails/phoneNumbers/1", value:{number:"456"}}];
'''
Comparing two object trees:
...
```

#### <a name="apidoc.element.fast-json-patch.default.observe"></a>[function <span class="apidocSignatureSpan">fast-json-patch.default.</span>observe (obj, callback)](#apidoc.element.fast-json-patch.default.observe)
- description and source-code
```javascript
function observe(obj, callback) {
    var patches = [];
    var root = obj;
    var observer;
    var mirror = getMirror(obj);
    if (!mirror) {
        mirror = new Mirror(obj);
        beforeDict.push(mirror);
    }
    else {
        observer = getObserverFromMirror(mirror, callback);
    }
    if (observer) {
        return observer;
    }
    observer = {};
    mirror.value = deepClone(obj);
    if (callback) {
        observer.callback = callback;
        observer.next = null;
        var dirtyCheck = function () {
            generate(observer);
        };
        var fastCheck = function () {
            clearTimeout(observer.next);
            observer.next = setTimeout(dirtyCheck);
        };
        if (typeof window !== 'undefined') {
            if (window.addEventListener) {
                window.addEventListener('mouseup', fastCheck);
                window.addEventListener('keyup', fastCheck);
                window.addEventListener('mousedown', fastCheck);
                window.addEventListener('keydown', fastCheck);
                window.addEventListener('change', fastCheck);
            }
            else {
                document.documentElement.attachEvent('onmouseup', fastCheck);
                document.documentElement.attachEvent('onkeyup', fastCheck);
                document.documentElement.attachEvent('onmousedown', fastCheck);
                document.documentElement.attachEvent('onkeydown', fastCheck);
                document.documentElement.attachEvent('onchange', fastCheck);
            }
        }
    }
    observer.patches = patches;
    observer.object = obj;
    observer.unobserve = function () {
        generate(observer);
        clearTimeout(observer.next);
        removeObserverFromMirror(mirror, observer);
        if (typeof window !== 'undefined') {
            if (window.removeEventListener) {
                window.removeEventListener('mouseup', fastCheck);
                window.removeEventListener('keyup', fastCheck);
                window.removeEventListener('mousedown', fastCheck);
                window.removeEventListener('keydown', fastCheck);
            }
            else {
                document.documentElement.detachEvent('onmouseup', fastCheck);
                document.documentElement.detachEvent('onkeyup', fastCheck);
                document.documentElement.detachEvent('onmousedown', fastCheck);
                document.documentElement.detachEvent('onkeydown', fastCheck);
            }
        }
    };
    mirror.observers.push(new ObserverInfo(callback, observer));
    return observer;
}
```
- example usage
```shell
...
jsonpatch.apply( myobj, patches );
// myobj == { firstName:"Joachim", lastName:"Wester", contactDetails:{ phoneNumbers[ {number:"555-123"} ] } };
'''
Generating patches:

'''js
var myobj = { firstName:"Joachim", lastName:"Wester", contactDetails: { phoneNumbers: [ { number:"555-123" }] } };
observer = jsonpatch.observe( myobj );
myobj.firstName = "Albert";
myobj.contactDetails.phoneNumbers[0].number = "123";
myobj.contactDetails.phoneNumbers.push({number:"456"});
var patches = jsonpatch.generate(observer);
// patches  == [
//   { op:"replace", path="/firstName", value:"Albert"},
//   { op:"replace", path="/contactDetails/phoneNumbers/0/number", value:"123"},
...
```

#### <a name="apidoc.element.fast-json-patch.default.unobserve"></a>[function <span class="apidocSignatureSpan">fast-json-patch.default.</span>unobserve (root, observer)](#apidoc.element.fast-json-patch.default.unobserve)
- description and source-code
```javascript
function unobserve(root, observer) {
    observer.unobserve();
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.fast-json-patch.default.validate"></a>[function <span class="apidocSignatureSpan">fast-json-patch.default.</span>validate (sequence, tree)](#apidoc.element.fast-json-patch.default.validate)
- description and source-code
```javascript
function validate(sequence, tree) {
    try {
        if (!_isArray(sequence)) {
            throw new JsonPatchError('Patch sequence must be an array', 'SEQUENCE_NOT_AN_ARRAY');
        }
        if (tree) {
            tree = JSON.parse(JSON.stringify(tree)); //clone tree so that we can safely try applying operations
            apply.call(this, tree, sequence, true);
        }
        else {
            for (var i = 0; i < sequence.length; i++) {
                this.validator(sequence[i], i);
            }
        }
    }
    catch (e) {
        if (e instanceof JsonPatchError) {
            return e;
        }
        else {
            throw e;
        }
    }
}
```
- example usage
```shell
...
'''

Validating a sequence of patches:

'''js
var obj = {user: {firstName: "Albert"}};
var patches = [{op: "replace", path: "/user/firstName", value: "Albert"}, {op: "replace", path: "/user/lastName", value: "Einstein
"}];
var errors = jsonpatch.validate(patches, obj);
if (errors.length == 0) {
 //there are no errors!
}
else {
for (var i=0; i < errors.length; i++) {
  if (!errors[i]) {
    console.log("Valid patch at index", i, patches[i]);
...
```

#### <a name="apidoc.element.fast-json-patch.default.validator"></a>[function <span class="apidocSignatureSpan">fast-json-patch.default.</span>validator (operation, index, tree, existingPathFragment)](#apidoc.element.fast-json-patch.default.validator)
- description and source-code
```javascript
function validator(operation, index, tree, existingPathFragment) {
    if (typeof operation !== 'object' || operation === null || _isArray(operation)) {
        throw new JsonPatchError('Operation is not an object', 'OPERATION_NOT_AN_OBJECT', index, operation, tree);
    }
    else if (!objOps[operation.op]) {
        throw new JsonPatchError('Operation 'op' property is not one of operations defined in RFC-6902', 'OPERATION_OP_INVALID',
index, operation, tree);
    }
    else if (typeof operation.path !== 'string') {
        throw new JsonPatchError('Operation 'path' property is not a string', 'OPERATION_PATH_INVALID', index, operation, tree);
    }
    else if (operation.path.indexOf('/') !== 0 && operation.path.length > 0) {
        // paths that aren't emptystring should start with "/"
        throw new JsonPatchError('Operation 'path' property must start with "/"', 'OPERATION_PATH_INVALID', index, operation, tree
);
    }
    else if ((operation.op === 'move' || operation.op === 'copy') && typeof operation.from !== 'string') {
        throw new JsonPatchError('Operation 'from' property is not present (applicable in 'move' and 'copy' operations)', 'OPERATION_FROM_REQUIRED
', index, operation, tree);
    }
    else if ((operation.op === 'add' || operation.op === 'replace' || operation.op === 'test') && operation.value === undefined) {
        throw new JsonPatchError('Operation 'value' property is not present (applicable in 'add', 'replace' and 'test' operations
)', 'OPERATION_VALUE_REQUIRED', index, operation, tree);
    }
    else if ((operation.op === 'add' || operation.op === 'replace' || operation.op === 'test') && hasUndefined(operation.value)) {
        throw new JsonPatchError('Operation 'value' property is not present (applicable in 'add', 'replace' and 'test' operations
)', 'OPERATION_VALUE_CANNOT_CONTAIN_UNDEFINED', index, operation, tree);
    }
    else if (tree) {
        if (operation.op == "add") {
            var pathLen = operation.path.split("/").length;
            var existingPathLen = existingPathFragment.split("/").length;
            if (pathLen !== existingPathLen + 1 && pathLen !== existingPathLen) {
                throw new JsonPatchError('Cannot perform an 'add' operation at the desired path', 'OPERATION_PATH_CANNOT_ADD', index
, operation, tree);
            }
        }
        else if (operation.op === 'replace' || operation.op === 'remove' || operation.op === '_get') {
            if (operation.path !== existingPathFragment) {
                throw new JsonPatchError('Cannot perform the operation at a path that does not exist', 'OPERATION_PATH_UNRESOLVABLE
', index, operation, tree);
            }
        }
        else if (operation.op === 'move' || operation.op === 'copy') {
            var existingValue = { op: "_get", path: operation.from, value: undefined };
            var error = jsonpatch.validate([existingValue], tree);
            if (error && error.name === 'OPERATION_PATH_UNRESOLVABLE') {
                throw new JsonPatchError('Cannot perform the operation from a path that does not exist', 'OPERATION_FROM_UNRESOLVABLE
', index, operation, tree);
            }
        }
    }
}
```
- example usage
```shell
...
        if (obj[key] === undefined) {
            existingPathFragment = keys.slice(0, t).join('/');
        }
        else if (t == len - 1) {
            existingPathFragment = patch.path;
        }
        if (existingPathFragment !== undefined) {
            this.validator(patch, p - 1, tree, existingPathFragment);
        }
    }
}
t++;
if (key === undefined) {
    if (t >= len) {
        results[p - 1] = rootOps[patch.op].call(patch, obj, key, tree); // Apply patch
...
```



# <a name="apidoc.module.fast-json-patch.json_patch"></a>[module fast-json-patch.json_patch](#apidoc.module.fast-json-patch.json_patch)

#### <a name="apidoc.element.fast-json-patch.json_patch.JsonPatchError"></a>[function <span class="apidocSignatureSpan">fast-json-patch.json_patch.</span>JsonPatchError (message, name, index, operation, tree)](#apidoc.element.fast-json-patch.json_patch.JsonPatchError)
- description and source-code
```javascript
function JsonPatchError(message, name, index, operation, tree) {
    _super.call(this, message);
    this.message = message;
    this.name = name;
    this.index = index;
    this.operation = operation;
    this.tree = tree;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.fast-json-patch.json_patch.apply"></a>[function <span class="apidocSignatureSpan">fast-json-patch.json_patch.</span>apply (tree, patches, validate)](#apidoc.element.fast-json-patch.json_patch.apply)
- description and source-code
```javascript
function apply(tree, patches, validate) {
    var results = new Array(patches.length), p = 0, plen = patches.length, patch, key;
    while (p < plen) {
        patch = patches[p];
        p++;
        // Find the object
        var path = patch.path || "";
        var keys = path.split('/');
        var obj = tree;
        var t = 1; //skip empty element - http://jsperf.com/to-shift-or-not-to-shift
        var len = keys.length;
        var existingPathFragment = undefined;
        while (true) {
            key = keys[t];
            if (validate) {
                if (existingPathFragment === undefined) {
                    if (obj[key] === undefined) {
                        existingPathFragment = keys.slice(0, t).join('/');
                    }
                    else if (t == len - 1) {
                        existingPathFragment = patch.path;
                    }
                    if (existingPathFragment !== undefined) {
                        this.validator(patch, p - 1, tree, existingPathFragment);
                    }
                }
            }
            t++;
            if (key === undefined) {
                if (t >= len) {
                    results[p - 1] = rootOps[patch.op].call(patch, obj, key, tree); // Apply patch
                    break;
                }
            }
            if (_isArray(obj)) {
                if (key === '-') {
                    key = obj.length;
                }
                else {
                    if (validate && !isInteger(key)) {
                        throw new JsonPatchError("Expected an unsigned base-10 integer value, making the new referenced value the
 array element with the zero-based index", "OPERATION_PATH_ILLEGAL_ARRAY_INDEX", p - 1, patch.path, patch);
                    }
                    key = parseInt(key, 10);
                }
                if (t >= len) {
                    if (validate && patch.op === "add" && key > obj.length) {
                        throw new JsonPatchError("The specified index MUST NOT be greater than the number of elements in the array
", "OPERATION_VALUE_OUT_OF_BOUNDS", p - 1, patch.path, patch);
                    }
                    results[p - 1] = arrOps[patch.op].call(patch, obj, key, tree); // Apply patch
                    break;
                }
            }
            else {
                if (key && key.indexOf('~') != -1)
                    key = key.replace(/~1/g, '/').replace(/~0/g, '~'); // escape chars
                if (t >= len) {
                    results[p - 1] = objOps[patch.op].call(patch, obj, key, tree); // Apply patch
                    break;
                }
            }
            obj = obj[key];
        }
    }
    return results;
}
```
- example usage
```shell
...
'''js
var myobj = { firstName:"Albert", contactDetails: { phoneNumbers: [ ] } };
var patches = [
   {op:"replace", path:"/firstName", value:"Joachim" },
   {op:"add", path:"/lastName", value:"Wester" },
   {op:"add", path:"/contactDetails/phoneNumbers/0", value:{ number:"555-123" }  }
   ];
jsonpatch.apply( myobj, patches );
// myobj == { firstName:"Joachim", lastName:"Wester", contactDetails:{ phoneNumbers[ {number:"555-123"} ] } };
'''
Generating patches:

'''js
var myobj = { firstName:"Joachim", lastName:"Wester", contactDetails: { phoneNumbers: [ { number:"555-123" }] } };
observer = jsonpatch.observe( myobj );
...
```

#### <a name="apidoc.element.fast-json-patch.json_patch.validate"></a>[function <span class="apidocSignatureSpan">fast-json-patch.json_patch.</span>validate (sequence, tree)](#apidoc.element.fast-json-patch.json_patch.validate)
- description and source-code
```javascript
function validate(sequence, tree) {
    try {
        if (!_isArray(sequence)) {
            throw new JsonPatchError('Patch sequence must be an array', 'SEQUENCE_NOT_AN_ARRAY');
        }
        if (tree) {
            tree = JSON.parse(JSON.stringify(tree)); //clone tree so that we can safely try applying operations
            apply.call(this, tree, sequence, true);
        }
        else {
            for (var i = 0; i < sequence.length; i++) {
                this.validator(sequence[i], i);
            }
        }
    }
    catch (e) {
        if (e instanceof JsonPatchError) {
            return e;
        }
        else {
            throw e;
        }
    }
}
```
- example usage
```shell
...
'''

Validating a sequence of patches:

'''js
var obj = {user: {firstName: "Albert"}};
var patches = [{op: "replace", path: "/user/firstName", value: "Albert"}, {op: "replace", path: "/user/lastName", value: "Einstein
"}];
var errors = jsonpatch.validate(patches, obj);
if (errors.length == 0) {
 //there are no errors!
}
else {
for (var i=0; i < errors.length; i++) {
  if (!errors[i]) {
    console.log("Valid patch at index", i, patches[i]);
...
```

#### <a name="apidoc.element.fast-json-patch.json_patch.validator"></a>[function <span class="apidocSignatureSpan">fast-json-patch.json_patch.</span>validator (operation, index, tree, existingPathFragment)](#apidoc.element.fast-json-patch.json_patch.validator)
- description and source-code
```javascript
function validator(operation, index, tree, existingPathFragment) {
    if (typeof operation !== 'object' || operation === null || _isArray(operation)) {
        throw new JsonPatchError('Operation is not an object', 'OPERATION_NOT_AN_OBJECT', index, operation, tree);
    }
    else if (!objOps[operation.op]) {
        throw new JsonPatchError('Operation 'op' property is not one of operations defined in RFC-6902', 'OPERATION_OP_INVALID',
index, operation, tree);
    }
    else if (typeof operation.path !== 'string') {
        throw new JsonPatchError('Operation 'path' property is not a string', 'OPERATION_PATH_INVALID', index, operation, tree);
    }
    else if (operation.path.indexOf('/') !== 0 && operation.path.length > 0) {
        // paths that aren't emptystring should start with "/"
        throw new JsonPatchError('Operation 'path' property must start with "/"', 'OPERATION_PATH_INVALID', index, operation, tree
);
    }
    else if ((operation.op === 'move' || operation.op === 'copy') && typeof operation.from !== 'string') {
        throw new JsonPatchError('Operation 'from' property is not present (applicable in 'move' and 'copy' operations)', 'OPERATION_FROM_REQUIRED
', index, operation, tree);
    }
    else if ((operation.op === 'add' || operation.op === 'replace' || operation.op === 'test') && operation.value === undefined) {
        throw new JsonPatchError('Operation 'value' property is not present (applicable in 'add', 'replace' and 'test' operations
)', 'OPERATION_VALUE_REQUIRED', index, operation, tree);
    }
    else if ((operation.op === 'add' || operation.op === 'replace' || operation.op === 'test') && hasUndefined(operation.value)) {
        throw new JsonPatchError('Operation 'value' property is not present (applicable in 'add', 'replace' and 'test' operations
)', 'OPERATION_VALUE_CANNOT_CONTAIN_UNDEFINED', index, operation, tree);
    }
    else if (tree) {
        if (operation.op == "add") {
            var pathLen = operation.path.split("/").length;
            var existingPathLen = existingPathFragment.split("/").length;
            if (pathLen !== existingPathLen + 1 && pathLen !== existingPathLen) {
                throw new JsonPatchError('Cannot perform an 'add' operation at the desired path', 'OPERATION_PATH_CANNOT_ADD', index
, operation, tree);
            }
        }
        else if (operation.op === 'replace' || operation.op === 'remove' || operation.op === '_get') {
            if (operation.path !== existingPathFragment) {
                throw new JsonPatchError('Cannot perform the operation at a path that does not exist', 'OPERATION_PATH_UNRESOLVABLE
', index, operation, tree);
            }
        }
        else if (operation.op === 'move' || operation.op === 'copy') {
            var existingValue = { op: "_get", path: operation.from, value: undefined };
            var error = jsonpatch.validate([existingValue], tree);
            if (error && error.name === 'OPERATION_PATH_UNRESOLVABLE') {
                throw new JsonPatchError('Cannot perform the operation from a path that does not exist', 'OPERATION_FROM_UNRESOLVABLE
', index, operation, tree);
            }
        }
    }
}
```
- example usage
```shell
...
        if (obj[key] === undefined) {
            existingPathFragment = keys.slice(0, t).join('/');
        }
        else if (t == len - 1) {
            existingPathFragment = patch.path;
        }
        if (existingPathFragment !== undefined) {
            this.validator(patch, p - 1, tree, existingPathFragment);
        }
    }
}
t++;
if (key === undefined) {
    if (t >= len) {
        results[p - 1] = rootOps[patch.op].call(patch, obj, key, tree); // Apply patch
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
