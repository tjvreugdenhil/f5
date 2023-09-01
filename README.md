<h3> Hey there! My name is TJ 👋 </h3>
<h4> A extremely helpful F5 Solutions Architect </h4>

> In this repo, we will demonstrate API Management with F5 Distributed Cloud (XC) - DNS using vscode
<img align="top" alt="GIF" src="https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/1f759a05-39e5-4829-a74c-210f36154c03" width="200"/>

<h3> 👨🏻‍💻 PREPARATION </h3>

1) Download: [Visual Studio Code](https://code.visualstudio.com/)

   ![visual-studio-code](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/7bfce184-3a3d-49b9-a93a-f1d5c78501d0)


2) Install [REST Client Extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) from the Visual Studio Code Marketplace:

`Ctrl + Shift + X -> search for humao.rest-client -> install
`
      ![restclient](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/b3774426-abcb-4fdc-afec-a0ef5032a6e0)

> Files ending with .http or .rest will automatically be syntax-highlighted


3) Install [Dotenv Official Extension](https://marketplace.visualstudio.com/items?itemName=dotenv.dotenv-vscode) from the Visual Studio Code Marketplace:
   
`Ctrl + Shift + X -> search for dotenv.dotenv-vscode ->  install 
`
      ![dotenv](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/de319c92-c6b2-484f-a3f9-b53a73fd3ca6)

> This is used to quickly reference API tokens without exposing API tokens in code. 


4) Create API Token from F5 XC tenant:
   
   ![f5xc home](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/67f27e89-b228-42f9-87d0-f9abd80784b6)

> Administration > Personal Management > Credentials > Add Credentials

   ![f5xc-api-token](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/cad1fe80-d5ac-4ba8-b404-97eef6ffdb38)

5) Clone this github repository by using the git bash terminal in vscode

   ![git bash](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/9064d58e-9ee5-4c66-a450-46cefa305d32)

`   gh repo clone tjvreugdenhil/f5xc-dns-zone-vscode 
`

7) Rename ".env.sample" from github repo to ".env"
    
   > paste API token into the .env file

   > paste f5 XC tenant name into the .env file 

<h3>🛠 CREATE F5-XC DNS ZONE AND RECORDS</h3>

1) Verify F5 DNS Zone does not exist:
`{Send Request}:  "GET f5xc-demo.com.rest"
`
![GET](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/56d54c92-1920-4eec-94d0-dc9299919618)

2) Create F5 DNS Zone:
`{Send Request}: "POST f5xc-demo.com zone.rest"
`

![POST](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/e355366d-9bf9-4e74-a523-41273e9596f3)

3) Verify F5 DNS Zone:
`{Send Request}:  "GET f5xc-demo.com.rest"
`

![GET](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/56d54c92-1920-4eec-94d0-dc9299919618)

4) Replace F5 DNS Zone with new records:
`{Send Request}:  "PUT f5xc-demo.com zone.rest"
`

![PUT](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/81ebe06b-f24d-4bff-bd74-356ed335fdad)

![200 OK after PUT](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/ab5bd601-a451-4a6e-9bda-bcf615a60c57)

![f5 dns zone verification](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/569d15d3-a253-4ad6-a897-88b9c986e4cf)


6) Delete F5 DNS Zone
`{Send Request}:  "DELETE f5xc-demo.com zone.rest"
`

![DELETE](https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/22f2adfa-51f3-482e-acbf-ea7972fd5147)

**ADDITIONAL INFORMATION:**

> #POST - Creates DNS Zone. If one already exists, it will give an error.

> #PUT - Replaces DNS Zone 

> #GET - Lists DNS Zone or use "curl GET f5xc-demo.com zone.rest"

> #DELETE - Deletes DNS Zone


#If using "f5xc-backup.sh" - install jq for Windows by running this curl in gitbash or the vscode bash terminal

`curl -L -o /usr/bin/jq.exe https://github.com/stedolan/jq/releases/latest/download/jq-win64.exe
`

#Install vscode thunder client extension to build REST collections: 

`Ctrl + Shift + X -> search for rangav.vscode-thunder-client -> install 
`

#install gitignore for .env file:

`Ctrl + Shift + X -> codezombiech.gitignore -> install 
`
