# Pony Watcher Scripts

These simple scripts can be used to watch for changes to `.pony` files and
trigger builds and runs of the Pony programs.

# Basic Usage

__Terminal A:__
```bash
cd path/to/pony/code
./path/to/pony-watcher/bin/wpony
```

__Terminal B:__
```bash
cd path/to/pony/code
./path/to/pony-watcher/bin/wprog
```

__Terminal C:__
```bash
cd path/to/pony/code
cat <<-EOF
	actor Main
		new create(env: Env) =>
			env.out.print("Hello World!")
EOF
```

This will result in the "hello world" Pony program being build and executed.

## Configuration

### Paths

In order to add paths that are watched for `.pony` files they can either be
added to the command line:

```bash
cd path/to/pony/code
./path/to/pony-watcher/bin/wprog my/extra/path my/other/extra/path
```

Or, a `wpony.paths` script can be extended with path lines:
```
...
LIST+=/my/extra/path
LIST+=./my/other/extra/path
...
```

### Optimisation

`ponyc` optimisation can take a while to complete and is not always necessary
during the iterative development cycle. So, it can be useful to have the
optimisation turned off, simply include `-d` or `--no-optimise`:

```bash
cd path/to/pony/code
./path/to/pony-watcher/bin/wpony -d
```
