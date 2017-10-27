   * Install git-crypt: brew install git-crypt
     Run and Check if git crypt is installed: git-crypt --help
   * Initial git crypt: cd repo
                        git-crypt init
   * Specify files to encrypt by creating a .gitattributes file:
     '''
     secretfile filter=git-crypt diff=git-crypt
     *.key filter=git-crypt diff=git-crypt
     '''
   * Share  with other users: git-crypt add-gpg-user USER_ID
        Note: USER_ID could be a key ID, an email address. 
        This command will add and commit a GPG-encrypted ky file in the .git-crypt directory of the root of your repo
     Alternatively export a secret key: git-crypt export-key /path/to/key
        Note: Do not add this key file in repo. Send this file by email or other methods
   * Unlock encrypted file: git-crypt unlock /path/to/key
        Note: please download key file from TRACKSIDE-770 page
        
        That's all you need to do - after git-crypt is set up (either with git-crypt init or git-crypt unlock)
        You can use git normally - encryption and decryption happen transparently.
