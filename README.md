# cypress-workflows
> Reusable Cypress workflows for GitHub Actions

Call these workflows from your GitHub Action workflows, a single line (with parameters) let's you run N parallel test jobs without any configuration.

## Example

Let's split all tests across 3 machines using [Cypress Parallelization](https://on.cypress.io/parallelization)

```yml
name: ci
on: [push]
jobs:
  test:
    uses: bahmutov/cypress-workflows/.github/workflows/parallel.yml@v1
    with:
      n: 3
    secrets:
      recordKey: ${{ secrets.CYPRESS_RECORD_KEY }}
```

Result:

![Workflow](./images/flow.png)

## Workflows

- [standard.yml](./.github/workflows/standard.yml) checks out code, installs dependencies, and runs tests on a single machine
- [parallel.yml](./.github/workflows/parallel.yml) lets you specify the number if test machines to use

The workflows allow passing pretty much all [Cypress GH Action](https://github.com/cypress-io/github-action) parameters, see the individual workflow YML file.

## Versions

Advice: use an explicit [release tag](https://github.com/bahmutov/cypress-workflows/releases) when using a workflow like `parallel.yml@v1.0.1`. You might also use the latest release from the major branch `v1` like `parallel.yml@v1`. Not recommended: using the latest commit on the branch `parallel.yml@main` or using a specific commit `parallel.yml@2a9d460`.

## Examples

- [bahmutov/cypress-workflows-example](https://github.com/bahmutov/cypress-workflows-example)

## Small print

Author: Gleb Bahmutov &lt;gleb.bahmutov@gmail.com&gt; &copy; 2021

- [@bahmutov](https://twitter.com/bahmutov)
- [glebbahmutov.com](https://glebbahmutov.com)
- [blog](https://glebbahmutov.com/blog)
- [videos](https://www.youtube.com/glebbahmutov)
- [presentations](https://slides.com/bahmutov)
- [cypress.tips](https://cypress.tips)

License: MIT - do anything with the code, but don't blame me if it does not work.

Support: if you find any problems with this module, email / tweet /
[open issue](https://github.com/bahmutov/cypress-workflows/issues) on Github

## MIT License

Copyright (c) 2021 Gleb Bahmutov &lt;gleb.bahmutov@gmail.com&gt;

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the "Software"), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.
