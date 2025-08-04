# ip-allowlist-updater
A simple Python script to update allow-listed IPs based on a remove list.
# IP Allow List Updater

This Python script automates the process of updating an IP allow list by removing specified IP addresses from a file.

## 📂 Project Overview

At my organization, access to restricted content is controlled using an `allow_list.txt` file. This script removes IP addresses listed in a separate `remove_list.txt` file, ensuring only authorized addresses remain.

## 🚀 Features

- Reads and processes IP addresses from a file
- Compares allow list with remove list
- Outputs an updated allow list with unauthorized IPs removed
- Uses efficient file handling and list operations in Python

## 📄 How It Works

1. Reads `allow_list.txt` containing allowed IPs
2. Reads `remove_list.txt` containing IPs to revoke
3. Removes any matches
4. Rewrites the `allow_list.txt` file with updated entries

## 🔧 Sample Code

```python
with open("allow_list.txt", "r") as file:
    ip_addresses = file.read().split()

with open("remove_list.txt", "r") as file:
    remove_list = file.read().split()

for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)

with open("allow_list.txt", "w") as file:
    file.write("\n".join(ip_addresses))
