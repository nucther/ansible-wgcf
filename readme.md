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
cf_api_token: [ Clouflare API Token with permission Access: Service Tokens:Edit, Zero Trust:Read ]
organization_id: [ Your organiation id, can grab from team url ]
organization_name: [Your team organization subdomain]

```

you can generate cloudflare api token from here https://dash.cloudflare.com/profile/api-tokens

next step run ansible-playbook command. for me I use this command 

```
$ ansible-playbook -i host_inventory_file -e "@variable_file.yaml" playbook.yaml
```
