# 📚 Linux Commands Cheat Sheet  

A collection of commonly used Linux commands for system management, monitoring, and basic file operations.  

---

## 🚀 **1. Cache Management**  
- **Clear the system cache:**  
    ```bash
    sudo sync && sudo sh -c 'echo 3 > /proc/sys/vm/drop_caches'
    ```  
    Clears page cache, dentries, and inodes to free memory.  

---

## 📊 **2. System Monitoring**  
- **Track overall CPU and memory usage:**  
    ```bash
    top
    ```  
    Displays real-time CPU and memory usage.  

- **Track PostgreSQL CPU usage:**  
    ```bash
    top -u postgres
    ```  
    Displays CPU usage specifically for PostgreSQL processes.  

- **Calculate total memory usage (%MEM) of all processes:**  
    ```bash
    ps aux --no-headers | awk '{sum += $4} END {print sum "%"}'
    ```  

- **Calculate total memory usage (%MEM) of PostgreSQL processes:**  
    ```bash
    ps aux --no-headers | awk '$1 == "postgres" {sum += $4} END {print sum "%"}'
    ```  

- **Check memory-related details:**  
    ```bash
    free -h
    free -m
    top
    ```  

---

## 💾 **3. Disk and File Operations**  
- **Display disk space usage and availability:**  
    ```bash
    df -h
    ```  

- **Get the number of files starting with 'output' in the current directory:**  
    ```bash
    find . -type f -name 'output*' | wc -l
    ```  

- **Get the current working directory:**  
    ```bash
    pwd
    ```  

- **Delete a file:**  
    ```bash
    rm -rf output.txt
    ```  

- **Delete a folder:**  
    ```bash
    rm -r [folder]
    ```  

- **Copy a file to a destination directory:**  
    ```bash
    cp [file_name] [destination_directory_path]
    ```  

- **Move a file to a destination directory:**  
    ```bash
    mv [file_name] [destination_directory_path]
    ```  
    **Difference between `cp` and `mv`:**  
    - `cp`: Creates a duplicate copy at the destination.  
    - `mv`: Moves the original file to the destination.  

---

## 📝 **4. Text Editing (vi Editor)**  
- **Open a file in text editor mode:**  
    ```bash
    vi smartrecondbcred.properties
    ```  
    Basic Commands:  
    - **Edit:** Press `i` to enter insert mode.  
    - **Search:** Press `/` and type the search term.  
    - **Save and Exit:** Press `:wq`.  
    - **Exit without saving:** Press `:q!`.  

- **Open a file in read-only mode:**  
    ```bash
    vi -R smartrecondbcred.properties
    ```  

---

## 🐘 **5. PostgreSQL Management**  
- **Restart PostgreSQL service:**  
    ```bash
    sudo systemctl restart postgresql.service
    ```  

- **Check the status of PostgreSQL service:**  
    ```bash
    systemctl status postgresql.service
    ```  

- **List active PostgreSQL services:**  
    ```bash
    systemctl list-units --type=service | grep postgresql
    ```  

- **List all PostgreSQL services (active + inactive):**  
    ```bash
    systemctl list-units --type=service --all | grep postgresql
    ```  

---

## ☕ **6. Java (JDK) Management**  
- **Install Java JDK:**  
    ```bash
    sudo yum install java-11-openjdk-devel
    ```  

- **Check Java version:**  
    ```bash
    java --version
    ```  

- **Switch Java version:**  
    ```bash
    sudo update-alternatives --config java
    ```  

- **Set JAVA_HOME environment variable:**  
    ```bash
    export JAVA_HOME=/usr/lib/jvm/java-17-openjdk
    export PATH=$JAVA_HOME/bin:$PATH
    source /etc/profile
    ```  

- **Check JAVA_HOME:**  
    ```bash
    echo $JAVA_HOME
    ```  

---

## 🔍 **7. Process Management**  
- **Check active Tomcat processes:**  
    ```bash
    ps -ef | grep tomcat
    ```  

- **Kill all Tomcat processes:**  
    ```bash
    pkill -f tomcat
    ```  

---

## 🖥️ **8. System Information**  
- **Get the OS name:**  
    ```bash
    uname -s
    ```  

- **Get detailed OS information:**  
    ```bash
    cat /etc/os-release
    ```  

---

### ✅ **Tips for Better Productivity:**  
- Always verify commands before executing on a production server.  
- Use `man [command]` to view detailed documentation for a specific command.  
- Keep a backup of important files before running destructive commands like `rm`.  

---

🎯 **Happy Command-Lining!** 🚀  
