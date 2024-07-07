# Architecture

## NPM

### Use locally installed packages with `npx --package=<pkg>`

The Angular documentation [suggests][Angular CLI setup] installing the Angular CLI globally.
> ```console
> npm install -g @angular/cli
> ```
[Angular CLI setup]: https://angular.dev/tools/cli/setup-local

I still think that local packages should be preferred to global packages.
The solution was found in the [StackOverflow answer][StackOverflow answer].

[StackOverflow answer]: https://stackoverflow.com/a/56346181

The NPM ecosystem has been moving more and more towards installing tools as project-local `devDependencies`,
instead of requiring users to install them globally.
This is considered a good practice.
As it allows to use multiple versions (one per project), instead of having one unique global version.

In order to start the project from scratch,
you need to point to the package with `--package` flag (otherwise `npx` will not find it):
```console
npx --package @angular/cli ng new <project-name>
```
The mention of the flag can be shortened:
```console
npx -p @angular/cli ng new <project-name>
```
