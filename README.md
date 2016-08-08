# meteor-absolute-path-bug
Repository for reproduction of meteor absolute path in node modules
## Reproduction steps
```
C:\>git clone https://github.com/Kurounin/meteor-absolute-path-bug.git
Cloning into 'meteor-absolute-path-bug'...
remote: Counting objects: 18, done.
remote: Compressing objects: 100% (13/13), done.
remote: Total 18 (delta 0), reused 14 (delta 0), pack-reused 0
Unpacking objects: 100% (18/18), done.
Checking connectivity... done.

C:\>cd meteor-absolute-path-bug

C:\meteor-absolute-path-bug>meteor npm install

> kerberos@0.0.21 install C:\meteor-absolute-path-bug\node_modules\kerberos
> (node-gyp rebuild) || (exit 0)

Building the projects in this solution one at a time. To enable parallel build, please add the "/m" switch.
  kerberos.cc
  worker.cc
  security_buffer.cc
  security_buffer_descriptor.cc
  security_context.cc
  security_credentials.cc
  win_delay_load_hook.cc
  base64.c
  kerberos_sspi.c
     Creating library C:\meteor-absolute-path-bug\node_modules\kerberos\build\Release\kerberos.lib and object C:\meteor
  -absolute-path-bug\node_modules\kerberos\build\Release\kerberos.exp
  Generating code
  Finished generating code
  kerberos.vcxproj -> C:\meteor-absolute-path-bug\node_modules\kerberos\build\Release\\kerberos.node
  kerberos.vcxproj -> C:\meteor-absolute-path-bug\node_modules\kerberos\build\Release\kerberos.pdb (Full PDB)
absolute-path@ C:\meteor-absolute-path-bug
+-- kerberos@0.0.21
| `-- nan@2.3.5
`-- meteor-node-stubs@0.2.3
  +-- assert@1.3.0
  +-- browserify-zlib@0.1.4
  | `-- pako@0.2.8
  +-- buffer@4.5.1
  | +-- base64-js@1.1.2
  | +-- ieee754@1.1.6
  | `-- isarray@1.0.0
  +-- console-browserify@1.1.0
  | `-- date-now@0.1.4
  +-- constants-browserify@1.0.0
  +-- crypto-browserify@3.11.0
  | +-- browserify-cipher@1.0.0
  | | +-- browserify-aes@1.0.6
  | | | +-- buffer-xor@1.0.3
  | | | `-- cipher-base@1.0.2
  | | +-- browserify-des@1.0.0
  | | | +-- cipher-base@1.0.2
  | | | `-- des.js@1.0.0
  | | |   `-- minimalistic-assert@1.0.0
  | | `-- evp_bytestokey@1.0.0
  | +-- browserify-sign@4.0.0
  | | +-- bn.js@4.11.1
  | | +-- browserify-rsa@4.0.1
  | | +-- elliptic@6.2.3
  | | | +-- brorand@1.0.5
  | | | `-- hash.js@1.0.3
  | | `-- parse-asn1@5.0.0
  | |   +-- asn1.js@4.5.2
  | |   | `-- minimalistic-assert@1.0.0
  | |   +-- browserify-aes@1.0.6
  | |   | +-- buffer-xor@1.0.3
  | |   | `-- cipher-base@1.0.2
  | |   `-- evp_bytestokey@1.0.0
  | +-- create-ecdh@4.0.0
  | | +-- bn.js@4.11.1
  | | `-- elliptic@6.2.3
  | |   +-- brorand@1.0.5
  | |   `-- hash.js@1.0.3
  | +-- create-hash@1.1.2
  | | +-- cipher-base@1.0.2
  | | +-- ripemd160@1.0.1
  | | `-- sha.js@2.4.5
  | +-- create-hmac@1.1.4
  | +-- diffie-hellman@5.0.2
  | | +-- bn.js@4.11.1
  | | `-- miller-rabin@4.0.0
  | |   `-- brorand@1.0.5
  | +-- inherits@2.0.1
  | +-- pbkdf2@3.0.4
  | +-- public-encrypt@4.0.0
  | | +-- bn.js@4.11.1
  | | +-- browserify-rsa@4.0.1
  | | `-- parse-asn1@5.0.0
  | |   +-- asn1.js@4.5.2
  | |   | `-- minimalistic-assert@1.0.0
  | |   +-- browserify-aes@1.0.6
  | |   | +-- buffer-xor@1.0.3
  | |   | `-- cipher-base@1.0.2
  | |   `-- evp_bytestokey@1.0.0
  | `-- randombytes@2.0.3
  +-- domain-browser@1.1.7
  +-- events@1.1.0
  +-- http-browserify@1.7.0
  | +-- Base64@0.2.1
  | `-- inherits@2.0.1
  +-- https-browserify@0.0.1
  +-- os-browserify@0.2.1
  +-- path-browserify@0.0.0
  +-- process@0.11.2
  +-- punycode@1.4.1
  +-- querystring-es3@0.2.1
  +-- readable-stream@2.0.6
  | +-- core-util-is@1.0.2
  | +-- inherits@2.0.1
  | +-- isarray@1.0.0
  | +-- process-nextick-args@1.0.6
  | `-- util-deprecate@1.0.2
  +-- stream-browserify@2.0.1
  | `-- inherits@2.0.1
  +-- string_decoder@0.10.31
  +-- timers-browserify@1.4.2
  +-- tty-browserify@0.0.0
  +-- url@0.11.0
  | +-- punycode@1.3.2
  | `-- querystring@0.2.0
  +-- util@0.10.3
  | `-- inherits@2.0.1
  `-- vm-browserify@0.0.4
    `-- indexof@0.0.1


C:\meteor-absolute-path-bug>meteor run
[[[[[ C:\meteor-absolute-path-bug ]]]]]

