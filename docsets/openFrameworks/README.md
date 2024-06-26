# Docset for openFrameworks

Created by [Yi donghoon](https://github.com/icq4ever), [@icq4ever.dev](https://instagram.com/icq4ever.dev/)

## generate docset for Dash

### dependencies 
To create this docset, we need two application
- [doxytag2zealdb](https://github.com/vedvyas/doxytag2zealdb) 
- [dashing](https://github.com/technosophos/dashing#readme) : `dsidx` is not generated by doxygen. so we need this.

### instruction
1. edit `Doxyfile` in `_OF_DIR_/libs/openFrameworksCompiled/project/doxygen/`
    - set `GENERATE_DOCSET` to `YES` 
    - set `DISABLE_INDEX` to `YES` 
    - set `GENERATE_TAGFILE` value = `openFrameworks.tag` 
2. run `doxygen` in `_OF_DIR_/libs/openFrameworksCompiled/project/doxygen/`
3. generate `dsidx` with `dashing`
    - `dashing create` in `build/html` directory
    - edit `dashing.json` as below
    ``` 
    {
        "name": "openFrameworks",
        "package": "openFrameworks",
        "index": "index.html",
        "selectors": {
            "dt a": "Command",
            "title": "Package"
        },
        "ignore": [
            "ABOUT"
        ],
        "icon32x32": "oF_logo_32x32.png",   // prepare logo png in `build/html` directory
        "allowJS": false,
        "ExternalURL": "http://openframeworks.cc"
    }
    ```
    - `dashing build .` in `build/html`
  
4. generate index with [doxytag2zealdb](https://github.com/vedvyas/doxytag2zealdb) in `_OF_DIR_/libs/openFrameworksCompiled/project/doxygen` directory, with terminal command below.
    ```
    $ doxytag2zealdb --tag ./openFrameworks.tag --db ./build/html/openFrameworks.docset/Contents/Resources/docSet.dsidx --include-parent-scopes --include-function-signatures
    ```
5. update plist if needed.
6. rename `.docset` folder if needed.
7. archive `.docset` folder to `.tgz` and pull request.



---

## Contributions
#### Docset for openFrameworks 0.12.0 
- Created by [Yi donghoon](https://github.com/icq4ever), [@icq4ever.dev](https://instagram.com/icq4ever)

#### Docset for openFrameworks 0.11.1
- Created by [Yi donghoon](https://github.com/icq4ever), [@icq4ever](https://twitter.com/icq4ever)
- 
#### Docset for openFrameworks 0.11.0 
- Created by [Yi donghoon](https://github.com/icq4ever), [@icq4ever](https://twitter.com/icq4ever)

#### Docset for openFrameworks 0.10.1 
- Created by [Yi donghoon](https://github.com/icq4ever), [@icq4ever](https://twitter.com/icq4ever)

#### Docset for openFrameworks 0.10.0 
- Created by [Yi donghoon](https://github.com/icq4ever), [@icq4ever](https://twitter.com/icq4ever)

#### Docset for openFrameworks 0.9.8
- Created by [Yi donghoon](https://github.com/icq4ever), [@icq4ever](https://twitter.com/icq4ever)

#### Docset for openFrameworks 0.9.3 

- Created by [Yi donghoon](https://github.com/icq4ever), [@icq4ever](https://twitter.com/icq4ever)

#### Docset for openFrameworks 0.8.4 

- Created by [Marcus Ficner](https://github.com/mficner), [@marcusficner](https://twitter.com/marcusficner)
