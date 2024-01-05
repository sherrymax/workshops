### Setup ADF workspace


#### Assumptions

The below commands are used to setup ADF Workspace in Amazon Linux.

#### Remote Connect using VS Code

```
Host adf-workshop-env-1
    HostName ec2-18-232-63-233.compute-1.amazonaws.com
    IdentityFile <your-path>/smathews-aws.pem
    User ec2-user

Host adf-workshop-env-2
    HostName ec2-54-85-125-38.compute-1.amazonaws.com
    IdentityFile <your-path>/smathews-aws.pem
    User ec2-user
```

#### Installation Steps

1. Install Node Version Manager - For BASH Shell
* Please run the below commands, one after another.
    ```
    [ec2-user@ip-1-2-3-4 ~]$ mkdir adf-workshop && cd adf-workshop

    [ec2-user@ip-1-2-3-4 adf-workshop]$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash

    [ec2-user@ip-1-2-3-4 adf-workshop]$ chsh -s /bin/bash

    [ec2-user@ip-1-2-3-4 adf-workshop]$ cat /etc/shells

    [ec2-user@ip-1-2-3-4 adf-workshop]$ touch ~/.bash_profile

    [ec2-user@ip-1-2-3-4 adf-workshop]$ . ~/.bash_profile

	  [ec2-user@ip-1-2-3-4 adf-workshop]$ . ~/.nvm/nvm.sh

    ```

* Open `.bash_profile` in VI editor
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ vi ~/.bash_profile
    ```

* Add below snippet to `.bash_profile` file in VI editor
    ```
    export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm    
    ```

* Verify the NVM installation. Once installed the response to below command will be `nvm`
    ```
	[ec2-user@ip-1-2-3-4 adf-workshop]$ command -v nvm
    ```
2. Install Node Version Manager - For ZSH
    * https://dev.to/saanchitapaul/install-nvm-node-version-manager-inside-zsh-34ke

    * https://gdevops.gitlab.io/tuto_javascript/installation/nvm/nvm.html

3. Install a specific version of NVM (e.g. : 18.17.0)
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ nvm install 18.17.0
    ```
    >Note: The above command will install NodeJS and NPM.

4. Check NodeJS version
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ node --version
    ```

5. Check NPM version
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ npm --version
    ```

6. Verify if Python is available, by typing `python3` at command prompt.
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ python3
    ```
    If not install it by `sudo yum install python3`

7. Install Yoeman
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ npm install -g yo
    ```
8. Install the latest version of the [generator-alfresco-adf-app](https://github.com/Alfresco/generator-alfresco-adf-app)
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ npm install -g generator-alfresco-adf-app@latest
    ```
9. Install the Angular CLI
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ npm install -g @angular/cli
    ```

10. Create and navigate to a Project Folder
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ cd <project-folder-name>
    ```

11. Create your First ADF application
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ yo alfresco-adf-app
    ```

12. If needed, download source code of an example ADF application from [Alfresco ADF GitHub](https://github.com/Alfresco/alfresco-ng2-components/tree/6.4.0)
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ nvm install 20.9.0

    [ec2-user@ip-1-2-3-4 adf-workshop]$ nvm use 20.9.0

    [ec2-user@ip-1-2-3-4 adf-workshop]$ cd workshop/<username>

    [ec2-user@ip-1-2-3-4 adf-workshop]$ curl -X GET "http://ec2-44-210-156-223.compute-1.amazonaws.com/alfresco/api/-default-/public/alfresco/versions/1/nodes/6dd1eb7f-e29e-4fa3-b406-c5ae7b32cd7d/content?attachment=true" -H  "accept: application/octet-stream" -H  "authorization: Basic ZGVtbzpkZW1v" --output alfresco-ng2-components-6.4.0.zip

    [ec2-user@ip-1-2-3-4 adf-workshop]$ unzip alfresco-ng2-components-6.4.0.zip    

    [ec2-user@ip-1-2-3-4 adf-workshop]$ cd alfresco-ng2-components-6.4.0

    ```

13. Add a .env file and update with your Sandbox IP.
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ echo 'PROXY_HOST_ADF="http://<my-sandbox-IP>"' >> .env
    ```

14. Install NPM
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ npm install
    ```

15. Start the ADF app.
    ```
    [ec2-user@ip-1-2-3-4 adf-workshop]$ npm start
    ```
