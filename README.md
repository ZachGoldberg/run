## USAGE
```bash
$ ./run hello-world
Hello World
```

where `hello-world` is a function defined inside `run` e.g.

```bash
run_hello_world() {
    echo "Hello World"
}
```

Note that `run` will match at runtime underscores or dashes, you can use either.


## Adding New Functions
Create a new function inside `run` with the prefix `run_` then call the function on the command line without the `run_` prefix.

Functions can of course be composed inside the script, and you can write functions in other files and include them in run via `source` e.g.

`extras.sh`
```bash
run_extra_script() {
    echo "show me what you got"
}
```
`run`:
```bash
...
source extras.sh

run_hello_world() {
...
```

```bash
$ ./run extra-script
show me what you got
```
