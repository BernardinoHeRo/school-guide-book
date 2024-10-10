# School Guide Book

This project is a static website built to serve as a comprehensive guide for students and faculty. It provides information about the turorial, its programs, tips, and resources in an organized and easy-to-navigate format.
This website is built using [Docusaurus](https://docusaurus.io/), a modern static website generator.

### Prerequisites

- Node.js version >= 18.x
- Yarn, npm, or bun installed globally

### Installation

#### Using Yarn

```
yarn
```

#### Using npm

```
npm install
```

#### Using bun

```
bun install
```

### Local Development

#### Using Yarn

```
yarn start
```

#### Using npm

```
npm start
```

#### Using bun

```
bun start
```

> [!NOTE]
> This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

### Build

#### Using Yarn

```
yarn build
```

#### Using npm

```
npm run build
```

#### Using bun

```
bun build
```

> [!NOTE]
> This command generates static content into the `build` directory and can be served using any static contents hosting service.

### Deployment

#### Using SSH:

###### Using Yarn

```
USE_SSH=true yarn deploy
```

###### Using npm

```
USE_SSH=true npm run deploy
```

###### Using bun

```
bun deploy
```

#### Not using SSH:

###### Using Yarn

```
GIT_USER=<Your GitHub username> yarn deploy
```

###### Using npm

```
GIT_USER=<Your GitHub username> USE_SSH=true npm run deploy
```

###### Using bun

```
bun deploy
```

> [!NOTE]
> If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.

### Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bugs.

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
