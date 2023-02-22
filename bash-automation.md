# Linux Bash Automation
## Adding Multiple Users on Linux
first create bash file, example : user.sh

    nano user.sh

for example we add 100 users, user1-user100. Edit file user.sh

    for i in {1..100}
    do
    adduser user$i --disabled-password --gecos user$i
    passwd user$i <<< "P4$$w0rd"$'\n'"P4$$w0rd"
    done
    
give privilege to execute user.sh

    chmod +x user.sh
    
and run
    
    bash user.sh
 
---

## Create Multiple Bind9 Subdomains
first create bash file, example : domain.sh
    
    nano domain.sh
    
for example we create 100 domain with name user1-100, and use IP 192.168.1.1 & domain example.com

    for i in {1..100}
    do
    echo user$i 'IN   A     192.168.1.1' >> /var/cache/bind/db.domain
    echo '2 IN    PTR     'user$i'.example.com.' >> /var/cache/bind/db.ip
    done

give privilege to execute domain.sh

    chmod +x domain.sh
    
and run
    
    bash domain.sh

---
