# Flatpak Builder Action

This action builds a Flatpak bundle of your app.

## Usage

You only need to add this to your workflow file:

```yml
uses: nahuelwexd/flatpak-builder-action@<the base you want>
with:
  <insert the inputs here>
```

Where you have to replace `<the base you want>` with either `freedesktop-19-08`
or `gnome-3-36` (kde sdk not yet implemented). Also your project needs to have
the meson build system.

### Inputs

- `manifest-path`  
  This is the path to your application's manifest. It can be YAML or JSON.
- `meson-args`  
  The args passed to meson to configure your app. Typically this is
  `-Dprofile=development`.
- `flatpak-module`  
  The module name for your app. This is used to know which modules are
  dependencies and which are not.
- `app-id`  
  The ID of your application.
- `runtime-repo`  
  The repository that will be used to get the runtimes when the user installs
  the bundle
- `bundle`  
  The file name that the bundle will have

### Example

You can see a working example on this project, [here](.github/workflow/flatpak-test.yml)
