# Ansible setup for fedora

Make sure that ansible is installed on the system.  
``` sudo dnf install ansible -y ```  

Once installed check the main.yml and check what the playbook installs.
It will install some of the tools needed for general dev work, but some of the tools installed are optional (cli tools, and some of the utils).

This is a working progress, so feel free to add any changes to the repo.

There is two playbooks ```main.yml``` and ```install-vscode.yml```, the ```main.yml``` will install most packages and the ```install-vscode-extensions.yml``` well ya it installs some vscode extensions.

The ```main.yml``` has to be run as sudo.  
``` sudo ansible-playbook main.yml```  

The vscode extensions has to be run without sudo.  
```ansible-playbook install-vscode-extensions.yml```

After the playbooks has run you will need to add your user to the docker group.
```sudo usermod -aG docker $USER ```

If you installed dbeaver you will have to restart the session (by logging out and back in agian, before its available).