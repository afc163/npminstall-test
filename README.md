## npminstall result compare

Fixed `rc-util` and `@types/react` version in parent dependencies.

npminstall-test-child package.json: https://unpkg.com/npminstall-test-child@2.0.0/package.json

### default way

It will install `rc-util` and `@types/react` according to `npminstall-test-child`'s dependencies.

```
tnpm install
```

```
├─┬ npminstall-test-child@2.0.0 -> /Users/afc163/Projects/npminstall-test/node_modules/.2.0.0@npminstall-test-child
│ ├── @types/react@15.0.6
│ └─┬ rc-util@4.0.2
│   ├── add-dom-event-listener@1.0.2
│   └─┬ shallowequal@0.2.2
│     └─┬ lodash.keys@3.1.2
│       ├── lodash._getnative@3.9.1
│       ├── lodash.isarguments@3.1.0
│       └── lodash.isarray@3.0.4
├── object-assign@4.1.1 -> /Users/afc163/Projects/npminstall-test/node_modules/.4.1.1@object-assign extraneous
├─┬ rc-util@4.0.0 -> /Users/afc163/Projects/npminstall-test/node_modules/.4.0.0@rc-util
│ └─┬ add-dom-event-listener@1.0.2
│   └── object-assign@4.1.1
└── shallowequal@0.2.2 -> /Users/afc163/Projects/npminstall-test/node_modules/.0.2.2@shallowequal extraneous
```

### by npm

It will install `rc-util` and `@types/react` according to `npminstall-test-parent`'s dependencies.

```
tnpm install --by=npm
```

```
├── @types/react@15.0.4
├── npminstall-test-child@2.0.0
└─┬ rc-util@4.0.0
  └─┬ add-dom-event-listener@1.0.2
    └── object-assign@4.1.1
```
