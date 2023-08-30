<h3> Hey there! My name is TJ 👋 </h3>
<h4> A extremely helpful F5 Solutions Architect for SHI </h4>

> In this repo, we will demonstrate API Management with F5 Distributed Cloud (XC) - DNS using vscode
<img align="top" alt="GIF" src="https://github.com/tjvreugdenhil/f5xc-dns-zone-vscode/assets/20447165/1f759a05-39e5-4829-a74c-210f36154c03" width="200"/>

<h3> 👨🏻‍💻 PREPARATION </h3>

1) Download: [Visual Studio Code](https://code.visualstudio.com/)

2) Install “REST Client” Extension from the Visual Studio Code Marketplace:

`Ctrl + Shift + X -> search for humao.rest-client -> install
`
> Files ending with .http or .rest will automatically be syntax-highlighted


3) Install “Dotenv Official” Extension from the Visual Studio Code Marketplace:
   
`Ctrl + Shift + X -> search for dotenv.dotenv-vscode ->  install 
`

> This is used to quickly reference API tokens without exposing API tokens in code. 


4) Create API Token from F5 XC tenant:
> Administration > Personal Management > Credentials > Add Credentials

5) Rename ".env.sample" to ".env"
    
   > paste API token into the .env file

   > paste f5 XC tenant name into the .env file 

<h3>🛠 CREATE F5-XC DNS ZONE AND RECORDS</h3>

1) Verify F5 DNS Zone does not exist:
`{Send Request}:  "GET f5xc-demo.com.rest"
`
2) Create F5 DNS Zone:
`{Send Request}: "POST f5xc-demo.com zone.rest"
`
3) Verify F5 DNS Zone:
`{Send Request}:  "GET f5xc-demo.com.rest"
`
4) Replace F5 DNS Zone with new records:
`{Send Request}:  "PUT f5xc-demo.com zone.rest"
`

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
