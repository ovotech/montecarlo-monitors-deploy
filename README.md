# montecarlo-monitors-deploy

This action provides the following functionality for GitHub Actions users:
- Connect to Monte Carlo
- Performs a dry run of monitors on feature branches
- Deploys monitors when merged to main branch


## Basic usage

```
steps:
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
