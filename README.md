# Webserver Cluster Module

A reusable Terraform module that deploys a highly available web server cluster on AWS using an Auto Scaling Group and Application Load Balancer.

## Usage
```hcl
module "webserver_cluster" {
  source = "path/to/modules/services/webserver-cluster"

  cluster_name  = "webservers-dev"
  instance_type = "t3.micro"
  min_size      = 2
  max_size      = 4
}
```

## Inputs

| Name | Description | Type | Required |
|------|-------------|------|----------|
| cluster_name | Name for all cluster resources | string | yes |
| instance_type | EC2 instance type | string | no |
| min_size | Minimum ASG instances | number | yes |
| max_size | Maximum ASG instances | number | yes |
| server_port | HTTP port | number | no |

## Outputs

| Name | Description |
|------|-------------|
| alb_dns_name | DNS name of the load balancer |
| asg_name | Name of the Auto Scaling Group |
