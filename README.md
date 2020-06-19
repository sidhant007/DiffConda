A script that checks if all the packages mentioned in the YAML conda file is a subset of the packages in the current conda environment.

Incase any package is missing or there are version mismatches they are reported.

In version equality matching, we match empty versions, version prefixes and wildcards correctly.

Ex.
```
0.6.4 == '' (empty)
0.6.4 == 0.6.4
0.6.4 == 0.6.*
0.6.4 == 0.*.4
0.6.4 == 0.*.*
0.6.4 == 0 
0.6.4 == 0.6 
0.6.4 != 0.6*
0.6.4 != 0.6.
```

Also, nested lists in `dependencies` (most popluar example being `pip` is ignored in the diff)

Ex. 
```
dependencies:
  - pip:
    - Flask-Testing
    - abc
```
