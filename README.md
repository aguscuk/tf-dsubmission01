## tf-dsubmission01

### REFF https://github.com/gruntwork-io/terraform-google-sql

### first, create file terraform.tfvars
```
master_user_name        = "your_username"
master_user_password    = "your_password"
name_prefix             = "your_prefix"
project                 = "your_project_id"
region                  = "your_region"
```


### 2nd, using cloudsql-proxy
wget https://dl.google.com/cloudsql/cloud_sql_proxy.linux.amd64 -O cloud_sql_proxy

cloud_sql_proxy -dir /tmp/cloudsql \
-instances=$project:$region:[database name]=tcp:3306 \
-credential_file=[service account credential]