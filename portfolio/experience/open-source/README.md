# Open-source

I am a firm believer in the benefits of open-source software, and am proud to be a member of the open-source community. While I mostly develop my own projects, I have made numerous contributions to other open-source projects, from improving documentation, fixing bugs and adding features.

## NixOS Hardware ([CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/))

[NixOS hardware](https://github.com/NixOS/nixos-hardware) is a collection of hardware configurations for various devices. Applying these kinds of patches on other Linux systems requires lots of niche knowledge of device-specific software and driver requirements. I [contributed](https://github.com/NixOS/nixos-hardware/pull/1761) settings to configure and enable the fingerprint sensor for the Dell XPS 15 9500, meaning all users of this device will gain the ability to use the device's fingerprint sensor with no additional configuration required.

## Slackadays/Clipboard ([GPL 3](https://www.gnu.org/licenses/gpl-3.0.en.html))

[`cb` is a "***ridonkuliciously*** smart" clipboard manager](https://github.com/Slackadays/Clipboard) which enables a consistent set of commands for clipboard management across Windows, MacOS and Linux.

* I contributed design advice for a [scripting system](https://github.com/Slackadays/Clipboard/issues/171#issuecomment-2430947544) to improve integration in systems like Linux Wayland.
* I helped to [improve the installation script](https://github.com/Slackadays/Clipboard/pull/124) so that installing the application no-longer requires `sudo` privileges to install on most Linux systems.

## Piccolo ORM ([MIT](https://opensource.org/license/MIT))

[Piccolo](https://piccolo-orm.com/) is a fast, asynchronous and type-safe ORM for Python. I [discovered](https://github.com/piccolo-orm/piccolo/issues/672) and [fixed](https://github.com/piccolo-orm/piccolo/pull/673) untested edge case where a confusing internal error was produced, helping to improve the user-experience of the library.

## Poetry ([MIT](https://opensource.org/license/MIT))

[Poetry](https://python-poetry.org/) is a Python dependency manager and build system, adored for its simplicity and ease-of-use. I encountered a confusing error when incorrect project metadata was supplied in a `pyproject.toml` file. [My fix](https://github.com/python-poetry/poetry-core/pull/827) allows Poetry to gracefully handle the error, and report it in a user-friendly manner.

## NVBN/TheF*ck ([MIT](https://opensource.org/license/MIT))

[The F*ck](https://github.com/nvbn/thefuck) is a *"magnificent app that corrects errors in previous console commands"*. It uses your shell's history to analyse errors in your commands so that if you make a mistake, you can simply hurl expletives at your terminal, and it will suggest corrections.

I contributed [a new rule](https://github.com/nvbn/thefuck/pull/1302) for suggesting a `git clone` prefix when a Git URL is pasted into the terminal.

