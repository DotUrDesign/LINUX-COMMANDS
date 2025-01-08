# Linux Commands Cheat Sheet

This repository contains a collection of useful Linux commands for system monitoring, file manipulation, and process management.

## 1. Cache Management

- **Clear the system cache:**

    ```bash
    sudo sync && sudo sh -c 'echo 3 > /proc/sys/vm/drop_caches'
    ```

    This command will clear the page cache, dentries, and inodes to free up memory.

## 2. Monitoring System Usage

- **Track overall CPU and memory usage:**

    ```bash
    top
    ```

    This command opens the interactive `top` tool to monitor system performance, including CPU and memory usage.

- **Track CPU usage for PostgreSQL processes:**

    ```bash
    top -u postgres
    ```

    This command will show the CPU usage of PostgreSQL-related processes only.

- **Calculate total memory usage percentage for all processes:**

    ```bash
    ps aux --no-headers | awk '{sum += $4} END {print sum "%"}'
    ```

    This command sums up the `%MEM` usage of all currently running processes.

- **Calculate total memory usage percentage for PostgreSQL processes:**

    ```bash
    ps aux --no-headers | awk '$1 == "postgres" {sum += $4} END {print sum "%"}'
    ```

    This command calculates the total memory usage percentage for all PostgreSQL processes.

## 3. Disk Usage

- **Display disk space usage for file systems:**

    ```bash
    df -h
    ```

    This command shows disk space usage in a human-readable format.

## 4. File Operations

- **Open a file in `vi` text editor:**

    ```bash
    vi smartrecondbcred.properties
    ```

    Basic operations in `vi`:
    - **Edit**: Press `i` to enter insert mode.
    - **Search**: Press `/` and type the search term.
    - **Save and exit**: Press `:wq`.
    - **Exit without saving**: Press `:q!`.

- **Open a file in read-only mode in `vi`:**

    ```bash
    vi -R smartrecondbcred.properties
    ```

    This opens the file in read-only mode to prevent accidental modifications.
