# Generate Warp for Team config using Ansible 


## How to use this 

Please create host inventory example 

```
all:
    hosts:
        srv1.domain.tld:
    vars:
        ansible_ssh_username: debian
        ansible_ssh_private_key_file: private_key.pem 

```

then create Vars files example: 

```
accesss_id: [CF-Access-Client-Id]
access_secret: [CF-Access-Client-Secret]
organization: [Your team organization subdomain]

```
you can get Client ID and Client Secret from this tutorial https://developers.cloudflare.com/cloudflare-one/identity/service-tokens/


next step run ansible-playbook command. for me I use this command 

```
$ ansible-playbook -i host_inventory_file -e "@variable_file.yaml" playbook.yaml
```
