# Easily Deploy Nextflow on a VM on GCP with necessary config files
This repo will help you setup Nextflow to use during the hands on lab. Please refer to the Codelab guide shared with you for more information

The script assumes no default VPC network and that only internal IP addresses will be used.
The script will create the following in an empty project 
* A VPC and Subnet in the designated Region
* A firewall rule to allow access using IAP
* A Cloud NAT and required router to allow instances with internal IP addresses to access the internet
* A service Account with necessary permissions to run Batch and Life Sciecnes API
* A storage Bucket for input files and work directory
* A VM with Java, latest verion of Nextflow and a preconfigured nextflow confg file with a batch and LS API profiles


  ## Deploying to an existing project
  You can deploy the script to an new/existing project by following these steps
  1. Clone this repo to Cloud Shell and broswse to the repo fodler
  2. Enable Resource Manager and IAM services
     `gcloud services enable iam.googleapis.com cloudresourcemanager.googleapis.com`
  4. Make any desired changes to the variables
  5. Run terraform init
  6. Run terraform apply

  Once the terraform is fully execute it will display some information icluding the VM and Storag Bucket name and the gcloud commange to ssh to the VM.
  Note that it can take a few minutes for the installation script to finish, when it is complete you will see a Google Cloud ASCII logo when you SSH to the VM
