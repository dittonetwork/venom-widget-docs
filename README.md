# Ditto Venom Widget

<img src="https://i.imgur.com/g846Eq5.png" alt="Ditto" width="600">

## Table of Contents

- [Widget installation](#widget-installation)
- [Getting started](#getting-started)
- [Top-level architecture](#top-level-architecture)
    - [Architectural approach](#architectural-approach)
    - [Development stack](#development-stack)
- [Contributing](#contributing)
- [License](#license)

## Widget installation

To put widget at your website, simply create iframe or similar object that can display other websites inside:

```html

<iframe src="https://venom-widget-beta.dittonetwork.io/"
        width="450" height="550" frameborder="0"
        allowfullscreen sandbox
>
    Sorry, your browser does not support iframes
</iframe>
```

Widget recommended sizes:

- `width — from 320px to 540px`
- `height — from 530px to 600px`

_Other sizes are also supported, but the widget will display best at the specified sizes._

If you want to change widget theme, simply add query parameter into URL _(default theme is `light`)_:

```html

<iframe src="https://venom-widget-beta.dittonetwork.io/?theme=dark"
        width="450" height="550" frameborder="0"
        allowfullscreen sandbox
>
    Sorry, your browser does not support iframes
</iframe>
```

Supported themes: `light`, `dark`.

## Getting started

First, download repository:

```bash
git clone https://github.com/dittonetwork/ditto-front/
```

Then switch to a branch that meets your needs:

```bash
git checkout <branch_name> # Main is default branch
```

Branches list:

- `dev` - Development branch (nightly builds)
- `stage` - Pre-releases testing branch (pre-release builds)
- `main` - Releases

Install dependencies:

```bash
npm install
```

Download submodules:

```bash
git submodule update --remote # Ensure that you have access to all submodule repos
```

Run development server:

```bash
npm run serve # http://localhost:8080
```

## Top-level architecture

### Architectural approach

[Future Sliced Design](https://feature-sliced.design/docs/get-started/overview)

Project structure:

1. `shared` - reused code that is not application/business specific (e.g. UIKit, libs, APIs)
2. `entities` - business entities (e.g. User, Product, Order)
3. `features` - user interactions, actions that have business value for the user (e.g. SendComment, AddToCart,
   UsersSearch)
4. `widgets` - a composite layer for connecting entities and features into independent blocks (e.g. IssuesList,
   UserProfile).
5. `pages` - a compositional layer for assembling complete pages from entities, features, and widgets.
6. `processes` - complex scripts covering several pages (e.g. authorization)
7. `app` - settings, styles and providers for the whole application

### Development stack:

- Application: `React.js ^18.2` + `TypeScript ^4.8`
- Styles: `SASS` / `SCSS`
- HTML: `Plain HTML`
- State management: `MobX ^6.6 (decorators)`
- Bundler: `Webpack ^5.74`

## Contributing

Please refer to project's code style for submitting patches and additions.

1. Fork the repo on GitHub
2. Clone the project to your own machine.
3. If you're fixing bug or adding a new feature, create related issue.
4. Commit changes to your own branch.
5. Push your work back up to your fork.
6. Submit a Pull request so that we can review your changes.

NOTE: Be sure to merge the latest from "upstream" before making a pull request!

## License

You can copy and paste the MIT license summary from below.

```
MIT License

Copyright (c) 2023 Ditto Network

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```
