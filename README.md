# automatAccountwithbash

```
#!/bin/bash

read -p "Enter the username: " username

if id "$username" &>/dev/null; then
    echo "Error: User already exists."
    exit 1
fi

read -p "Enter the user's full name: " fullname

read -s -p "Enter the user's password: " password

useradd -m -c "$fullname" -s /bin/bash "$username"

echo "$username:$password" | chpasswd

echo "$username ALL=(ALL:ALL) ALL" >> /etc/sudoers

echo "User account created successfully." 
```
