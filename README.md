What is nullDVCS?
-----------------

**nullDVCS** is a lightweight, concurrent version control system targeted at Mono development.

Why use nullDVCS?
-----------------

Compared to git and mercurial, nullDVCS provides scalable access to an arbitrary number of
developers - in fact, the number of participants in a nullDVCS scheme approaches infinity,
and is only limited by the number of computers which currently both exist and run a POSIX
compliant OS.

Compared to SVN or CVS, nullDVCS has 80% less eldrich horror, and much simpler syntax.

Finally, nullDVCS is lightweight - the whole system is less than 10kb! For those of you
developing on pocket calculators, you can breathe a sigh of relief.


What operating systems are supported?
-------------------------------------

Currently BSD, Mac OS X, and Linux. Porting efforts are underway to bring nullDVCS to
Windows, as the efficient, non-iterative storage paradigm is expected to be particularly
beneficial to mainstream .NET development.


How does it work?
-----------------

As the name implies, nullDVCS stores versioning data efficiently in the `/dev/null` device
available on POSIX systems. Writing to `/dev/null` is *extremely* efficient even on slow
systems, and no matter how much data you store, you can rest easy knowing your entire team
has access to the exact same content. One benefit of nullDVCS is efficiency: a team using
our system will produce *radically* fewer versions, which will make management much easier.


FAQ
---

###Q. What are the system requirements?
A. We have had limited success deploying nullDVCS on embedded systems running BusyBox. It's
reasonable to assume that it will work on your development systems, though if you have issues
please let us know.

###Q. How do I keep changes synced between development machines?
A. You don't have to worry about this. Transactions with `/dev/null` are completely atomic,
and each developer is guaranteed to be working off the same dataset.

###Q. How much bandwidth is required for syncing versions?
A. We have successfully tested nullDVCS on dialup, and even for very large codebases we
experienced acceptable performance. One time the phone cord wasn't even plugged in to anything!

###Q. How does merging work?
A. What?

###Q. I've accidentally deleted my source tree, what do I do?
A. Don't worry! You've actually just stored your working tree alongside your historical
versions. It's fine.

###Q. How do I get it back out?
A. Try merging your filesystem with the nullDVCS contents as follows:

    rm -rf /
    
###Q. Is nullDVCS's licensing suitable for corporate use?
A. There are a lot of misconceptions about the use of GPL software, but the short answer is yes,
that's absolutely fine. As long as you (or your business) are not **redistributing** software
based on the GPL'd code, no licensing restrictions come into play. It's worth noting that
"redistribution" does not include providing the software to employees for business use.

For additional clarity, let us examine this excerpt from the <a href='http://www.gnu.org/licenses/gpl-faq.html#GPLRequireSourcePostedPublic'>GPL FAQ:</a>

    Does the GPL require that source code of modified versions be posted to the public?

    The GPL does not require you to release your modified version,
    or any part of it. You are free to make modifications and use
    them privately, without ever releasing them. This applies to
    organizations (including companies), too; an organization can
    make a modified version and use it internally without ever
    releasing it outside the organization.
    
    But if you release the modified version to the public in some
    way, the GPL requires you to make the modified source code
    available to the program's users, under the GPL.
    
    Thus, the GPL gives permission to release the modified
    program in certain ways, and not in other ways; but the
    decision of whether to release it is up to you.
    
    
###Q. What filesystems does nullDVCS support?
A. Though in theory it should support any filesystem mounted in a POSIX environment,
nullDVCS has only been tested with EXT4.
