---
title: "Day 3 of Bash Blaze Challenge
User Account Management"
datePublished: Tue Aug 08 2023 09:34:14 GMT+0000 (Coordinated Universal Time)
cuid: cll23u6pt000809mna6pfbevp
slug: day-3-of-bash-blaze-challenge-user-account-management
tags: linux, bash, devops, trainwithshubham, bashblaze-challange

---

## Introduction

In this challenge, you will create a bash script that provides options for managing user accounts on the system. The script should allow users to perform various user account-related tasks based on command-line arguments.

## User Account Management

So, you want to be the ruler of your system, managing user accounts like a true wizard? Well, grab your bash wand (keyboard) and let's dive into this enchanting adventure! 🧙‍♂️🔮

🚪 **Step 1: Open the Gates** 🚪 Imagine your system as a grand castle, and the gates to the castle are the terminal. To open these gates, type `bash` and press Enter. Abracadabra, you're in the mystical land of Bash! 🏰🔓

📜 **Step 2: Summoning Spells (Commands)** 📜 Now, let's conjure up some commands to manage user accounts:

1. **Creating a User**: To create a new user, use the spell `sudo adduser username`. Replace 'username' with the magical name you desire. 🧙‍♀️✨
    
2. **Changing Secrets (Password)**: To change a user's secret spell (password), use `sudo passwd username`. The castle's guardian dragon might ask you for permission. 🐉🔑
    
3. **Granting Powers (Adding to Groups)**: To grant special powers (add to a group), use `sudo usermod -aG groupname username`. Choose the group wisely, like the "Knights of Files" or "Wizards of Wheel". 🛡️🪄
    
4. **Banishing (Locking an Account)**: To temporarily banish an account, use `sudo usermod -L username`. Be careful, they might turn into a pumpkin! 🎃🔒
    
5. **Summoning Banished Souls (Unlocking)**: To bring back a banished soul, use `sudo usermod -U username`. They shall rise like a phoenix! 🦅🔓
    
6. **Unleash the Wrath (Deleting an Account)**: To bid farewell, use `sudo deluser username`. Poof! They're gone. Just like a puff of smoke! 💨👋
    

📦 **Step 3: Magical Artifacts (Options)** 📦 Each spell can be customized with powerful artifacts (options):

* `-m`: When creating a user, this artifact crafts a home castle for them. 🏠✨
    
* `-d`: In the creation spell, this artifact lets you set the date when the user's castle shall crumble. ⏳🏰
    
* `-s`: This artifact silences the castle guardian when changing secrets (passwords). Shh, no roaring! 🤫🔒
    

⚡ **Step 4: Magic Incantations (Examples)** ⚡

1. To summon a new sorcerer named Merlin with a magical castle: `sudo adduser Merlin -m`
    
2. To grant Merlin the power of the "Wizards of Wheel": `sudo usermod -aG wheel Merlin`
    
3. To temporarily imprison Merlin: `sudo usermod -L Merlin`
    
4. To release Merlin from the dungeon: `sudo usermod -U Merlin`
    
5. To banish and erase the mischievous sprite Puck: `sudo deluser Puck`
    

🌟 **Step 5: You're the Bash Sorcerer!** 🌟 With these spells and artifacts, you're now a true bash sorcerer, weaving the tapestry of user accounts in your kingdom. But remember, great power comes with great responsibility! Use your newfound knowledge wisely. 🧙‍♂️🌍✨

Now, go forth and conquer the realm of User Account Management in the bash command-line land! May your spells be error-free and your terminal always at your command! 🎩🔥🌟

So, I think you understand what User Account Management Do.So finally proced further for part 1 challenge..

### Part 1: Account Creation

### Task: 1

Implement an option `-c` or `--create` that allows the script to create a new user account. The script should prompt the user to enter the new username and password.

### Task: 2

Ensure that the script checks whether the username is available before creating the account. If the username already exists, display an appropriate message and exit gracefully.

### Task: 3

After creating the account, display a success message with the newly created username.

```bash
#!/bin/bash

# Function to check if a username already exists
username_exists() {
    if id "$1" &>/dev/null; then
        return 0 # Username exists
    else
        return 1 # Username does not exist
    fi
}

# Function to create a new user account
create_user_account() {
    read -p "Enter the new username: " username
    if username_exists "$username"; then
        echo "Username '$username' already exists. Please choose a different username."
        exit 1
    fi

    read -s -p "Enter the password: " password
    echo
    read -s -p "Confirm password: " confirm_password
    echo

    if [ "$password" != "$confirm_password" ]; then
        echo "Passwords do not match."
        exit 1
    fi

    sudo useradd -m "$username" &>/dev/null
    echo "User account '$username' created successfully."
}

# Main script
if [ "$1" == "-c" ] || [ "$1" == "--create" ]; then
    create_user_account
else
    echo "Usage: $0 [-c|--create]"
    echo "Option -c or --create: Create a new user account"
    exit 1
fi
```

