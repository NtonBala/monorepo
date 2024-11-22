# Monorepo

Simple monorepo practice that relates to [Monorepos - A Beginner's Guide](https://www.udemy.com/course/monorepos-a-beginners-guide) Udemy course by [Robert Donnelly](https://www.udemy.com/user/robert-donnelly-6).

Project uses [Yarn](https://classic.yarnpkg.com) as package manager.

Projects (which can be either app or library) are located in `packages` folder:

1. module-a
1. module-b

Monorepo is set via _workspaces_.

Run `yarn install` from the root directory to automatically create the symlinks.  
Then run `node packages/module-a` to start the project.

`module-a` requires `module-b` so when starting the project console should output:

> I am module-a  
> I am module-b

**Other dependencies**

Project uses [lodash](https://github.com/lodash/lodash) that is prevented from hoisting.

**Bin Scripts**

`module-b` file is defined as a _bin script_ and set as `"start"` script in root `package.json`. So to run `module-b` locally run `yarn start` at the root.
