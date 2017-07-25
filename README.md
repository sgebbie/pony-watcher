# Pony Watch Scripts

These simple scripts can be used to watch for changes to `.pony` files and
trigger builds and runs of the Pony programs.

# Basic Usage

_Terminal A:_
```bash
cd path/to/pony/code
./path/to/pony-watcher/bin/wpony
```

_Terminal B:_
```bash
cd path/to/pony/code
./path/to/pony-watcher/bin/wprog
```

_Terminal C:_
```bash
cd path/to/pony/code
cat <<-EOF
	actor Main
		new create(env: Env) =>
			env.out.print("Hello World!")
EOF
```

This will result in the "hello world" Pony program being build and executed.
