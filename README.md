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

[Shebang](https://en.wikipedia.org/wiki/Shebang_(Unix)) is incorporated at the top of the bash script so that the interpreter will process the script. 

- Example: ```#!/usr/bin/env bash```

The bash script's [Linux permission](https://en.wikipedia.org/wiki/Chmod) was changed in order to be executable. 

- Example: ```$ chmod u+x ./bin/install_terraform_cli```

### GitPod Lifecycle: 

Restarting a [GitPod workspace](https://www.gitpod.io/docs/configure/workspaces/tasks) will not process ```Init``` so ```Before``` was used. 

### Environment Variables (env vars):

List env vars: ```env```. Filter specific env vars using grep: ```env | grep AWS_```

Set env vars in terminal: ```export HELLO='world'```. Unset env vars in terminal: ```unset HELLO```. Temporarily et env var when running a command: ```HELLO='world' ./bin/print_message```

 Set env var without export in bash script: 
 ```sh
 #!/usr/bin/env bash
 HELLO='world'
 echo $HELLO
 ```

Print env var using echo: ```echo $HELLO```

A new bash terminal that is opened in VSCode will not know of env var that were set in another window. This can be remedied by setting env vars in bash profile: ```bash_profile```

Store env vars in GitPod Secret Storage to persist them: ```gp env HELLO='world'```. This allows future workspaces to set env vars for all bash terminals. Another option is to set only non-sensitive env vars in ```.gitpod.yml``` file. 

