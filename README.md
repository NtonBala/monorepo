# Monorepo

Simple monorepo practice that relates to [Monorepos - A Beginner's Guide](https://www.udemy.com/course/monorepos-a-beginners-guide) Udemy course by [Robert Donnelly](https://www.udemy.com/user/robert-donnelly-6).

Projects (which can be either app or library) are located in `packages` folder. To launch a project run `node packages/${projectName}`.

There're next projects:

1. module-a
1. module-b

Initially both modules are not set to be standalone packages, though we can require module-b from module-a via `require('../module-b')` and run `node packages/module-a`. It will work and console output will be:

```
I am module-a
I am module-b
```

But we can not require modules as standalone packages via `require('module-b')`. If we try to do so, we'll get an error: `Cannot find module 'module-b'`.

## Require Project as Standalone Package

There are several ways to require a project as a standalone package, but all of them take advantage of _Node Modules Resolution Strategy_.

### Node Modules Trick

If we rename `packages` folder to `node_modules`, Node we'll be able to find a project by name. So code `require('module-b')` will work.

In this case we don't have the prettiest directory structure but it's the simplest way to set up mono repository.
