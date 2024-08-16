# vitest-monorepo-bug

## Steps to reproduce

### Install

- Run `npm install` from the root directory
- Run `npm install` from the `project` directory

### Run

Run `npm run test` from the root directory. This will fail with an error message saying `Error: No test suite found in file /workspaces/vitest-monorepo-bug/project/src/index.test.ts`.

Now run `npm run test` from the `project` directory. This time, vitest will find the test suite and run it successfully.

## Expected behaviour / Things I noticed

I expected vitest to find the test suite, regardless of the directory from which the tests are ran.

This may have something to do with the seperate installations of vitest (one in the root directory and one in the `project` directory).

It seems to work fine when project is referenced as a workspace in the root `package.json`.
