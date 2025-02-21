![Github Actions Build Status](https://github.com/jhipster/prettier-java/actions/workflows/github-ci.yml/badge.svg?branch=main)

# Prettier Java

![Prettier Java Banner](./logo/prettier-java-wide-dark.svg#gh-dark-mode-only)
![Prettier Java Banner](./logo/prettier-java-wide-light.svg#gh-light-mode-only)

## Intro

Prettier is an opinionated code formatter. It enforces a consistent style by parsing your code and re-printing it with its own rules that take the maximum line length into account, wrapping code when necessary.

## How it works

A Prettier plugin must first parse the source code of the target language
into a traversable data structure (Usually an **A**bstract **S**yntax **T**ree)
and then print out that data structure in a "pretty" style.

Prettier-Java uses a [Java-Parser](./packages/java-parser) implemented in JavaScript using the
[Chevrotain Parser Building Toolkit for JavaScript](https://github.com/SAP/chevrotain).
What this means is that unlike many other Prettier plugins,
`prettier-java` has **no additional runtime pre-requisites** (e.g: Python executable).
It could even be used inside a browser.

## Subpackages

This project contains 2 packages:

- [prettier-plugin-java](./packages/prettier-plugin-java) A plugin for
  [Prettier](https://prettier.io/) to format Java code

  [![npm-prettier-plugin-java][npm-prettier-plugin-java-image]][npm-prettier-plugin-java-url]

* [java-parser](./packages/java-parser) A Java Parser using [Chevrotain](https://github.com/SAP/chevrotain) which output a **C**oncrete **S**yntax **T**ree

  [![npm-java-parser][npm-java-parser-image]][npm-java-parser-url]

[npm-prettier-plugin-java-image]: https://img.shields.io/npm/v/prettier-plugin-java.svg?color=blue&label=prettier-plugin-java&logo=prettier-plugin-java
[npm-prettier-plugin-java-url]: https://www.npmjs.com/package/prettier-plugin-java
[npm-java-parser-image]: https://img.shields.io/npm/v/java-parser.svg?color=blue&label=java-parser&logo=java-parser
[npm-java-parser-url]: https://www.npmjs.com/package/java-parser

## Install

### Pre-requirements

- [Node version](https://nodejs.org/en/download/releases/) 10+
- [Prettier](https://github.com/prettier/prettier)

### Install Prettier and Prettier-Java plugin

```bash
# Local installation
npm install prettier-plugin-java --save-dev

# Or globally
npm install -g prettier prettier-plugin-java
```

or with yarn:

```bash
# Local installation
yarn add prettier-plugin-java --dev

# Or globally
yarn global add prettier prettier-plugin-java
```

Note: If you want to install the prettier-plugin-java globally, you should also install the prettier package globally.

## Usage

To reformat all your Java files, run:

```bash
# If you have installed the package locally
npx prettier --write "**/*.java"

# Or globally
prettier --write "**/*.java"
```

To see an advanced usage: please go to the [Advanced Usage](./docs/advanced_usage.md) section

## Maven plugin

A neat maven plugin for prettier-java was made by developers from HubSpot. \
Add it to the `plugins` section of your `build` configuration

```xml
<build>
  <plugins>
    <plugin>
      <groupId>com.hubspot.maven.plugins</groupId>
        <artifactId>prettier-maven-plugin</artifactId>
        <!-- Find the latest version at https://github.com/jhipster/prettier-java/releases -->
        <version>0.8</version>
    </plugin>
  </plugins>
</build>
```

If you would like to use this plugin, we recommend you to check their [project](https://github.com/HubSpot/prettier-maven-plugin) as is it well documented.

## Organize imports

Prettier-java is currently sorting imports according to the [Google Java Style guide](https://google.github.io/styleguide/javaguide.html#s3.3-import-statements).

If you are using an IDE such as IntelliJ, you might want to configure it to match with Prettier-java.

For IntelliJ, you can use this configuration:
![IntelliJ config](./docs/intellij_imports_config.png)

You can also import the Checkstyle configuration provided in the next section.

For VSCode with [Language Support for Java](https://marketplace.visualstudio.com/items?itemName=redhat.java), you can use this configuration (`settings.json`):

```json
{
  "java.completion.importOrder": ["#"]
}
```

## Checkstyle configuration

You can use Prettier in combination with other linter, like Checkstyle.

Here is one [Checkstyle Prettier compatible configuration](./docs/checkstyle/checkstyle.xml) you can use to start with !

You can directly import the config into IntelliJ Idea for instance:

![Import Checkstyle configuration](./docs/checkstyle/import-checkstyle-configuration.gif)

## Contributing

Contributions are very welcome.
See the [contribution guide](./CONTRIBUTING.md) to get started.
And the [Help Wanted](https://github.com/jhipster/prettier-java/labels/help%20wanted) issues.

## Credits

Special thanks to [@thorbenvh8](https://github.com/thorbenvh8) for creating the original `prettier-java`
plugin and the associated Java Parser implemented in JavaScript.

We would also like to thank the [Chevrotain](https://github.com/SAP/chevrotain/graphs/contributors) and [Prettier](https://github.com/prettier/prettier/graphs/contributors) contributors which made this possible.