=> Started proxy.
=> Started MongoDB.
C:\Users\catalin\AppData\Local\.meteor\packages\meteor-tool\1.4.0-1\mt-os.windows.x86_32\isopackets\ddp\npm\node_modules\meteor\promise\node_modules\meteor-promise\promise_server.js:165
      throw error;
      ^

Error: Surprising path: /build/Release/kerberos
    at toDosPath (C:\Users\catalin\AppData\Local\.meteor\packages\meteor-tool\1.4.0-1\mt-os.windows.x86_32\tools\static-assets\server\mini-files.js:35:13)
    at C:\Users\catalin\AppData\Local\.meteor\packages\meteor-tool\1.4.0-1\mt-os.windows.x86_32\tools\static-assets\server\mini-files.js:85:16
    at Array.map (native)
    at Function._.map._.collect (C:\Users\catalin\AppData\Local\.meteor\packages\meteor-tool\1.4.0-1\mt-os.windows.x86_32\dev_bundle\lib\node_modules\underscore\underscore.js:97:56)
    at C:\Users\catalin\AppData\Local\.meteor\packages\meteor-tool\1.4.0-1\mt-os.windows.x86_32\tools\static-assets\server\mini-files.js:82:16
    at Resolver._joinAndStat (C:\tools\isobuild\resolver.js:141:18)
    at Resolver._resolveNodeModule (C:\tools\isobuild\resolver.js:218:33)
    at Resolver.resolve (C:\tools\isobuild\resolver.js:95:12)
    at C:\tools\isobuild\import-scanner.js:477:38
    at _.each._.forEach (C:\Users\catalin\AppData\Local\.meteor\packages\meteor-tool\1.4.0-1\mt-os.windows.x86_32\dev_bundle\lib\node_modules\underscore\underscore.js:87:22)
    at ImportScanner._scanFile (C:\tools\isobuild\import-scanner.js:476:5)
    at C:\tools\isobuild\import-scanner.js:539:12
    at _.each._.forEach (C:\Users\catalin\AppData\Local\.meteor\packages\meteor-tool\1.4.0-1\mt-os.windows.x86_32\dev_bundle\lib\node_modules\underscore\underscore.js:87:22)
    at ImportScanner._scanFile (C:\tools\isobuild\import-scanner.js:476:5)
    at C:\tools\isobuild\import-scanner.js:539:12
    at _.each._.forEach (C:\Users\catalin\AppData\Local\.meteor\packages\meteor-tool\1.4.0-1\mt-os.windows.x86_32\dev_bundle\lib\node_modules\underscore\underscore.js:87:22)
    at ImportScanner._scanFile (C:\tools\isobuild\import-scanner.js:476:5)
    at C:\tools\isobuild\import-scanner.js:539:12
    at _.each._.forEach (C:\Users\catalin\AppData\Local\.meteor\packages\meteor-tool\1.4.0-1\mt-os.windows.x86_32\dev_bundle\lib\node_modules\underscore\underscore.js:87:22)
    at ImportScanner._scanFile (C:\tools\isobuild\import-scanner.js:476:5)
    at C:\tools\isobuild\import-scanner.js:338:14
    at Array.forEach (native)
    at ImportScanner.scanImports (C:\tools\isobuild\import-scanner.js:336:22)
    at C:\tools\isobuild\compiler-plugin.js:1014:17
    at Array.forEach (native)
    at Function.computeJsOutputFilesMap (C:\tools\isobuild\compiler-plugin.js:982:19)
    at ServerTarget._emitResources (C:\tools\isobuild\bundler.js:926:8)
    at C:\tools\isobuild\bundler.js:697:12
    at C:\tools\utils\buildmessage.js:359:18
    at [object Object].withValue (C:\tools\utils\fiber-helpers.js:89:14)
    at C:\tools\utils\buildmessage.js:352:34
    at [object Object].withValue (C:\tools\utils\fiber-helpers.js:89:14)
    at C:\tools\utils\buildmessage.js:350:23
    at [object Object].withValue (C:\tools\utils\fiber-helpers.js:89:14)
    at Object.enterJob (C:\tools\utils\buildmessage.js:324:26)
    at ServerTarget.make (C:\tools\isobuild\bundler.js:688:18)
    at C:\tools\isobuild\bundler.js:2572:14
    at C:\tools\isobuild\bundler.js:2640:20
    at C:\tools\utils\buildmessage.js:271:13
    at [object Object].withValue (C:\tools\utils\fiber-helpers.js:89:14)
    at C:\tools\utils\buildmessage.js:264:29
    at [object Object].withValue (C:\tools\utils\fiber-helpers.js:89:14)
    at C:\tools\utils\buildmessage.js:262:18
    at [object Object].withValue (C:\tools\utils\fiber-helpers.js:89:14)
    at C:\tools\utils\buildmessage.js:253:23
    at [object Object].withValue (C:\tools\utils\fiber-helpers.js:89:14)
    at Object.capture (C:\tools\utils\buildmessage.js:252:19)
    at bundle (C:\tools\isobuild\bundler.js:2525:31)
    at C:\tools\isobuild\bundler.js:2472:32
    at Object.withCache (C:\tools\fs\files.js:1445:12)
    at Object.exports.bundle (C:\tools\isobuild\bundler.js:2472:16)
    at C:\tools\runners\run-app.js:591:36
    at Function.run (C:\tools\tool-env\profile.js:489:12)
    at bundleApp (C:\tools\runners\run-app.js:581:34)
    at AppRunner._runOnce (C:\tools\runners\run-app.js:634:35)
    at AppRunner._fiber (C:\tools\runners\run-app.js:893:28)
    at C:\tools\runners\run-app.js:411:12

C:\meteor-absolute-path-bug>
```
