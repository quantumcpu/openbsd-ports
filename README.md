# OpenBSD Ports for the Tor Browser Bundle (TBB) #

These are the OpenBSD ports that correspond to the Tor browser bundle.
They are a work in progress.  Please beware that until we make release
announcements on [our web site](https://torbsd.github.io) you should
be careful using this stuff.  You must be runing OpenBSD -current and
have your ports and src synced up (like I said: running -current).

## Branches and Versions ##

As of 23 Octover 2015 the `master` branch has release __5.0.3__:

    tor-browser       5.0.3 (based on ff-esr 38.3.0)
    torbutton         1.9.3.4
    tor-launcher      0.2.7.7
    noscript          2.6.9.36
    https-everywhere  5.0.7

The `develop` branch is always used to work on the next release.  We
use tags to mark release points that correspond as closely as possible
to TBB releases.  They are marked "-sans-pt" to indicate that
Pluggable Transports (PT) is not yet a part of this set of ports...
working on it...

## Meta Package ##

There is also a meta/tbb package, but in order to use it it needs at
least `/usr/ports/meta/Makefile.inc` dropped in; assuming you have
copied the `meta` and `www` dirs from this repo to
`/usr/ports/mystuff`:

    # cp /usr/ports/meta/Makefile.inc /usr/ports/mystuff/meta/
    # cd /usr/ports/mystuff/meta/tbb
    # make install

YMMV.  I mainly did that for convenience in testing, but it's morally
no different than the `meta/avr` port.

## Play Along at Home ##

I keep notes in [notes.org](notes.org).  You're welcome to look over
my shoulder but then don't be offended by what I say :-) ...  This
work is sometimes irritating; if I'm going to be transparent then I
have to vent transparently sometimes, as well... Also, we've started
using [the GH issue tracker](https://github.com/torbsd/openbsd-ports/issues)
to enumerate (if not organize) what we're working on.

I generally build and test on amd64 first, i386 second.  Testing on
other architectures greatly appreciated.

## Repositories ##

Most of the ports in this repo pull their source tarballs from other
GH [torbsd repositories](https://github.com/torbsd).  This is because
the Tor project chooses not to make source tarballs easily available
for anything except tor itself (their gitian-based build process does
not require them).  Also, the OpenBSD ports system explicitly supports
pointing at GH projects.  I maintain the tags and branches in these
repositories and track changes in the
[tor project's git repositories](https://gitweb.torproject.org).
Where possible I prefer to have ports pull source from some
authoritative download area maintained by the project itself; in the
case of noscript I do this, for example.

## Beware: Experimental Until Otherwise Stated ##

This is still work in progress.  Until we make an official release
statement you should use this only if you want to help in testing. 

## Contact ##

You can get my attention by posting [issues](https://github.com/torbsd/openbsd-ports/issues) to this repository if you
like, or use one of the contact methods mentioned on my
[home page](http://trac.haqistan.net/~attila).

--attila
