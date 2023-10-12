# Terraform Beginner Bootcamp 2023

## Semantic Versioning

This project will utilize [semantic versioning](https://semver.org/) for its tagging. 
- Example: `1.0.1`

## Terraform CLI

CLI: Command Line Interface

### Terraform CLI Installation Code:

Updated the Terraform CLI installation script based on [Terraform Documentations](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli). 

### Linux Distribution: 

Checked the [Linux Distribution](https://opensource.com/article/18/6/linux-version) and determined that this project will run on Ubuntu: `$ cat /etc/os-release`.

### Bash Script:

Created a [bash script](./bin/install_terraform_cli) to install Terraform CLI, which will be called by the [GitPod task file (.gitpod.yml)](.gitpod.yml).

[Shebang](https://en.wikipedia.org/wiki/Shebang_(Unix)) is incorporated at the top of the bash script so that the interpreter will process the script: `#!/usr/bin/env bash`.

The bash script's [Linux permission](https://en.wikipedia.org/wiki/Chmod) was changed in order to be executable: `$ chmod u+x ./bin/install_terraform_cli`.

### GitPod Lifecycle: 

Restarting a [GitPod workspace](https://www.gitpod.io/docs/configure/workspaces/tasks) will not process `Init` so `Before` was used. 

### Environment Variables (env vars):

List env vars: `env`. Filter specific env vars using grep: `env | grep AWS_`.

Set env vars in terminal: `export HELLO='world'`. Unset env vars in terminal: `unset HELLO`. Temporarily et env var when running a command: `HELLO='world' ./bin/print_message`.

 Set env var without export in bash script: 
 ```sh
 #!/usr/bin/env bash
 HELLO='world'
 echo $HELLO
 ```

Print env var using echo: `echo $HELLO`.

A new bash terminal that is opened in VSCode will not know of env var that were set in another window. This can be remedied by setting env vars in bash profile: `bash_profile`.

Store env vars in GitPod Secret Storage to persist them: `gp env HELLO='world'`. This allows future workspaces to set env vars for all bash terminals. Another option is to set only non-sensitive env vars in `.gitpod.yml` file. 

## AWS CLI

Installed [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) via bash script, [./bin/install_aws_cli](./bin/install_aws_cli).

Configured AWS CLI using [ Env Vars](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html).

Generated AWS CLI credentials from IAM User. Checked if credentials were configured correctly using `aws sts get-caller-identity` and this format was displayed in json:
```json
{
    "UserId": "123456789012345678901",
    "Account": "123456789012",
    "Arn": "arn:aws:iam::123456789012:user/terraform-beginner-bootcamp"
}
```

## Terraform Basics

[Terraform Registry](https://registry.terraform.io/) is used for providers and modules. Provider [random](https://registry.terraform.io/providers/hashicorp/random/latest) was used. Provider binaries are stored in `.terraform`. 

Terraform Console lists Terraform commands using: `terraform`. 
- Run `terraform init` to download provider binaries, at project start. 
- Run `terraform plan` to display changes.
- Run  `terraform apply` to apply changes, with prompting or run  `terraform apply --auto-approve` to apply changes, without prompting. 

Terraform Lock File, `.terraform.lock.hcl`, has providers or modulues locked versioning and it is **committed** to the Version Control System (GitHub).

Terraform State File, `.terraform.tfstate`, has details regarding infrastructure's current state and it is **not committed** to Version Control System (GitHub). The previous version of the state file is `.terraform.tfstate.backup`.





