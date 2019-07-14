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
