### Steps for setting up Alfresco Digital Workspace (ADW)

--------------------


1. Create a folder and Navigate into that folder
```
mkdir adw6
cd adw6
```

2.  Download ADW 6.0.0 Source Code into the folder.
```
    curl -X GET "http://ec2-34-204-80-138.compute-1.amazonaws.com/alfresco/api/-default-/public/alfresco/versions/1/nodes/5ad9f098-bca4-45e8-99f0-98bca445e884/content?attachment=true" -H  "accept: application/octet-stream" -H  "authorization: Basic ZGVtbzpkZW1v" --output alfresco-digital-workspace-6.0.0-source-code.zip
```

3. Unzip `alfresco-digital-workspace-6.0.0-source-code.zip` File
```
unzip alfresco-digital-workspace-6.0.0-source-code.zip -d alfresco-digital-workspace-6.0.0-source-code

cd alfresco-digital-workspace-6.0.0-source-code

```

4. NPM Clean Install
```
npm ci

npm install
```

5. Delete .env file and Create again your Sandbox IP.
```
Open .env file
Add the following line and update your hostname

BASE_URL="http://<your-hostname>"

```

6. Update the `app.config.json` located at `alfresco-digital-workspace-6.0.0-source-code/apps/content-ee/src/app.config.json`.
   Its `authType` field should be updated to 'BASIC'.
```
"authType": "BASIC",
```

6. NPM Start
```
npm start content-ee
```

