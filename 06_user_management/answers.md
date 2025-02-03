1. 
    - `sudo useradd -m user1`
    - `sudo useradd -M user2`

2. 
    - `sudo passwd user1`
    - `sudo passwd user2`

3. `sudo passwd -l user2`

4. `sudo usermod -s /bin/bash user1`

5. 
```bash
    sudo groupadd developers
    sudo usermod -g developers user1
```

6. `sudo usermod -l archived_user user2`

7. 
```bash
    sudo userdel -r user1
    sudo userdel user2
    sudo groupdel developers
    sudo groupdel user1
```
