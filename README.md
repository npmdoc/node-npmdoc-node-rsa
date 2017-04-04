# api documentation for  [node-rsa (v0.4.2)](https://github.com/rzcoder/node-rsa)  [![npm package](https://img.shields.io/npm/v/npmdoc-node-rsa.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-node-rsa) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-node-rsa.svg)](https://travis-ci.org/npmdoc/node-npmdoc-node-rsa)
#### Node.js RSA library

[![NPM](https://nodei.co/npm/node-rsa.png?downloads=true)](https://www.npmjs.com/package/node-rsa)

[![apidoc](https://npmdoc.github.io/node-npmdoc-node-rsa/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-node-rsa_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-node-rsa/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-node-rsa/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-node-rsa/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "rzcoder"
    },
    "bugs": {
        "url": "https://github.com/rzcoder/node-rsa/issues"
    },
    "dependencies": {
        "asn1": "0.2.3"
    },
    "description": "Node.js RSA library",
    "devDependencies": {
        "chai": "^3.5.0",
        "grunt": "^1.0.1",
        "grunt-contrib-jshint": "^1.0.0",
        "grunt-simple-mocha": "^0.4.1",
        "jit-grunt": "^0.10.0",
        "lodash": "^4.13.1"
    },
    "directories": {},
    "dist": {
        "shasum": "d6391729ec16a830ed5a38042b3157d2d5d72530",
        "tarball": "https://registry.npmjs.org/node-rsa/-/node-rsa-0.4.2.tgz"
    },
    "gitHead": "5f169c8152ccf54238654ceb363bf724b02d5595",
    "homepage": "https://github.com/rzcoder/node-rsa",
    "keywords": [
        "node",
        "rsa",
        "crypto",
        "assymetric",
        "encryption",
        "decryption",
        "sign",
        "verify",
        "pkcs1",
        "oaep",
        "pss"
    ],
    "license": "MIT",
    "main": "src/NodeRSA.js",
    "maintainers": [
        {
            "name": "rzcoder",
            "email": "rzcoder@gmail.com"
        }
    ],
    "name": "node-rsa",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/rzcoder/node-rsa.git"
    },
    "scripts": {
        "test": "grunt test"
    },
    "version": "0.4.2"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module node-rsa](#apidoc.module.node-rsa)
1.  object <span class="apidocSignatureSpan">node-rsa.</span>utils

#### [module node-rsa.utils](#apidoc.module.node-rsa.utils)
1.  [function <span class="apidocSignatureSpan">node-rsa.utils.</span>detectEnvironment ()](#apidoc.element.node-rsa.utils.detectEnvironment)
1.  [function <span class="apidocSignatureSpan">node-rsa.utils.</span>get32IntFromBuffer (buffer, offset)](#apidoc.element.node-rsa.utils.get32IntFromBuffer)
1.  [function <span class="apidocSignatureSpan">node-rsa.utils.</span>linebrk (str, maxLen)](#apidoc.element.node-rsa.utils.linebrk)
1.  object <span class="apidocSignatureSpan">node-rsa.utils.</span>_



# <a name="apidoc.module.node-rsa"></a>[module node-rsa](#apidoc.module.node-rsa)



# <a name="apidoc.module.node-rsa.utils"></a>[module node-rsa.utils](#apidoc.module.node-rsa.utils)

#### <a name="apidoc.element.node-rsa.utils.detectEnvironment"></a>[function <span class="apidocSignatureSpan">node-rsa.utils.</span>detectEnvironment ()](#apidoc.element.node-rsa.utils.detectEnvironment)
- description and source-code
```javascript
detectEnvironment = function () {
    if (process && process.title === 'browser' || (typeof(window) !== 'undefined' && window)) {
        return 'browser';
    }

    return 'node';
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.node-rsa.utils.get32IntFromBuffer"></a>[function <span class="apidocSignatureSpan">node-rsa.utils.</span>get32IntFromBuffer (buffer, offset)](#apidoc.element.node-rsa.utils.get32IntFromBuffer)
- description and source-code
```javascript
get32IntFromBuffer = function (buffer, offset) {
    offset = offset || 0;
    var size = 0;
    if ((size = buffer.length - offset) > 0) {
        if (size >= 4) {
            return buffer.readUInt32BE(offset);
        } else {
            var res = 0;
            for (var i = offset + size, d = 0; i > offset; i--, d += 2) {
                res += buffer[i - 1] * Math.pow(16, d);
            }
            return res;
        }
    } else {
        return NaN;
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.node-rsa.utils.linebrk"></a>[function <span class="apidocSignatureSpan">node-rsa.utils.</span>linebrk (str, maxLen)](#apidoc.element.node-rsa.utils.linebrk)
- description and source-code
```javascript
linebrk = function (str, maxLen) {
    var res = '';
    var i = 0;
    while (i + maxLen < str.length) {
        res += str.substring(i, i + maxLen) + "\n";
        i += maxLen;
    }
    return res + str.substring(i, str.length);
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
