# nodejs extension example write by napi

# pre-install

  nvm install 9.3.0

  npm i

# setup binding.gyp for compile napi

```
{
  "targets": [
    { 
      "cflags!": [ "-fno-exceptions" ],
      "cflags_cc!": [ "-fno-exceptions" ],
      "include_dirs" : [
        "<!@(node -p \"require('node-addon-api').include\")"
      ],
      "target_name": "hello_world",
      "sources": [ "hello_world.cc" ],
      'defines': [ 'NAPI_DISABLE_CPP_EXCEPTIONS' ]
    }
  ]
}
```
[ref](https://medium.com/the-node-js-collection/native-extensions-for-node-js-767e221b3d26)

# what is more?

  napi is still expirement feature in node v9.3

  but will be stable in node v10