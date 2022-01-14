.. _testing:

:tocdepth: 3

Applications and Tools in Testing
#################################

Using SSH and SFTP Clients with Duo
===================================

Until January 18, 2022 only ``login02.m2.smu.edu`` has Duo enabled.

SSH via Terminal Applications
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Users using SSH via a terminal application such as Terminal and iTerm on macOS,
Terminal on Linux, or PuTTY, MobaXTerm, and WSL on Windows will be prompted in
their terminal session for their password followed by a request for a Duo
**passcode** or ``1`` for a Duo push. The passcode can come from the Duo app or
from an OIT procured hardware token (faculty and staff only).

SFTP Clients
^^^^^^^^^^^^

Users using SFTP clients such as Transmit and Cyberduck on macOS or Cyberduck
and WinSCP on Windows will be prompted by the application for their password,
if not saved, followed by a request for a Duo **passcode** or ``1`` for a Duo
push. The passcode can come from the Duo app or from an OIT procured hardware
token (faculty and staff only).

Reducing the Number of Duo Authentications
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

An initial SSH/SFTP connection to M2 can be reused for subsequent connections,
which allows for multiple connections without being prompted by Duo repeatedly.

For those using OpenSSH (macOS, Linux, and Windows WSL), add the following to
your SSH ``~/.ssh/config`` file::

   Host *
     ControlMaster auto
     ControlPath ~/.ssh/sockets/ssh_mux_%h_%p_%r
     ControlPersist 600

For those using PuTTY on Windows, check the box "Share SSH connection if
possible" under "Category"; "Connection"; "SSH"; "Sharing an SSH connection
between PuTTY tools.

.. Note::

   Some applications or SFTP clients don't use ControlPersist and may
   occationally prompt for Duo authentication.

SSH Keys
^^^^^^^^

SSH keys to be used for SSH and SFTP clients, which allows for password-less
access, but still requires Duo authentication.

