pijul bootstrap
---------------

This pkgbuild will update your `pijul` with the latest development version straight from [the
nest](nest.pijul.com). However, it needs pijul to pull from there, so it can't be used for first
time installation.

Steps:

1. `pacaur -S pijul` or otherwise get a working pijul installation.
1. `makepkg`
1. `pacman -U ...`

Three times the nest will be down, three other times it will serve you unmerged sources, seventh
time the build will succeed. Have patience & enjoy!