## Part 2: Account Deletion

### Task: 1

Implement an option `-d` or `--delete` that allows the script to delete an existing user account. The script should prompt the user to enter the username of the account to be deleted.

### Task: 2

Ensure that the script checks whether the username exists before attempting to delete the account. If the username does not exist, display an appropriate message and exit gracefully.

### Task: 3

After successfully deleting the account, display a confirmation message with the deleted username.

```bash
#!/bin/bash

# Function to check if a username exists
username_exists() {
    if id "$1" &>/dev/null; then
        return 0 # Username exists
    else
        return 1 # Username does not exist
    fi
}

# Function to delete a user account
delete_user_account() {
    read -p "Enter the username to delete: " username
    if ! username_exists "$username"; then
        echo "Username '$username' does not exist."
        exit 1
    fi

    sudo userdel -r "$username" &>/dev/null
    echo "User account '$username' deleted successfully."
}
```

## Part 3: Password Reset

### Task:1

Implement an option `-r` or `--reset` that allows the script to reset the password of an existing user account. The script should prompt the user to enter the username and the new password.

### Task:2

Ensure that the script checks whether the username exists before attempting to reset the password. If the username does not exist, display an appropriate message and exit gracefully.

### Task:3

After resetting the password, display a success message with the username and the updated password.

```bash
#!/bin/bash

# Function to check if a username exists
username_exists() {
    if id "$1" &>/dev/null; then
        return 0 # Username exists
    else
        return 1 # Username does not exist
    fi
}

# Function to reset a user account password
reset_user_password() {
    read -p "Enter the username to reset password: " username
    if ! username_exists "$username"; then
        echo "Username '$username' does not exist."
        exit 1
    fi

    read -s -p "Enter the new password: " new_password
    echo
    read -s -p "Confirm new password: " confirm_new_password
    echo

    if [ "$new_password" != "$confirm_new_password" ]; then
        echo "Passwords do not match."
        exit 1
    fi

    echo "$username:$new_password" | sudo chpasswd
    echo "Password for user '$username' has been successfully updated."
}
```

## Part 4: List User Accounts

### Task: 1

Implement an option `-l` or `--list` that allows the script to list all user accounts on the system. The script should display the usernames and their corresponding user IDs (UID).

```bash
#!/bin/bash

# Function to list all user accounts
list_user_accounts() {
    echo "Listing all user accounts:"
    echo "---------------------------"
    awk -F':' '{ printf "Username: %s\tUID: %s\n", $1, $3 }' /etc/passwd
}
```

## Conclusion

🔐 **Unlocking the Secrets of User Account Management!** 🔑

And there you have it, intrepid adventurers of the digital realm! 🌐 We've journeyed through the enchanted forests of user accounts, learning how to wield the mighty bash script as our magical wand. 🧙‍♂️✨

In the grand castle of command lines, we discovered the power to create new knights and sorcerers with just a few keystrokes, using the `-c` or `--create` option. 🛡️🧙‍♀️

But beware! With great power comes great responsibility. Our trusty script was ever-vigilant, ensuring that no imposter usernames entered our domain. 🚫👀

And then, oh brave souls, we faced the dragons of forgotten passwords and dared to use the `-r` or `--reset` option! With a new password in hand, we could breathe life back into our accounts. 🐉🔑

But let us not forget the sorrows of those who have been banished. The `-d` or `--delete` option brought forth the winds of change, sweeping away the castles and memories of those who once roamed our digital kingdom. 🏰💨

Yet, it wasn't all battles and banishments. With a flick of `-l` or `--list`, we painted a tapestry of usernames and UIDs, illuminating the many inhabitants of our cyber domain. 🌌📜

As we set down our virtual swords and staves, let us remember that the world of user account management is a realm of balance. With our trusty script as our guide, we can summon new beings into existence, grant them power, and even say our farewells when needed. 🧚‍♀️🔮

So, fellow digital explorers, as you venture forth into the wilderness of system administration, remember the lessons of user account management. Keep your passwords strong, your usernames unique, and your bash script close at hand. 🌟🛡️

Until next time, may your keystrokes be error-free and your virtual gates well-guarded! 🌐⚔️🔒

  
<mark>Happy Learning</mark>