### Setup ADF workspace


#### Assumptions

The below commands are used to setup ADF Workspace in Amazon Linux.

#### Remote Connect to the Repository using VS Code

> For Unix users : Enter the remote repository values in the config file under /Users/<username>/.ssh

```
Host adf-shop-env-1
    HostName ec2-18-232-63-233.compute-1.amazonaws.com
    IdentityFile <your-path>/<pem-file-name>.pem
    User ec2-user

Host adf-shop-env-2
    HostName ec2-54-85-125-38.compute-1.amazonaws.com
    IdentityFile <your-path>/<pem-file-name>.pem
    User ec2-user
```

#### Installation Steps

1. Install Node Version Manager - <b>For BASH Shell</b>
* Please run the below commands, one after another.
    ```
    [ec2-user@ip-1-2-3-4 ~]$ mkdir adf-shop && cd $_

    [ec2-user@ip-1-2-3-4 adf-shop]$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash

    Optional step to Change Shell
    [ec2-user@ip-1-2-3-4 adf-shop]$ chsh -s /bin/bash

    [ec2-user@ip-1-2-3-4 adf-shop]$ cat /etc/shells

    [ec2-user@ip-1-2-3-4 adf-shop]$ touch ~/.bash_profile

    [ec2-user@ip-1-2-3-4 adf-shop]$ . ~/.bash_profile

    [ec2-user@ip-1-2-3-4 adf-shop]$ . ~/.nvm/nvm.sh

    ```

* Open `.bash_profile` in VI editor
    ```
    vi ~/.bash_profile
    ```

* Add below snippet to `.bash_profile` file in VI editor
    ```
    export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm    
    ```

* Verify the NVM installation. Once installed the response to below command will be `nvm`
    ```
	command -v nvm
    ```
2. Install Node Version Manager - <b>ONLY For ZSH</b>
    * https://dev.to/saanchitapaul/install-nvm-node-version-manager-inside-zsh-34ke

    * https://gdevops.gitlab.io/tuto_javascript/installation/nvm/nvm.html

3. Install a specific version of NVM (e.g. : 18.17.0)
    ```
    nvm install 18.17.0
    nvm install 20.9.0
    ```
    >Note: The above command will install NodeJS and NPM.

4. Check NodeJS version
    ```
    node --version
    ```

5. Check NPM version
    ```
    npm --version
    ```

6. Verify if Python is available, by typing `python3` at command prompt.
    ```
    python3
    ```
    If not install it by `sudo yum install python3`.
    > Press `Ctrl+D` to quit and return the prompt.

7. Install `build-essentials` package.
    ```
    sudo yum install gcc-c++ make
    ```

8. Install Yoeman
    ```
    npm install -g yo

    *** Use Yoeman v4.3.1 due to errors with latest version of Yoeman ***
    npm install -g yo@4.3.1
    ```
9. Install the latest version of the [generator-alfresco-adf-app](https://github.com/Alfresco/generator-alfresco-adf-app)
    ```
    npm install -g generator-alfresco-adf-app@latest
    ```
10. Install the Angular CLI
    ```
    npm install -g @angular/cli
    ```

11. Check Angular version
    ```
     ng version
    ```

12. Create and navigate to a Project Folder
    ```
    mkdir <project-folder-name>
    cd <project-folder-name>
    ```

13. Create your First ADF application
    ```
    yo alfresco-adf-app
    ```

14. If needed, download source code of an example ADF application from [Alfresco ADF GitHub](https://github.com/Alfresco/alfresco-ng2-components/tree/6.4.0)
    ```
    nvm install 20.9.0

    nvm use 20.9.0

    cd workshop/<username>

    curl -X GET "http://ec2-44-210-156-223.compute-1.amazonaws.com/alfresco/api/-default-/public/alfresco/versions/1/nodes/6dd1eb7f-e29e-4fa3-b406-c5ae7b32cd7d/content?attachment=true" -H  "accept: application/octet-stream" -H  "authorization: Basic ZGVtbzpkZW1v" --output alfresco-ng2-components-6.4.0.zip

    unzip alfresco-ng2-components-6.4.0.zip    

    cd alfresco-ng2-components-6.4.0

    ```

15. Add a .env file and update with your Sandbox IP.
    ```
    echo 'PROXY_HOST_ADF="http://<my-sandbox-IP>"' >> .env
    ```

16. Install NPM
    ```
    npm install
    ```

17. Start the ADF app.
    ```
    npm start
    ```
