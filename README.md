> [!IMPORTANT]
> I have [resigned as a Cygwin maintainer](https://cygwin.com/pipermail/cygwin-apps/2026-September/045173.html). I am therefore archiving this repository and GitHub organisation.
>
> If you're interested in maintaining this package for Cygwin, check out [Cygwin's information for package maintainers](https://cygwin.com/packages.html) for how to get started.
>
> If you're interested in using the GitHub cygporter organisation as a whole, I'd be happy to hand over responsibility to anyone with a reasonable link to the Cygwin project. Please [get in touch](https://dinwoodie.org)!

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
