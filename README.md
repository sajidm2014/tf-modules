# Terraform modules for AWS, GCP & Azure code.
```
Multi Cloud Deployments of micro-services and Data Bases.
```

## Git CLI for terraform modules 
mkdir tf-modules
cd tf-modules
cp -r /data/modules/* .
git init

git add .
git branch

git commit -m "First commit for modules"

git branch 
git branch dev
git branch

git tag -a "v1.0" -m "modules version v1.0"
git remote add origin https://github.com/sajidm2014/tf-modules.git

git push -uf origin master/main  --follow-tags

## Use tf-modules on github as follws

```
provider "aws" {
	region = "us-west-1"
}

```

## main.tf
```
module "aws-compute" {
  source = "git::git@github.com:sajidm2014/tf-modules.git//aws_EC2?ref=v1.0"
  type = "t2.micro"
  ami = data.aws_ami.ami.id
  az = "us-west-1"
  fwname = "secgrp_prod"
  inport = 80
  inprot = "tcp"
  secgrp = module.aws-compute.secgrp
  tags = "ec2-prod"
  
}


```

## terraform cli setup
```
terraform init
terraform plan
terraform apply
terraform destroy
```

