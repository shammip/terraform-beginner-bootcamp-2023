# Terraform Beginner Bootcamp 2023

## Semantic Versioning

This project will utilize [semantic versioning](https://semver.org/) for its tagging. 
- Example: `1.0.1`

## Terraform CLI

CLI: Command Line Interface

### Terraform CLI Installation Code:

Updated the Terraform CLI installation script based on [Terraform Documentations](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli). 

### Linux Distribution: 

Checked the [Linux Distribution](https://opensource.com/article/18/6/linux-version) and determined that this project will run on Ubuntu. 

- Example: ```$ cat /etc/os-release```

### Bash Script:

Created a [bash script](./bin/install_terraform_cli) to install Terraform CLI, which will be called by the [GitPod task file (.gitpod.yml)](.gitpod.yml).

[Shebang](https://en.wikipedia.org/wiki/Shebang_(Unix)) is incorporated at the top of the bash script to determine which program will run the script. 

- Example: ```#!/usr/bin/env bash```

The bash script's [Linux permission](https://en.wikipedia.org/wiki/Chmod) was changed in order to be executable. 

- Example: ```$ chmod u+x ./bin/install_terraform_cli```

### GitPod Lifecycle 

Restarting a [GitPod workspace](https://www.gitpod.io/docs/configure/workspaces/tasks) will not process ```Init``` so ```Before``` was used. 



