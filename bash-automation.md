# Linux Bash Automation
## Create Multiple Bind9 Subdomains
first create bash file, example : domain.sh
    
    nano domain.sh
    
example we create 100 domain with name user1-100, and use IP 192.168.1.1 & domain example.com

    for i in {1..100}
    do
    echo user$i 'IN   A     192.168.1.1' >> /var/cache/bind/db.domain
    echo '2 IN    PTR     'user$i'.example.com.' >> /var/cache/bind/db.ip
    done

give privilege to execute domain.sh

    chmod +x domain.sh
    
and run
    
    bash domain.sh
