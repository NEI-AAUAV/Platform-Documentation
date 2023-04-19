
# Node Packages Management


It is important to keep the number of node packages as few as possible, so that we can avoid unnecessary dependencies. If there is one that makes the job easier or that is foreseeable to be used much more in the future, then it is recommended.

Currently, `yarn` is being used as the package manager for JavaScript, since it improves the speed and reliability of package installations compared to `npm`.

The command `yarn install` creates a `yarn.lock` file, which is used to ensure that the same versions of dependencies are installed across all machines. Thus it is important to commit this file to the repository.

New packages should be added using `yarn add <package-name>`, and if the package is only used in development, then it is added using `yarn add -D <package-name>`.


In this package.json file:

- The `dependencies` section includes react, react-dom, and react-scripts as dependencies.
- The `scripts` section includes scripts for starting the development server, building the app, running tests, and ejecting the app from Create React App.
- The `eslintConfig` section specifies the configuration for ESLint, including extending the default configuration used by Create React App.
- The `browserslist` section specifies the target browsers for the app, both in production and development modes.


### devDependencies

devDependencies are packages that are only used in development, and are not necessary in production. They are usually used for testing, linting, etc.

To run them, you need to use yarn:

```bash
yarn <package-name>
```
Or use the binary directly from `node_modules/.bin`:
```bash
./node_modules/.bin/<package-name>
```

#### source-map-explorer

This is a tool that analyzes JavaScript bundles using the source maps. It can be used to understand where code bloat is coming from and to optimize the size of the bundles.
**NOTE:** It does not analyze or visualize CSS or other types of assets, like `tailwindcss` or `daisyUI`.

The commands below will generate a report in `sme-result.html` of the `build` folder with `source-map-explorer`, which can be opened in the browser.

```bash
yarn build
yarn analyze
```

<!-- 
This error message indicates that there is an invalid version range specified in the package.json file of the react-typist package.

In this case, the version range "^0.14 || ^15.0 || ^16.0" is not a valid semver range. The || operator means "or", and the version range is trying to specify that the package is compatible with either version 0.14.x or versions 15.x.x or versions 16.x.x.
 -->



## Node Dependecies

Since it is important to have as few node packages as possible, we should justifiy the use of each one of them.

Sometimes

### @emotion/react


### @nextui-org/react

Only used for *Rally Tascas - Break The Bars*. It was an experiment, and it should be removed in the future.

### autoprefixer, postcss

`PostCSS` is a tool for transforming CSS with JavaScript. It is a popular package in the Node.js ecosystem and is used by many front-end developers to preprocess and transform their CSS before it's sent to the browser.

It works with plugins, like `autoprefixer`, which ensures maximum compatibility with older browsers by adding automatically vendor prefixes in CSS rules (`-webkit`, `-moz`, `-ms`, etc).

Not sure if they are well configured, or if they are even being used, since it may need `Webpack`, `Gulp` or `Parcel`.

### axios

This package is used to make HTTP requests to the backend. It is a simpler alternative to the native `fetch` API, with much more built-in advantages, being the biggest one the ability to intercept requests. This is useful for refreshing the access token when it expires, for example.

### classnames

This package is used to conditionally join CSS classes together. Useful for avoiding the use of binary or ternary operators in JSX, that make the code harder to read and may lead to bugs, like forgetting to add a space between classes, or adding *undefined* or *false* as classes.

### d3


### daisyui

This package is used to style the website. It is a CSS framework that is based on `Tailwind CSS` that speeds up the development of pages with premade CSS classes that offer a more modern look and feel.

### flowbite-datepicker

A beautiful datepicker that was customized to fit the design of the website. Much better than the default from HTML, and saves the burden of having to implement something alike from scratch.

### framer-motion


### html-react-parser

This package is used to parse HTML strings into React components safely. Not sure if it is necessary, but it was used in the past, and it is still used in some places.

### lodash


### popmotion


### react-countdown

Only used in *Rally Tascas - Break The Bars*. 

### react-hook-form

This is a React hook library for forms. It is used to validate and submit forms, and to manage the state of the form. It is much simpler and easier to use than other popular libraries like `Formik`, which require secondary libraries, like `Yup`, to include form validation features. Besides, it is the most lightweight package and has the best performance.

### react-particles, tsparticles

This is only used in the homepage right now to create the floating particles, but it could be used in other places as well.

### tailwindcss

Well, this is obviously the main CSS framework used in this project.

### typeit-react

This is a React component that allows you to create a typing effect in a text. Currently, it is used almost in every page. It was a replacement for the `react-typist` package, which was not being maintained anymore.

### zustand

This is a state management library for React that offers a simple API and uses the React Hooks API, making it easier and faster to use than other popular state management libraries like `Redux`. `Zustand` is also lightweight and has good performance thanks to its use of the React Context API and memoization.

A state management library is a must for any React application, since it allows you to manage the state of your application in a centralized place, and to avoid passing props down the component tree. This makes the code easier to read and maintain.


## Dependabot security updates

Dependabot security update feature automates the process of checking for and updating your project's dependencies to the latest, most secure versions. When Dependabot detects a security vulnerability in one of your project's dependencies, it creates a pull request to update the vulnerable dependency to a patched version. You can review and merge the pull request to automatically update the dependency and resolve the security vulnerability.


```bash
yarn audit
```

```bash

yarn audit / dependabot
yarn list --pattern svgo
yarn why
yarn upgrade-interactive
```

As mentioned above, do not use `npm` for listing packages. While `npm ls` may seem equivalent to `yarn list`, it does not take into account the `yarn.lock`.


![Dependabot Update Attempt](/docs/assets/images/package-management/dependabot-update-error.png)

This error message indicates that `nth-check`, a dependency of `react-scripts`, could not be updated to the version **2.0.1** (where the patch that fixed the vulnerability was made) since it was not compatible with the range version required by `react-scripts`. It shows how dependabot is useful to automatically updated vulnerable package versions whenever possible.
