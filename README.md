# mongoexec

Wrapper for executing scripts from command line with MongoDB.

## Installation

Place `mongoexec` in some directory which is part of the `$PATH` variable, e.g:

```
sudo wget -O /usr/bin/mongoexec https://raw.githubusercontent.com/pveierland/mongoexec/master/mongoexec
```

## Usage

Place a [shebang](https://en.wikipedia.org/wiki/Shebang_(Unix)) at the start of the JavaScript file you wish to execute:

```
#!/usr/bin/mongoexec --quiet
```

The `--quiet` represents an optional argument which will be passed to the `mongo` executable. Arguments to the script can be passed on the command line, and will be available as the `args` array within the script. Remember that strings must be appropriately quoted.

```
$ ./example.js 42 "\"Hello, World\!\""
[ 42, "Hello, World!" ]
```

NB: Remember to make the script executable using `chmod +x example.js`.

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)