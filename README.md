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
