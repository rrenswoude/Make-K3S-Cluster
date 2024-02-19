With a Machiavelli twist we give you Robota

## 1. Adding repositories (create-k3s-cluster-playbook-generator)
1. In Left Navigator Menu click on Repositories
2. On top right click on the New Repository
3. Enter Name : create-k3s-cluster-playbook-generator
4. Enter Url or Path (SSh Http File Git)
5. Enter Branch: master
6. Enter Access Key

## 2. Creating users
1. In Left Navigator Menu click on Team
2. On top right click on the New Team Member button
3. select user and select role

## 3. Create Key Store (robota)
1. In Left Navigator Menu click on KeY Store
2. On top right click on the New Key button
3. enter name for key (robota)
4. select type(ssh) and enter credentials (credentials for ssh user robota)
5. We need aditional credentials for robota-root
5. Create credentails for robota-root
6. Type: Login Password

## 4. Create Environment (robota)
1. In Left Navigator Menu click on Enviroment
2. On top right click on the New Environment button
3. Enter name: robota
Add this to the Extra variables field
```
{
  "ansible_ssh_user": "robota"
}  
 
```
## 5. Create Inventory (inventory)
1. In Left Navigator Menu click on Inventory
2. On top right click on the New Inventory button
3. Enter inventory name : inventory
4. Select type (File)
5. Enter Path to Inventory file (/inventories/production/inventory.ini)

## 6. Creating task Template for create_k3s_primary_master_node.yml
1. In Left Navigator Menu click on Task Templates
2. On top right click on the New Template button
3. Enter Name : create_k3s_primary_master_node
4. Enter Descxription: create_k3s_primary_master_node
5. Enter Playbook Filename: create_k3s_primary_master_node.yml
6. Enter Inventory: inventory
7. Enter Repository: create-k3s-cluster-playbook-generator
8. Enter Environment: robota
9. Enter Vault Password: robota_root
10. Add Survey Variables : 
```
node_type
node_name
k3s_token
master_node_ip_address
```

## 7. create task templates for the other two playbooks
add the same procedure, values, and Survey Variables as above for playbooks:
1. create_k3s_other_master_node.yml
2. create_k3s_worker_node.yml


