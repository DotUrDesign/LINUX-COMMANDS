# LINUX-COMMANDS
LINUX COMMANDS

# full cache clear 
=> sudo sync && sudo sh -c 'echo 3 > /proc/sys/vm/drop_caches'

-- cpu usage and memory usage track
top

-- only postgresql cpu usage track
top -u postgres

-- Calculate the total memory usage percentage(%MEM) of all currently running processes in the LINUX s/m
ps aux --no-headers | awk '{sum += $4} END {print sum "%"}'

-- Calculate the total memory usage percentage(%MEM) of all postgres running processes in the LINUX s/m
ps aux --no-headers | awk '$1 == "postgres" {sum += $4} END {print sum "%"}'


-- displays the disk space usage of file systems
df -h

-- Opens a file in text-editor mode
vi smartrecondbcred.properties
    Follow-up => 1. edit something - i
                 2. search something - /
                 3. save and exit - :wq
                 4. exit without saving - :q!


-- Open a file in read-only mode
vi -R smartrecondbcred.properties

-- 




