# glfw-example

To build and run the project, you need to install a c/c++ compiler for your OS and `cmake`.

Start by resolving the dependency for glfw with git:

```bash
git submodule update --init
```

Then build the project with cmake:

```bash
cmake -S . -B ./build
cmake --build ./build
```

And run the generated executable:

```bash
./build/glfw-example
```
