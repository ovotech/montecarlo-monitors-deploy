# montecarlo-monitors-deploy

This action provides the following functionality for GitHub Actions users:
- Connect to Monte Carlo
- Performs a dry run of monitors on feature branches
- Deploys monitors when merged to main branch

#### [Monte Carlo Monitors as code docs](https://docs.getmontecarlo.com/docs/monitors-as-code)

## Basic usage

You will first need to generate an API ID and API key, and store these as secrets in your repo.

To use the action as is your main branch will need to be called `main` (this can be overridden), and your YAML monitors
will need to live in a folder called `monitors` (this can be overridden) containing sub-folders by namespace. 

```
steps:
    - uses: actions/checkout@v3
    - uses: actions/setup-python@v4
      with:
        python-version: '3.10'

    - name: Install montecarlo
      shell: bash
      run: pip install -U montecarlodata

    - name: Monte Carlo Monitors Deploy
      uses: actions/montecarlo-monitors-deploy@v1
      with:
        MCD_DEFAULT_API_ID: ${{secrets.MCD_DEFAULT_API_ID}}
        MCD_DEFAULT_API_TOKEN: ${{secrets.MCD_DEFAULT_API_TOKEN}}
```
