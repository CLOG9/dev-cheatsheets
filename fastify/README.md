# fastify

### setup a fastify project with typescript, nodemon

## setup

make a new dir in your projects dir

```bash
mkdir fastify-template
cd fastify-template
```

then run

```bash
pnpm init
pnpm install fastify typescript ts-node @types/node nodemon --save-dev
```

then configure typescript

```bash
npx tsc --init
```

you'll get a `tsconfig.json` file in your root dir, you have to edit it:

- update target to `es2017`
- set `outDir:"./build"`

create a `src dir` in your root dir with an `index.ts` file.

write the setup code for fastify by following the official fastify docs.

now lets configure nodemon.
create a `nodemon.json` file in your root dir and add this to it:

```json
{
  "execMap": {
    "ts": "ts-node"
  }
}
```

now in your package.json add this to your scripts:

```json
"scripts": {
    "build": "tsc -p tsconfig.json",
    "start": "node index.js",
    "dev": "nodemon --watch src src/index.ts",
  },
```

i use a .gitignore extension to setup a file with node files.
make a repo on github and set it up now.

now you can start your server by running:

```bash
pnpm dev
```
