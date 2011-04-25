NAME
====
gitwork - a proposal to add working branch management commands to git

DESCRIPTION
===========
This project builds a package that can be used to update an existing git installation with scripts
and man pages that implement the proposed **git work** and **git base** commands.

In this way, people who are not in a position to rebuild their own version of git can still
make use of the proposed commands.

If you are in a position to rebuild your existing git installation, you can simply
fetch and the merge the work branch from git://github.com/jonseymour/git into your copy of git
and then build and install git in the normal way. Otherwise, follow the instructions below:

USAGE
=====
For more details about the commands provided by this package, read:
<ul>
<li><a href="https://jonseymour.s3.amazonaws.com/git-work.html" target="browse">git-work(1)</a></li>
<li><a href="https://jonseymour.s3.amazonaws.com/git-base.html" target="browse">git-base(1)</a></li>
<li><a href="https://jonseymour.s3.amazonaws.com/git-atomic.html" target="browse">git-atomic(1)</a></li>
<li><a href="https://jonseymour.s3.amazonaws.com/git-test.html" target="browse">git-test(1)</a></li>
</ul>


BUILDING
========
To build the package, you must have a working git installation and be able to build git
and its documentation. You do not, however, have to install git as part of this process.

Obtain the source:

       git clone git://github.com/jonseymour/gitwork
       cd gitwork

Make the tarball:

       git clone git://github.com/jonseymour/gitwork
       cd gitwork
       sh ./installer make-tar

This command will use git's make command to build the git documentation but
will not attempt to install git itself.

INSTALLATION
============
To install the package you need a working git installation that you have the
permission to update, a unix shell and tar and a copy of the git-work tarball
that you built yourself or obtained from a download location.

If you have just built the tarball, you can simply change into the
build/gitwork-vX.X.X directory, otherwise unpack the tarball
as follows:

	gzip -dc gitwork-vX.X.X.tar.gz | tar -xvf -
	cd gitwork-vX.X.X

Once you are in the root directory of the untar'd package, run:

	sh ./installer install

This command will update the version of git found in git --exec-path.

To install the documentation, run:

	sh ./installer install-man

This command will install the man pages into $(git --exec-path)/../../share/man/man1.

UNINSTALL
=========
If you need to uninstall gitwork, run the following command:
       sh ./installer uninstall

RATIONALE
=========
At this stage the **git work** and **git base** commands are proposed for inclusion
into git, however, there is no guarantee that the proposal will be accepted. The
objective of this package is to allow people to experiment with the proposed
commands while the proposal is being evaluated.
