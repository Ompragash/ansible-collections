# Collections

## What is collection?

A Collection is new distribution format to package and deliver all types of Ansible content. It is introduced in Ansible v2.8+ as a tech preview feature.

## Requirements

- Ansible 2.8+
- Mazer (It is a new command-line tool for managing Ansible content)

## Collection Data Structure

```
collection_name/
├── README.md
├── galaxy.yml
├── plugins
│   ├─ modules/
│   ├─ module_utils/
│   ├─ inventory/
│   ├─ lookup/
│   └─ callback/
├── tests/
├── playbooks/
└── roles/
```
More details at [here](https://docs.ansible.com/ansible/devel/collections_tech_preview.html#collection-structure).

# Create, Build and Upload Collections

## Step 1: Creating Collection

- Create a directory with the name same as [Galaxy Namespace name](https://galaxy.ansible.com/docs/contributing/namespaces.html#galaxy-namespaces)

```
# mkdir namespace && cd namespace
```
- Create another directory with required name inside `namespace` directory and this will be the `Collection` directory.

```
# mkdir collection_name && collection_name
```

***NOTE:*** Namespace and Collection name may only contain alphanumeric characters and underscores. Additionally the namespace cannot start with underscores or numbers and cannot contain consecutive underscores.
