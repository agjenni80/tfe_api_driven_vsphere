# tfe_api_driven_vsphere
Terraform Enterprise API driven runs in vsphere

This is specifically for the Application1-Stage workspace in the SE_Org Organizaqtion.

# This repo is building on the work done in this repo: 
https://github.com/AdamCavaliere/TFE_API_Driven_Runs/blob/master/api-pushCode.py

# Step 1
Clone this repo

# Step 2
Set your PTFE_TOKEN environment variable

$ export PTFE_TOKEN=<token generated from Team in workspace>

# Step 3
Run the python script

$ python api-pushCode.py

You may need to change the workspace name.
This will do an auto apply (because it is set to on the workspace), picking up your main.tf file to create resources. 


# Step 4

To Destroy your infrastructure, you can use a curl command calling the destroy_plan.json

curl \
--header "Authorization: Bearer $PTFE_TOKEN" \
--header "Content-Type: application/vnd.api+json" \
--request POST \
--data @destroy_plan.json \
https://ptfe.this-demo.rocks/api/v2/runs


