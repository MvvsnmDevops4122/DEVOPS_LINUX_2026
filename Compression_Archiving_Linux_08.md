# 📦 Compression and Archiving in Linux

---

## 🗜️ zip and unzip

**Used to compress and extract directories or files.**

| Command | Description |
|----------|-------------|
| `zip -r ansible.zip Ansible/` | Compress a directory recursively into a ZIP file |
| `unzip ansible.zip` | Extract the contents of a ZIP file |

> 📘 **Note:**  
> The `-r` option in `zip` stands for **recursive**, meaning it includes all subdirectories and files.

---

## 📁 tar — Archive Files and Directories

**`tar`** is commonly used to create and extract archive files.

| Command | Description |
|----------|-------------|
| `tar -cvf ansible.tar Ansible` | Create an archive file |
| `tar -xvf ansible.tar` | Extract an archive file |

> 🔹 **Options Explained:**  
> - `c` → Create an archive  
> - `x` → Extract from an archive  
> - `v` → Verbose mode (shows progress)  
> - `f` → File name to create or extract  

---

## 🔍 Working with Compressed Archives

| Command | Description |
|----------|-------------|
| `zgrep <pattern> file.gz` | Search for text inside a compressed file |
| `zcat file.gz` | Display contents of a compressed file without extracting |

---

## 🧩 Additional Tips

- To create a **compressed tarball**:
  ```bash
  tar -czvf ansible.tar.gz Ansible/
````

(`z` = gzip compression)

* To extract a **.tar.gz** file:

  ```bash
  tar -xzvf ansible.tar.gz
  ```

* To view files inside a tar archive without extracting:

  ```bash
  tar -tvf ansible.tar
  ```

---

✅ **Quick Example**

```bash
# 1. Compress the Ansible directory
zip -r ansible.zip Ansible/

# 2. Extract it
unzip ansible.zip

# 3. Create a tar archive
tar -cvf ansible.tar Ansible/

# 4. Extract it
tar -xvf ansible.tar

# 5. Create a compressed tarball
tar -czvf ansible.tar.gz Ansible/

# 6. Search inside a gzipped file
zgrep "hosts" ansible.tar.gz
```

---

📘 **Summary**

| Tool               | Purpose                          | Common Commands        |
| ------------------ | -------------------------------- | ---------------------- |
| **zip/unzip**      | Compress and extract ZIP files   | `zip -r`, `unzip`      |
| **tar**            | Archive files/directories        | `tar -cvf`, `tar -xvf` |
| **gzip utilities** | Work with `.gz` compressed files | `zcat`, `zgrep`        |
