---
layout: post
title: "Recipe for Debian Haskell packaging"
date: 2013-03-21 06:12
comments: true
categories:
- debian
- haskell
---
The following is what I usually do when I want to debianize a Haskell stuff from Hackage.  This is a personal recipe, by no means official procedure or such.  I may be wrong, badly at that.

<!--more-->

1. Check [pkg-haskell repository](http://anonscm.debian.org/darcs/pkg-haskell/) whether your intended package already exists or not.  Somebody might work on it already.

2. Find the webpage of your intended package at [HackageDB](http://hackage.haskell.org/packages/archive/pkg-list.html), then download "Cabal source package".  Untar it.  The tarball filename should be changed to fit the Debian source package convention.  For example, if the original name is something like foobar-1.0.tar.gz, then it should be haskell-foobar_1.0.orig.tar.gz.

3. File ITP.  [reportbug](http://wiki.debian.org/reportbug) is your friend.

4. Run [cabal-debian](http://packages.debian.org/source/sid/cabal-debian) in untared dir: 

        $ cabal-debian --debianize --quilt

    We do have the upstream tarball, so use --quilt.  See [http://wiki.debian.org/UsingQuilt](http://wiki.debian.org/UsingQuilt).  It might give you warnings about changelog.  debian/changelog doesn't exist yet, so ignore it.

5. Now read 

    [http://wiki.debian.org/Haskell/CollabMaint/Processes](http://wiki.debian.org/Haskell/CollabMaint/Processes)

    and

    [http://wiki.debian.org/Haskell/CollabMaint/PackageTemplate](http://wiki.debian.org/Haskell/CollabMaint/PackageTemplate)

    carefully.  Then do things as they say.  These two are short, but well-written instructions.

    Edit the generated debian/control appropriately.  Do not forget to make your debian/copyright machine-friendly.  See [http://www.debian.org/doc/packaging-manuals/copyright-format/1.0/](http://www.debian.org/doc/packaging-manuals/copyright-format/1.0/).

6. Test whether your package is flawless and really buildable.  Do [lintian](http://lintian.debian.org/).  Use pbuilder.

        $ lintian haskell-foobar_1.0-1_amd64.changes

        # pbuilder --build haskell-foobar_1.0-1.dsc

7. Read [http://wiki.debian.org/Haskell/CollabMaint/DarcsBasic](http://wiki.debian.org/Haskell/CollabMaint/DarcsBasic).

    Darcs is quite easy to use, and you don't have to be the master of Darcs to merely debianize things anyway.  Basically, what I usually do is

        $ darcs record -a; darcs push --repo=debian
	
    Darcs is well-suited to Haskell-related development, but seems you can use Git, too.

8. Change debian/changelog.  "UNRELEASED" in the first line should be "unstable" or "experimental".  Do not forget to close ITP.

9. Finally, do

        $ debuild -tc; debcommit -r; debrelease; darcs push --repo=debian

    That's all folks!