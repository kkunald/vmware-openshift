# vmware-openshift-mtv-ansible

**Requirements and Privileges
VMware Requirements:**
•	vCenter credentials with admin-level access to query and operate on folders, VMs, and datastores.
•	Ensure proper access to VMware REST APIs.

**OpenShift Requirements:**
•	An OpenShift cluster with Forklift MTV installed and properly configured.
•	A user with cluster-admin privileges or specific permissions to create and manage NetworkMap, StorageMap, and Plan resources.

**Network Firewall Ports Required
Open the following firewall ports:**

**1.	VMware vCenter**
o	Port 443: HTTPS (for vCenter API access)
**2.	OpenShift**
o	Port 6443: Kubernetes API server (for managing OpenShift resources)
o	Port 443 and 8443: OpenShift web console and APIs
o	Additional Ports: Depending on the specific configuration and the services being migrated, additional ports might be required for service communication.

**Here is how to use the playbooks(Individually):**

**Define the variables:**
Edit the vars/main.yml file and specify the appropriate values:

user_selected_vm_names: "VM1\nVM2"  # Enter the VM names separated by new lines
networkmap_name: "your-network-map-name"
storagemap_name: "your-storage-map-name"
plan_name: "your-plan-name"
warm_migration_choice: "cold"  # Choose 'warm' or 'cold'

**Execute the playbook:**

Use the Ansible Automation Platform or CLI to execute the playbook:
ansible-playbook playbooks/main.yml

