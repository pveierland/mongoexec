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

The `--quiet` represents an optional argument which will be passed to the `mongo` executable. Positional arguments to the script can be passed on the command line, and will be available as the `args` array within the script. Keyword arguments to the script can also be passed on the command line and will be available as the given variable name within the script. Values will fall back to be parsed as strings, such that unquoted values can be used on the command line.

```
$ ./example.js 42 hi "Hello, World!" mykey=myvalue
[ 42, "hi", "Hello, World!" ]
"myvalue"
```

NB: Remember to make the script executable using `chmod +x example.js`.

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)