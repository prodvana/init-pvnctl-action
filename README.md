# init-pvnctl Github Action

This action helps intstall Prodvana's [pvnctl](https://github.com/prodvana/pvnctl) command line utility and initialize authentication so you can use it during CI runs.

# Usage

## Inputs

| Input      | Default    | Description                                                           |
| ---------- | ---------- | --------------------------------------------------------------------- |
| version    | latest     | Version of the `pvnctl` binary to install                             |
| org        | (required) | Your Provdana Org Slug, found in your URL: `<org>.prodvana.io         |
| api_token  | (required) | Prodvana API Token. You can create one with `pvnctl api-token create` |

## Basic Usage

```yaml
steps:
  - uses: prodvana/init-pvnctl@v0.1.0 
    with:
      org: my-org # you can find this in your Prodvana URL: <org>.provana.io 
      api_token: ${{ secrets.YOUR_PRODVANA_API_TOKEN }} # create with `pvnctl api-tokens create`
  - run: pvnctl applications list 

```
