### Steps for setting up Alfresco Digital Workspace (ADW)

--------------------


1. Create a folder and Navigate into that folder
```
mkdir username-adw
cd username-adw
```

2.  Download ADW 4.3.0 Source Code into the folder.
```
    [ec2-user@ip-1-2-3-4 adp]$ curl -X GET "http://ec2-44-210-156-223.compute-1.amazonaws.com/alfresco/api/-default-/public/alfresco/versions/1/nodes/d6ea5403-f6ff-4c24-a435-4ec03335019d/content?attachment=true" -H  "accept: application/octet-stream" -H  "authorization: Basic ZGVtbzpkZW1v" --output alfresco-digital-workspace-4.3.0-source-code.zip
```

3. Unzip
```
unzip alfresco-digital-workspace-4.3.0-source-code.zip -d alfresco-digital-workspace-4.3.0-source-code

cd alfresco-digital-workspace-4.3.0-source-code

```

4. NPM Clean Install
```
npm ci

npm install
```

5. Delete .env file and Create again your Sandbox IP.
```
rm -rf .env

Env 1 : [ec2-user@ip-1-2-3-4 adp]$ echo 'BASE_URL="http://18.232.63.233"' >> .env
Env 2 : [ec2-user@ip-1-2-3-4 adp]$ echo 'BASE_URL="http://54.85.125.38"' >> .env

```

6. Update the `app.config.json` located at `alfresco-digital-workspace-4.3.0-source-code/apps/content-ee/src/app.config.json`.
   Its `authType` field should be updated to 'BASIC'.
```
"authType": "BASIC",
```

6. NPM Start
```
npm start content-ee
```
