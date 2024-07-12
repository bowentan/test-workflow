.. 
    x-release-please-start-version
Version: v0.7.4
.. 
    x-release-please-end

.. code-block:: yaml

        name: Code linting

        on:
          push:
            branches: ["main"]
          pull_request:
            branches: ["main"]

        jobs:
          glob-linters:
            runs-on: ubuntu-latest
            steps:
              - name: Checkout code
                uses: actions/checkout@v3
                with:
                  fetch-depth: 0
              - name: Linting
                uses: bowentan/glob-linters@v|major|
                env:
                GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

..
    x-release-please-start-major
.. |major| replace:: 0
..
    x-release-please-endJJ init
