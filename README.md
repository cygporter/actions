# cygporter workflows

This repository contains [custom actions][] to help creating builds of Cygwin
packages using [cygport][].

## Usage

For all these actions, set them up as individual steps within your GitHub
Actions jobs.

### vars

This action extracts variables from the Cygport file using `cygport <file>
vars` and makes them available as outputs.

```yaml
uses: cygporter/actions/vars@main
with:
  # Required: Path to the cygport file that you're using.
  cygport_file: <path>

  # Required: String with a single variable to extract, or a list of variables.
  vars: <variable> [<variable> ...]

  # Optional: Path to Cygwin's binaries.  This must be present if the Cygwin
  # binaries are not in the default for the cygwin/cygwin-install-action
  # install location of C:\cygwin\bin\.  Due to limitations of the GitHub
  # workflows, this path cannot contain spaces.
  cygwin_bin_path: <path>
```

[custom actions]: https://docs.github.com/en/actions/creating-actions/about-custom-actions
[cygport]: https://cygwin.github.io/cygport/
