# mkrdns

An automatic reverse DNS zone generator.

This is a fork of [oasys/mkrdns](https://github.com/oasys/mkrdns) who originally forked this from [mkrdns](https://sites.google.com/a/kluge.net/mkrdns/).
Description from the original site:

> Have you ever gotten tired of having to change both the forward and
> reverse zone maps when adding, removing, or changing hosts in DNS? If
> so, then mkrdns is for you! mkrdns automates the tedious procedure of
> editing both forward and reverse zones when making changes to your
> zones with likely no changes to your current configuration file.
>
> mkrdns does this by reading through all of the primary/secondary
> (master/slave) zones in your configuration file (either named.boot
> or named.conf). It will then automatically generate the reverse
> zone entries (IN PTR) for the networks for which you are the
> primary/master. It is now possible to simply edit the forward map,
> run mkrdns, and reload the zone. Clean, simple, and best of all,
> automatic.
>
> mkrdns also acts as a limited lint-like program, issuing warnings and
> errors if there are problems with your configuration or zone files.

Full documentation available via `perldoc mkrdns`.

## Added features/bug fixes

- Fixed directory bug (original script failed if options like "managed-keys-directory" were set)
- Fixed bug that caused first $ORIGIN to be deleted if before SOA (possibly required for SOA)
- Fixed bug that caused a double dot insertion onto the FQDN if $ORIGIN is just "." 

## Added features by Jason Lavoie

- full support for `$GENERATE` directive
- IPv6 support
- bind view support
- various bugfixes

## Credits

Thanks to Theo Van Dinter (felicity@mkrdns.org) for original script.
Thanks also to Jason Lavoie (https://github.com/oasys) and  Dan Pritts (https://github.com/danpritts) for their enhancements and fixes.

## License

GNU GPL
