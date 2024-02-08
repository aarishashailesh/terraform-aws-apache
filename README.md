# AWS Terraform Apache Module
Terraform module which creates AWS Apache Instance.

## Usage
```hcl

terraform {
}

module "aws_server" {
  source          = ".//terraform-aws-apache-example"
  vpc_id          = "vpc-XXXXXXXX"
  my_ip_with_cidr = "100.XX.XX.XXX/32"
  public_key      = "ssh-rsa AAAXXX..."
  instance_type   = "t2.micro"
  server_name     = "Apache Example Server"
}

output "public_ip" {
  value = module.aws_server.instance_public_ip
}

```