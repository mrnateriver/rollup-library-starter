# Template for ES/CJS libraries

Basic template for creating libraries using TypeScript and Rollup for bundling.

At its core is Rollup config, which:
 1. Creates two bundles: for CommonJS and ES modules;
 2. Outputs build progress ([rollup-plugin-progress](https://github.com/jkuri/rollup-plugin-progress));
 3. Clears output directory before building ([rollup-plugin-delete](https://github.com/vladshcherbin/rollup-plugin-delete));
 4. Resolves imports from `node_modules` ([@rollup/plugin-node-resolve](https://github.com/rollup/plugins/tree/master/packages/node-resolve));
 5. Transforms CJS modules into ES ones ([@rollup/plugin-commonjs](https://github.com/rollup/plugins/tree/master/packages/commonjs));
 6. And finally, compiles TypeScript ([rollup-plugin-typescript2](https://github.com/ezolenko/rollup-plugin-typescript2)).

 That particular plugin for TypeScript is used due to [this bug](https://github.com/rollup/plugins/issues/418) and [that bug](https://github.com/rollup/plugins/issues/272) in core Rollup plugin.

 TypeScript compilation is configured relatively liberally, and set for `esnext` target.

Apart from basic configuration, this template also includes:
 1. [ESLint](https://github.com/eslint/eslint) setup for linting TS/JS files ([@typescript-eslint/eslint-plugin](https://github.com/typescript-eslint/typescript-eslint));
 2. [Prettier](https://github.com/prettier/prettier) for autoformatting and linting code style (done via ESLint using [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier) and [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier));
 3. `.editorconfig` file with pretty common params (4 spaces for tabs, 120 line length);
 4. Workspace preferences for [Visual Studio Code](https://code.visualstudio.com) matching tooling settings, including extensions recommendations.
