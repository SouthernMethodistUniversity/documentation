.. _testing:

:tocdepth: 3

Applications and Tools in Testing
#################################

Using SSH and SFTP Clients with Duo
===================================

SSH via Terminal Applications
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Users using SSH via a terminal application such as Terminal and iTerm on macOS,
Terminal on Linux, or Putty, MobaXTerm, and WSL on Windows will be prompted in
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

SSH Keys
^^^^^^^^

Authorization is required for SSH keys to be used for SSH and SFTP clients,
which allows for password-less access, but still requires Duo authentication.
If you would like to use SSH keys, please send your request to help@smu.edu
with "HPC: SSH Keys" in the subject line.

Known Issues
^^^^^^^^^^^^

If you are using SSH keys and you are logging in without keys, you will be
prompted by Duo twice. This double Duo prompting may impact the ability to
login from certain non-terminal clients.

If you are using SSH keys and you are logging in without keys and using a
non-terminal client you may not be able to log in using a passcode alone. A
workaround is to install the Duo app.

