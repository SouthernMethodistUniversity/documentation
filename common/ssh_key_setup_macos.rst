Run the following commands from a terminal on the *local computer* that you want to have key-based access to ManeFrame II.

#. ``m2_username=<your M2 username>`` "<your M2 username>" is set to your M2 username to be used for the subsequent commands.
#. ``ssh-keygen -q -t ecdsa -f ~/.ssh/id_ecdsa_m2`` You will need generate a password for accessing the key (not SMU nor computer password).
#. ``cat ~/.ssh/id_ecdsa_m2.pub | ssh ${m2_username}@m2.smu.edu "mkdir -p ~/.ssh && chmod 0700 ~/.ssh && touch ~/.ssh/authorized_keys && chmod 0700 ~/.ssh/authorized_keys && cat >> ~/.ssh/authorized_keys && chmod 0400 ~/.ssh/authorized_keys"`` Press *enter* and you will be prompted for your M2 password.
#. ``printf "Host *m2.smu.edu\n  User %s\n  IdentityFile ~/.ssh/id_ecdsa_m2\nHost *\n  UseKeychain yes\n  AddKeysToAgent yes\n" "${m2_username}" >> ~/.ssh/config``
#. ``ssh-add --apple-use-keychain ~/.ssh/id_ecdsa_m2`` You will be asked for the key's password, if present.
