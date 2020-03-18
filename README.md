# Flatpak Builder Action

This action builds a Flatpak bundle of your app

## Inputs

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

## Example usage

```yml
uses: nahuelwexd/flatpak-builder-action@0.1
with:
  manifest-path: build-aux/org.example.MyApp.json
  meson-args: -Dprofile=development
  flatpak-module: myapp
  app-id: org.example.MyApp.Devel
  runtime-repo: https://flathub.org/repo/flathub.flatpakrepo
  bundle: org.example.MyApp.Devel.flatpak
```
