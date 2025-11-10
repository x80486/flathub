# Toolbox App

[Toolbox App][uri-jetbrains-toolbox-home] is an application that provides an
entry point for downloading, updating, and configuring IntelliJ-based IDEs,
local and remote projects, and managing providers.

[uri-jetbrains-toolbox-home]: https://www.jetbrains.com/toolbox-app/ "Manage Your Tools With Ease"

## Local Development — Build and Install Flatpak

Install `flatpak`, `flatpak-builder` and `git`, then run:

```shell
# Ensure Flathub remote exists for the current user
$ flatpak remote-add --if-not-exists --user flathub https://flathub.org/repo/flathub.flatpakrepo

$ git clone https://github.com/flathub/com.jetbrains.toolbox.git
$ cd com.jetbrains.toolbox/

$ flatpak-builder build --force-clean --install-deps-from=flathub --install --user com.jetbrains.toolbox.yaml
```

To uninstall:

```shell
$ flatpak uninstall --delete-data --user com.jetbrains.toolbox
```

To clean up build artifacts and Flatpak state:

```shell
$ rm --force --recursive .flatpak-builder/ build/
$ flatpak uninstall --unused --user
$ flatpak remote-delete --user flathub
```
