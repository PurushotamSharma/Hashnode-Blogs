---
title: "Directory Backup with Rotation"
datePublished: Wed Aug 02 2023 19:12:55 GMT+0000 (Coordinated Universal Time)
cuid: clku3v9pn000009kwgqwbh330
slug: directory-backup-with-rotation
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691003564645/6e2583ef-482d-4e73-9334-5019fdf82db9.png
tags: blogging, devops, backup, trainwithshubham, twsbashblazechallenge-trainwithshubham

---

## ¶ Introduction

📂🔄 Safeguarding Your Data: Unveiling the Magic of Directory Backup with Rotation! 🪄✨

Lost files? Never again! Dive into the world of Bash scripting as we unveil the ultimate secret to securing your precious data with style. 🛡️🔒 Join us on a journey of backup brilliance, where directories dance with rotation, and your files stay protected in a symphony of code. 🕺💃 Say goodbye to data disasters and hello to peace of mind! Let's learn the art of Bash backup wizardry together.

## ¶ Directory Backup with Rotation

Hey there! 👋 Imagine your computer is a treasure chest full of your important files and memories. Now, what if I told you there's a super cool way to create copies of that treasure chest (backup), and even spin it around like a DJ to keep things fresh (rotation)? 🎉📂

So, "Directory Backup with Rotation in Bash Script" is like having a magical spell that helps you make copies of your special files and folders (that's the directory part) using a smart script written in Bash (a fancy word for a type of computer language). And here's the fun part: it's like having a rotating stage for your treasure chest, so you always have the latest and greatest copy while still keeping some older versions, just in case! 🔄💼🪄

Imagine this: you're the director of a play, and your files are the actors. The script you create (using the magic of Bash) tells these actors to make copies of themselves regularly and step onto different stages. 🎭✨ Some stay on the main stage (the recent backup), while others go backstage (older backups), ready to shine again if needed.

In simpler words, it's a clever way to make sure your files are safe from accidents, like a knight in shining armor guarding your digital castle! 🏰🛡️ And all this happens with the power of a Bash script and a touch of digital wizardry. 🧙‍♂️🌟

So there you have it – Directory Backup with Rotation in Bash Script is like having a team of backup buddies who always have your back, ensuring your digital stuff is safe and sound, no matter what! 🤝💾 Ready to give it a try? Let's dive into the world of tech magic! 🚀🔮

## ¶ Challenge Description

Your task is to create a bash script that takes a directory path as a command-line argument and performs a backup of the directory. The script should create timestamped backup folders and copy all the files from the specified directory into the backup folder.

Additionally, the script should implement a rotation mechanism to keep only the last 3 backups. This means that if there are more than 3 backup folders, the oldest backup folders should be removed to ensure only the most recent backups are retained.

## ¶ backup\_with\_rotation.sh

```bash
#!/bin/bash

# Check if a directory path is provided as a command-line argument
if [ $# -ne 1 ]; then
    echo "Usage: $0 <directory_path>"
    exit 1
fi

# Directory to backup
source_dir="$1"

# Create a timestamp for the backup folder
timestamp=$(date +"%Y%m%d%H%M%S")
backup_dir="backup_$timestamp"

# Create the backup folder
mkdir "$backup_dir"

# Copy files from the source directory to the backup folder
cp -r "$source_dir"/* "$backup_dir"

# List all backup folders, sort them by date, and keep the last 3
backup_folders=($(ls -d backup_* | sort -r))
num_backups=${#backup_folders[@]}

# Check if there are more than 3 backups and remove the older ones
if [ $num_backups -gt 3 ]; then
    for ((i = 3; i < $num_backups; i++)); do
        rm -r "${backup_folders[i]}"
        echo "Removed backup: ${backup_folders[i]}"
    done
fi

echo "Backup completed successfully!"
```

Here's how the script works:

1. It checks if a directory path is provided as a command-line argument.
    
2. A timestamp is generated to create a unique backup folder.
    
3. The backup folder is created, and all files from the source directory are copied into it.
    
4. The script lists all backup folders, sorts them by date in reverse order, and counts the number of backups.
    
5. If there are more than 3 backups, it removes the older ones (keeping only the latest 3).
    
6. The script displays messages for each action taken.
    

To use the script, save it to a `.sh` file (e.g., `backup_script.sh`), make it executable (`chmod +x backup_script.sh`), and then run it with the source directory as an argument:

## ¶ Conclusion

🌟 Bravo, Tech Voyager! 🌟

You've just unlocked the secrets of "Directory Backup with Rotation" like a true digital magician! 🧙‍♂️💾 With your Bash script wand and a sprinkle of code enchantment, you've transformed data disasters into a thing of the past. 🚀🔮

Remember, just as heroes protect their kingdoms, your script shields your files, creating timely backups and gracefully dancing through rotation. 🏰💃✨ As you bid farewell to worries, embrace the magic of retaining only the freshest trio of backups, while older ones gracefully exit the stage. 🎭🔄

With each backup, you're painting a canvas of resilience and safeguarding memories for the future. 🎨🔒 So go forth, empowered one, and let your script be the guardian of digital treasures, keeping chaos at bay with every rotation and every backup. 🌌🌊

May your files be forever safe, and your tech adventures be ever thrilling! 🌟🚀🌈

Congratulations on completing Day 2 of the Bash Scripting Challenge! The challenge focuses on creating a backup script with rotation capabilities to manage multiple backups efficiently. Happy scripting and backing up!

<mark>Happy Learning&gt;&gt;&gt;</mark>

`"Your support and engagement mean the world to us! If you found these insights helpful, give us a thumbs up and let us know your thoughts in the comments below. Remember, your feedback fuels our passion to bring you more valuable content. Keep shining bright and stay tuned for more exciting reads! ✨👍💬"`