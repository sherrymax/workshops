### Setup ADF workspace


#### Assumptions

The below commands are used to setup ADF Workspace in Amazon Linux.

#### Prerequisites


1. Install Node Version Manager - For BASH Shell
* Please run the below commands one after another.
    ```
    [ec2-user@ip-1-2-3-4 adp]$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash

    [ec2-user@ip-1-2-3-4 adp]$ chsh -s /bin/bash

    [ec2-user@ip-1-2-3-4 adp]$ cat /etc/shells

    [ec2-user@ip-1-2-3-4 adp]$ touch ~/.bash_profile

    [ec2-user@ip-1-2-3-4 adp]$ . ~/.bash_profile

	[ec2-user@ip-1-2-3-4 adp]$ . ~/.nvm/nvm.sh

    ```
    
* Open `.bash_profile` in VI editor
    ```
    [ec2-user@ip-1-2-3-4 adp]$ vi ~/.bash_profile
    ```

* Add below snippet to `.bash_profile` file in VI editor
    ```
    export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm    
    ``` 

* Verify the NVM installation. Once installed the response to below command will be `nvm`
    ```
	[ec2-user@ip-1-2-3-4 adp]$ command -v nvm
    ```
2. Install Node Version Manager - For ZSH
    * https://dev.to/saanchitapaul/install-nvm-node-version-manager-inside-zsh-34ke

    * https://gdevops.gitlab.io/tuto_javascript/installation/nvm/nvm.html
<br/>

3. Install a specific version of NVM (e.g. : 18.17.0)
    ```
    [ec2-user@ip-1-2-3-4 adp]$ nvm install 18.17.0
    ```
    >Note: The above command will install NodeJS and NPM.

4. Check NodeJS version
    ```
    [ec2-user@ip-1-2-3-4 adp]$ node --version
    ```

5. Check NPM version
    ```
    [ec2-user@ip-1-2-3-4 adp]$ python3npm --version
    ```

6. Verify if Python is available, by typing `python3` at command prompt. 
    ```
    [ec2-user@ip-1-2-3-4 adp]$ python3
    ```
    If not install it by `sudo yum install python`

7. Install Yoeman
    ```
    [ec2-user@ip-1-2-3-4 adp]$ npm install -g yo
    ```
8. Install the latest version of the [generator-alfresco-adf-app](https://github.com/Alfresco/generator-alfresco-adf-app)
    ```
    [ec2-user@ip-1-2-3-4 adp]$ npm install -g generator-alfresco-adf-app@latest
    ```
9. Install the Angular CLI
    ```
    [ec2-user@ip-1-2-3-4 adp]$ npm install -g @angular/cli
    ```

10. Navigate to a Project Folder 
    ```
    [ec2-user@ip-1-2-3-4 adp]$ cd <project-folder-name>
    ```

11. Create your First ADF application
    ```
    [ec2-user@ip-1-2-3-4 adp]$ yo alfresco-adf-app
    ```
12. If needed, download source code of an example ADF application from [Alfresco ADF GitHub](https://github.com/Alfresco/alfresco-ng2-components/tree/develop/demo-shell)
    ```
    [ec2-user@ip-1-2-3-4 adp]$ sudo yum install git

    [ec2-user@ip-1-2-3-4 adp]$ git clone https://github.com/Alfresco/alfresco-ng2-components.git

    [ec2-user@ip-1-2-3-4 adp]$ cd alfresco-ng2-components

    [ec2-user@ip-1-2-3-4 adp]$ npm install

    [ec2-user@ip-1-2-3-4 adp]$ npm start
    ```
