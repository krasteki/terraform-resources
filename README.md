# This repository creates application hosted on publicity EC2 instance in AWS with security group which allow port 80 (default region - US West (Oregon) - us-west-2)

### Prerequisites

- Terraform (version used v1.1.5) - Check [here](https://learn.hashicorp.com/tutorials/terraform/install-cli) for install instructions.
- AWS subscription - Check [here](https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Types=*all&awsf.Free%20Tier%20Categories=*all) for AWS Free Tier.
- Before you can build the infrastructure, you need to provide your AWS credentials to Terraform as environment variables. You can create AWS credentials on [this page](https://console.aws.amazon.com/iam/home?#security_credential).

### Setup Instructions

#### I. Clone the repo

```
https://github.com/krasteki/terraform-resources.git
```

#### II. Authenticate to AWS

```
$ export AWS_ACCESS_KEY_ID=YOUR_ACCESS_KEY
$ export AWS_SECRET_ACCESS_KEY=YOUR_SECRET_KEY
```

**Note**: You may need to also export your `AWS_SESSION_TOKEN` and `AWS_SESSION_EXPIRATION` as **environment variables**.

#### III. Run the following commands in the cloned folder:

1. `$ terraform init` - Initializing a configuration directory downloads and installs the providers defined in the configuration, which in this case is the aws provider. It will prints out which version of the provider was installed. Terraform also creates a lock file named `.terraform.lock.hcl` which specifies the exact provider versions used, so that you can control when you want to update the providers used for your project.
2. `$ terraform fmt` - Automatically updates configurations in the current directory for readability and consistency. Format the configuration. Terraform will print out the names of the files it modified, if any. In this case, the configuration file was already formatted correctly, so Terraform won't return any file names.
3. `$ terraform validate` - Validates the configuration.
4. `$ terraform plan` - Creates an execution plan, which lets you preview the changes that Terraform plans to make to the infrastructure.
5. `$ terraform apply` - Creates the infrastructure.

#### IV. Check the output of `application-url`:

- In your browser, visit the `application-url` address from Terraform's output to view the PHP application. The address should start with `http`, not `https`.

![image](https://user-images.githubusercontent.com/51786552/154457382-6d883b8a-ee9f-40a0-9ddf-89d214cdbd1d.png)





