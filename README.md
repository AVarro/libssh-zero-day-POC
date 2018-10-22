=======================================================================
== Subject:    Authentication bypass in server code
==
== CVE ID#:    CVE-2018-10933
==
== Versions:   All versions of libssh 0.6 and later
==
== Summary:    There is a vulnerability within the server code which
==             can enable a client to bypass the authentication
==             process and set the internal state machine maintained
==             by the library to authenticated, enabling the
==             (otherwise prohibited) creation of channels.
==
=======================================================================

===========
Description
===========

libssh versions 0.6 and above have an authentication bypass vulnerability in
the server code.  By presenting the server an SSH2_MSG_USERAUTH_SUCCESS message
in place of the SSH2_MSG_USERAUTH_REQUEST message which the server would expect
to initiate authentication, the attacker could successfully authentciate
without any credentials.

The bug was discovered by Peter Winter-Smith of NCC Group.

==================
Patch Availability
==================

Patches addressing the issue have been posted to:

    https://www.libssh.org/

libssh version 0.8.4 and libssh 0.7.6 have been released to address this issue.

==========
Workaround
==========

There is no workaround for this issue.

=======
Credits
=======

The bug was discovered by Peter Winter-Smith of NCC Group.# libssh zero day POC
