# Ownership and dependencies

Original project code is licensed under **GPL-2.0-only** in [LICENSE](LICENSE),
as chosen by Xiangqin Chen. This is the kernel's GPL version choice; this project
does not adopt the Linux syscall exception or imply affiliation with Linux.
See the [Linux licensing documentation](https://docs.kernel.org/process/license-rules.html).

Slay the Spire 2, its assemblies, game rules implementation, artwork, localization,
and other assets remain the property of their respective rights holders. They are
not licensed by this repository and are not part of its source distribution.
The importer reads an installation supplied by the user; it does not download the
game. This project is independent research and is not endorsed by Mega Crit.

The headless host references locally supplied game assemblies, including GodotSharp,
Harmony, MonoMod, SmartFormat, Sentry, Steamworks.NET, JetBrains.Annotations and
System.IO.Hashing. Their own license notices govern them. Building against those
files does not make them GPL project code. The release source archive excludes all
DLLs, PCKs and compiled mod distributions. Review the upstream notices and applicable
distribution terms before distributing any separately built binary bundle.

This repository holds the mod and the headless host it needs to generate the vocabulary on your machine. The
training code, evaluation records and the paper are in the companion repository
[HalfVulpes/sts2ai](https://github.com/HalfVulpes/sts2ai).

The trained policies and the in-game mod package are published as GitHub release assets under the project's
GPL-2.0-only licence. They contain learned weights and our own compiled code only: no game assets and no
vocabulary.
