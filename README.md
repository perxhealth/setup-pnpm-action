![Perx Health](https://user-images.githubusercontent.com/4101096/163123610-9dfa9263-1518-4f5d-8839-9ddc142a513e.png)

# Node/PNPM Setup Action

This repository contains an opinionated **GitHub Action** allowing you to simultaneously
setup a specific version of node with a specific version of pnpm, while also
setting up a keyed dependency cache.

## Usage

Add the following `step` to a GitHub Actions workflow.

```yaml
- name: Setup pnpm and node
  uses: perxhealth/setup-pnpm-action@v1
  with:
    node-version: 16.15.0
    pnpm-version: 8.1.0
```

### Inputs

The Action currently expects two required inputs, and a single optional input

1. `node-version`

   the Nodejs version you wish to install, such as `16.15.0`, `20.2.0`, etc.

2. `to`

   the pnpm version you wish to install, such as `7.33.0`, `8.6.2`, etc.

3. `install-deps` (optional)

   defaults to `false`, this input allows you to automatically run `pnpm install`
   when set to `true`, otherwise you'll need a separate action to do so
   yourself.

### Outputs

The Action does not currently produce any outputs.

## Development

This is a composite action, so development is limited to and contained with
`action.yaml`. Tweak it to your needs and open a pull request.

### Clone the repository

```bash
$ git clone git@github.com:perxhealth/setup-pnpm-action
$ cd setup-pnpm-action
```

### Testing

On pushes to any branch, a workflow will run which performs a smoke test on
the action. Once you've made any changes, ensure the workflow located at
`.github/workflows/preflight.yaml` continues to pass.
