Simple yet elegant GNOME Terminal color theme based on the [Alabaster](https://github.com/tonsky/vscode-theme-alabaster) color palette.

## Getting started

### Requirements

The installation script requires [`dconf`][dconf] and `uuidgen` ([`util-linux`][util-linux]) to be available on your _PATH_ to create a new profile and generate a random profile UUID.

Some distributions may require additional package(s):

- `dconf-tools` - transitional package for `dconf-cli` and `dconf-editor` ([Debian][debian-dconf-tools], [Mint][mint-dconf-tools], [Ubuntu][ubuntu-dconf-tools])
- `dconf-gsettings-backend` to ensure _GSettings_ compatibility ([Debian][debian-dconf-gsettings-backend], [Mint][mint-dconf-gsettings-backend], [Ubuntu][ubuntu-dconf-gsettings-backend])
- `dconf-cli` to ensure full CLI support ([Debian][debian-dconf-cli], [Mint][mint-dconf-cli], [Ubuntu][ubuntu-dconf-cli])
- `dconf-service` to ensure D-Bus support for the _GSettings_ backend ([Debian][debian-dconf-service], [Mint][mint-dconf-service], [Ubuntu][ubuntu-dconf-service])
- `uuid-runtime` to provide runtime components for the Universally Unique ID library ([Debian][debian-uuid-runtime], [Mint][mint-uuid-runtime], [Ubuntu][ubuntu-uuid-runtime])

The packages should be available for all distributions using the GNOME Terminal by default.

### Installation

1. Clone this repository
   ```sh
   git clone https://github.com/findrakecil/alabaster-gnome-terminal.git

   cd alabsater-gnome-terminal
   ```
2. Run the `install.sh` shell script to start the automated installation with one of following command.

```sh
# try this
./install.sh

# or
bash ./install.sh

# or
sh ./install.sh
```

A list of available options can be shown with `-h`, `--help`.

```sh
./install.sh --help
```

**Usage**: `install.sh [OPTIONS]`

- `-h`, `--help` - Shows the help
- `-l`, `--loglevel <LOG_LEVEL>`, `--loglevel=<LOG_LEVEL>` - Set the log level
  - `0` _ERROR_
  - `1` _WARNING_
  - `2` _SUCCESS_ (default)
  - `3` _INFO_
  - `4` _DEBUG_
- `-p`, `--profile <PROFILE_NAME>`, `--profile=<PROFILE_NAME>` - The name of the profile to install the theme to. If not specified a new profile as clone of the _default_ profile will be created.

### Profile Handling

The script detects available profiles and

- **clones the default profile if no specific profile has been specified** - this ensures that no custom profile colors are overriden
- **allows to install the theme for a specific profile** - the name of the profile the theme should be installed to can be passed using the `-p`/`--profile` option
- **handles already existing Alabaster profiles via version comparison** - if the _Alabaster_ profile already exists and the script version is less than the installed version a confirmation is shown whether to override the theme of abort the installation, otherwise the profile will be
  - **updated** if the script version is **greater than** the installed version
  - **reinstalled** if the installed version is **equal to** the script version

### Log Level

The script provides a `-l`/`--loglevel` option to allow to define the log level. Available levels are

- `0` _ERROR_ - The script will run in _silent mode_, only error messages are shown
- `1` _WARNING_ - Shows _warning_ messages
- `2` _SUCCESS_ (default) - Shows _success_ messages
- `3` _INFO_ - Shows additional _information_ messages
- `4` _DEBUG_ - Runs the script in _debug mode_ showing additional debug messages

## Activation

> This tutorial is using GNOME 43. Other version may have different steps.

### Set as default profile

1. Open the _Preferences_
2. Switch to the _Profiles_ tab
3. Select `Alabaster` from the Profile list and choose _Make default_ on drop-down menu.

## Credits

[Nord theme GNOME Terminal](https://github.com/nordtheme/gnome-terminal) for installation scripts and documentation.
