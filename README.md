### Terraform Provider Google Cloud
#### open terminal
```
gcloud auth application-default login
```

#### cd alamat directory
```
terraform init
```

#### run main.tf
```
terraform apply
```

#### run cepat
```
terraform apply -auto-approve
```

#### menghapus resource(tidak disarankan)
```
terraform destroy -target google_compute_subnetwork.dev_subnet_02
```

#### terraform state
- list resource in the state ```terraform state list```
- move an item in the state ```terraform state mv```
- pull current state and output to stdout ```terraform state pull```
- update remote state from a local state file ```terraform state push```
- remove instances from the state```terraform state rm```
- show a resource in the state```terraform state show ```

#### melihat preview resource dan atribut
```terraform plan```

#### jika pakai nama file terraform.tfvars custom
```terraform apply -var-file terraform-dev.tfvars```



#### configurasi service account google cloud lewat environment variable
IAM & Admin => Service Account => Create Service Account => role editor

### Generate Credential
dibawah kolom Action tekan tombol tiga titik => Manage Keys => ADD KEY => Create new key => JSON => CREATE


### Logout Terraform Provider Google Cloud
#### open terminal
```gcloud auth application-default revoke```

#### mengasih input values ke variable melalui environment variable (TF_VAR_name)
```export TF_VAR_google_credentials=/Users/alsyodi/Downloads/aldisypu-labs-4036b.json```
```export TF_VAR_google_credentials=$(cat /Users/alsyodi/Downloads/aldisypu-labs-4036b.json)```