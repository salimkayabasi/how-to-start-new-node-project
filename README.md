# How To Start New Nodejs Project

Here, I want to create a check list that you need to follow before saying `This project is 
production ready`

- [ ] Prefer to use latest LTS version of `Nodejs` [v6.11.2][nodejs]
- [ ] Work with `Yarn` instead of `npm` [v0.27.5][yarn]
- [ ] Create npm scripts for building your project
- [ ] Always use `.editorconfig` file, more details on [editorconfig.org][editorconfig]
- [ ] Don't forget to add `README.md` file and explain all `npm scripts`
- [ ] Create docker image and its related scripts
- [ ] ES6 is a big feature that you shouldn't miss
- [ ] Linters are so important
- [ ] [Jest][jest] is super easy test suite with zero configuration
- [ ] Keep your dependencies updated 
- [ ] Create a generator for your projects with using [Yeoman][yeoman]
- [ ] Share your knowledge with community 
- [ ] Check the [best practices](https://expressjs.com/en/advanced/best-practice-security.html) 
from Express for Production 

    
### Nodejs Version

Some of Cloud platforms are not supporting latest version of nodejs and using LTS version would 
be more safe on most cases. You will less documentation and support on Stackoverflow if you decide
to use latest version.

### Yarn vs NPM

Current Nodejs comes with `npm@3`, nowadays we've heard that npm is still in race with `npm@5`. 
Regarding the current nodejs version and some comparing article, there is no big reason for 
switching package manager from yarn to `npm@5`. Still we can stay with yarn.

Don't forget to add `.yarnclean` file to your repository.

### Npm Scripts

Try to cover all development and deployment related tasks. Your project will run w/o any IDE on CI.
Any developer should be able to work w/o installing any IDE or text editor.

### Editor Config

Editor Config is kind of alignment feature for all different IDEs. Any developer can decide to 
use their own favorite IDE/TextEditor. All file formatting and syntax rules must be same for all 
developers. But this is an additional feature for formatting, as always please use linters. 

### Readme File

This file basically lists all details about your project. It should explain each steps from 
beginning. Start with explaining project and its purpose then list preconditions/dependencies.
Please create a list for all `npm scripts` and `ENV` variables that you are using in your project.

### Docker

Nowadays, Docker is another requirement. This will help to DevOps for deploying your project to 
production. If you need some docker-only npm scripts, all scripts start with a kind of prefix 
like `docker-build`.

In your project, create a `docker-compose` file if the project needs external services like 
`redis`, `mongodb` etc. This will helps developers to easily run the application w/o any hassle. 
And also these docker related files are kind of documentation for developers which are explaining
the working flow. Using `.dockerignore` file and removing `devDependencies` while creating docker
images will reduce size of your docker image.

Inside the container, please specify the version of Nodejs and Yarn that you will use it.

### Typescript vs Babel

It's hard to say which one is best and there is no only one solution for everything. There are a 
lot parameters to decide it. First of all, most important part is being comfortable on both sides.

TS is more useful if you will refactor your project. Built-in static type checker and interfaces 
are really cool. On the other hand, Babel is super powerful transpiler for latest ES standards.

At least using ES6 is mandatory for your project. Use [babel][babel] or [typescript][typescript] 
to transpile your project.

### Linters

- [Eslint][eslint] for JS projects
- [TSlint][tslint] for Typescript projects

Yet another comparison, ESLint and its plugins are very flexible and working better than TSLint. 
At the same time Typescript comes with its own static type checker which helps you about checking 
arguments and signature of methods. 

TSLint is not so stable/powerful as much as ESLint. ESLint has no type checker and can not detect
signature mistakes. In this case, using [Flow][flow] may help you.

- With ESLint, please follow the [Airbnb][npm-eslint-config-airbnb]'s rules for javascript
- With TSLint, please follow the [Microsoft][npm-tslint-microsoft-contrib]'s rules for ts files

Please check this [list](https://github.com/dustinspecker/awesome-eslint) if your are using ESLint

### Testing

There are a lot of testing tools for nodejs. With [Jest][jest], no need to configure your test 
tool with coverage report. Also you can use Jest for frontend and backend features. Mocking is 
also very important case while creating your test suites. Here, Jest has own utilities for mocking.

### Community

If you are using open source projects, you may contribute the community too. Please feel free to 
write your experience and very useful modules. As you are creating small modules for you/your 
company, maybe some of them could be useful for other people. Don't be shy about sharing them 
with others. 

### Tips

- For production, we may use some `ENV` variables, using [config][npm-config] may help you about
this case. This package is not `universal` and not suitable for universal applications
- [npm-check][npm-npm-check] or [ncu][npm-ncu] will help you about checking all outdated 
dependencies
- [types-checker][npm-types-checker] will detect the `DefinitelyTyped` modules for your TypeScript 
project
- Use [nsp][npm-nsp] for more security on your project


[nodejs]: https://nodejs.org/en/
[yarn]: https://yarnpkg.com/en/
[editorconfig]: http://editorconfig.org/
[eslint]: https://eslint.org/
[tslint]: https://palantir.github.io/tslint/
[babel]: https://babeljs.io/
[typescript]: https://www.typescriptlang.org/
[jest]: https://facebook.github.io/jest/
[flow]: https://flow.org/
[yeoman]: http://yeoman.io/
[npm-config]: https://www.npmjs.com/package/config
[npm-eslint-config-airbnb]: https://www.npmjs.com/package/eslint-config-airbnb
[npm-tslint-microsoft-contrib]: https://www.npmjs.com/package/tslint-microsoft-contrib
[npm-npm-check]: https://www.npmjs.com/package/npm-check
[npm-ncu]: https://www.npmjs.com/package/npm-check-updates
[npm-types-checker]: https://www.npmjs.com/package/types-checker
[npm-nsp]: https://www.npmjs.com/package/nsp
