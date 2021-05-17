```
ubuntu@nic-jump-sofia:~/aviVmc$ govc tags.category.ls -json
[
  {
    "id": "urn:vmomi:InventoryServiceCategory:36b687bf-4df2-4bd2-8454-0a6f238c7971:GLOBAL",
    "name": "EasyAvi",
    "cardinality": "MULTIPLE",
    "associable_types": [
      "VirtualMachine"
    ]
  },
  {
    "id": "urn:vmomi:InventoryServiceCategory:6de20b20-c2be-4fac-aeb1-9593dc19c90c:GLOBAL",
    "name": "vSANDirectStorage",
    "cardinality": "MULTIPLE",
    "associable_types": [
      "Datastore"
    ]
  },
  {
    "id": "urn:vmomi:InventoryServiceCategory:93f23ec7-203d-4694-a0c3-eb63c2d4d105:GLOBAL",
    "name": "ColoredVMs",
    "description": "Managed by Terraform",
    "cardinality": "SINGLE",
    "associable_types": [
      "VirtualMachine"
    ]
  }
]
ubuntu@nic-jump-sofia:~/aviVmc$

ubuntu@nic-jump-sofia:~/aviVmc$ govc tags.ls -json
[
  {
    "id": "urn:vmomi:InventoryServiceTag:c4c818f7-8d0b-4ffe-ba6d-5b734cfad907:GLOBAL",
    "name": "60901a503a476bb06e1879d0",
    "category_id": "EasyAvi"
  },
  {
    "id": "urn:vmomi:InventoryServiceTag:6c262887-3c3f-41b7-90f1-699b200139a0:GLOBAL",
    "description": "Managed by Terraform",
    "name": "vSphere_tag",
    "category_id": "ColoredVMs"
  }
]
ubuntu@nic-jump-sofia:~/aviVmc$



ubuntu@nic-jump-sofia:~/aviVmc$ govc tags.attached.ls 60901a503a476bb06e1879d0 | xargs govc ls -L
/SDDC-Datacenter/vm/Avi-Controllers/EasyAvi-jump
/SDDC-Datacenter/vm/Avi-SE-Default-Group/EasyAvi-se-60901a503a476bb06e1879d0-ugxau



ubuntu@nic-jump-sofia:~/aviVmc$ govc tags.attached.ls 60901a503a476bb06e1879d0
VirtualMachine:vm-1081
VirtualMachine:vm-1086
ubuntu@nic-jump-sofia:~/aviVmc$
```