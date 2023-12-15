---
title: "Day 2 of 
Bash Scripting Challenge 
- Interactive File and Directory Explorer"
datePublished: Wed Aug 02 2023 09:35:04 GMT+0000 (Coordinated Universal Time)
cuid: clktj84vl000f09l5hxoxc76f
slug: day-2-of-bash-scripting-challenge-interactive-file-and-directory-explorer
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690969125024/1463ea4b-2f7f-4482-8d0b-6c144ad3b673.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1690969151705/6c7c7a75-2795-4149-81b2-11b6be84dbc9.jpeg
tags: bash, devops, trainwithshubham, twsbashblazechallenge, twsbashblazechallenge-trainwithshubham

---

## [✍️](https://coolsymbol.com/copy/Writing_Hand_Emoji_Symbol_%E2%9C%8D%EF%B8%8F)Introduction

Welcome to Day 2 of the #TWSBashBlazeChallenge! The goal of today's task is to create an interactive Bash script that counts characters while looking through files and directories. We'll write a script called [explorer.sh](http://explorer.sh) that will let you browse through your files and folders in a fun and engaging way while also counting the characters you type in! Let's start with some magic from the Bash language!🪄🪄🪄

## [✍️](https://coolsymbol.com/copy/Writing_Hand_Emoji_Symbol_%E2%9C%8D%EF%B8%8F)Part: 1 File and Directory Exploration

Let's Explore files and Directories in Bash..

1. **Navigating Directories**: 🚀📁
    
    * `pwd`: Display the current directory.
        
    * `ls`: List files and directories.
        
    * `cd`: Change directory.
        
    
    🌟 Pro tip: Use `cd ..` to go up one level.
    
2. **Creating Stuff**: 🎉📝
    
    * `touch file.txt`: Create a new file named `file.txt`.
        
    * `mkdir new_dir`: Create a new directory named `new_dir`.
        
3. **Peek Inside**: 👀📄
    
    * `cat file.txt`: Display the contents of `file.txt`.
        
    * `less file.txt`: Display contents one screen at a time (use arrow keys to navigate, `q` to exit).
        
4. **Copying & Moving**: 📦🏃‍♂️
    
    * `cp source.txt destination/`: Copy `source.txt` to the `destination` folder.
        
    * `mv old.txt new_location/`: Move `old.txt` to `new_location`.
        
5. **Renaming & Deleting**: ✨🗑️
    
    * `mv old_name.txt new_name.txt`: Rename a file.
        
    * `rm file.txt`: Delete a file (be careful!).
        
6. **Wildcards**: 🌠🃏
    
    * `*`: Matches any characters (e.g., `*.txt` matches all `.txt` files).
        
    * `?`: Matches any single character (e.g., `file?.txt` matches `file1.txt`, `file2.txt`, etc.).
        
7. **Permissions**: 🔒👀
    
    * `ls -l`: List files with detailed information, including permissions.
        
    * `chmod`: Change file permissions (e.g., `chmod +x` [`script.sh`](http://script.sh) adds execute permission).
        
8. **Searching**: 🔍🕵️‍♀️
    
    * `grep pattern file.txt`: Search for a pattern in a file.
        
    * `grep -r pattern dir/`: Recursively search for a pattern in a directory.
        
9. **Hidden Treasures**: 🕵️‍♂️🔍
    
    * `ls -a`: List all files, including hidden ones (starting with `.`).
        
    * `ls -la`: List with detailed information, including hidden files.
        
10. **Shortcut Magic**: 🎩✨
    
    * `Tab`: Auto-complete file/folder names.
        
    * `Ctrl + C`: Interrupt a running command.
        
    * `Ctrl + D`: Exit the current shell.
        

The [explorer.sh](http://explorer.sh) script will display a friendly welcome message and list all the files and folders in the current path when it is launched without any command-line arguments. The script will print the name and size of each file and directory in a human-readable format (e.g., KB, MB, GB). We'll use the ls command along with the necessary arguments to achieve this. Let's check out the process!

## [✍️](https://coolsymbol.com/copy/Writing_Hand_Emoji_Symbol_%E2%9C%8D%EF%B8%8F)explorer.sh📂

```bash
#!/bin/bash

# Part 1: File and Directory Exploration

# Welcome message
echo "Welcome to the Interactive File and Directory Explorer! 🌟"

# Infinite loop until the user decides to exit
while true; do
    # Display files and directories in the current path using ls command with human-readable sizes
    echo "Files and Directories in the Current Path:"
    ls -lh

    # Ask the user to enter a line of text
    echo -n "Enter a line of text (Press Enter without text to exit): "

    # Read user input into the variable 'input'
    read input

    # Check if the user entered an empty string (i.e., pressed Enter without any text)
    if [[ -z "$input" ]]; then
        echo "Exiting the Interactive Explorer. Goodbye! 👋"
        break   # Exit the loop if the user entered an empty string
    else
        # Count the number of characters in the input and display the count
        char_count=${#input}
        echo "Character Count: $char_count"
    fi
done

# End of script
```

## [✍️](https://coolsymbol.com/copy/Writing_Hand_Emoji_Symbol_%E2%9C%8D%EF%B8%8F)Part:2 Character Counting

Let's dive into the world of character counting in Bash with a splash of emojis! 🧮📊

**1\. The** `wc` **Command**: 📜🔢

The `wc` command is your character-counting superhero! It stands for "word count," but it's versatile enough to count characters too.

```bash
 echo "Hello, world!" | wc -c
```

In this example, the `echo` command prints "Hello, world!" and the `wc -c` part counts the characters. It will output the number of characters in the text, including spaces and punctuation.

**2\. Counting in Files**: 📄🔤

You can also count characters in files using the `wc` command.

```bash
 wc -c my_file.txt
```

This command will tell you how many characters are in the file `my_file.txt`.

**3\. Ignoring Whitespace**: 🚀📝

Sometimes, you might want to ignore spaces, tabs, and newlines. You can do this using `tr` (translate) and `wc`.

```bash
echo "Hello,   how   are you?" | tr -d ' \t\n' | wc -c
```

Here, `tr -d ' \t\n'` removes spaces, tabs, and newlines, and then `wc -c` counts the remaining characters.

**4\. Emojis Counting**: 😄🔡

Emojis are characters too! Let's count them.

```bash
echo "🌟✨🚀" | wc -m
```

The `-m` flag in `wc` stands for "characters," which includes multi-byte characters like emojis.

**5\. Total Characters in Multiple Files**: 🗂️🔢

Want to know the total character count in multiple files? The `cat` command and `wc` can help.

```bash
cat file1.txt file2.txt | wc -c
```

This concatenates the contents of `file1.txt` and `file2.txt` and then counts the total characters.

**6\. Input from User**: 🙋‍♂️📥

You can even count characters from user input.

```bash
 read -p "Enter your text: " user_input
 echo $user_input | wc -c
```

Here, the user's input is read and stored in `user_input`, and then its character count is displayed.

So, there you have it! Character counting in Bash can be playful with emojis while helping you analyze text like a pro. 🎉🔠

## [✍️](https://coolsymbol.com/copy/Writing_Hand_Emoji_Symbol_%E2%9C%8D%EF%B8%8F)Input:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690967890945/ce4b4413-27c3-4135-9ee1-7904f9dbf05d.png align="center")

## [✍️](https://coolsymbol.com/copy/Writing_Hand_Emoji_Symbol_%E2%9C%8D%EF%B8%8F)Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690968083037/2f41e22b-63c2-4df3-8657-c963c8197507.png align="center")

### [✍️](https://coolsymbol.com/copy/Writing_Hand_Emoji_Symbol_%E2%9C%8D%EF%B8%8F)**Practical**

First, we create the Day 2 directory, then we use the touch command to create the script file ([explorer.sh](http://explorer.sh)), then we use the vim editor to write our script, and last we grant our file permission and execute it.

## [✍️](https://coolsymbol.com/copy/Writing_Hand_Emoji_Symbol_%E2%9C%8D%EF%B8%8F)Conclusion

### Congratulations! Day 2 of the #TWSBashBlazeChallenge is complete. The task is to create an interactive script that examines files and directories and counts characters using Command-Line Argument Parsing and Loops. Happy exploring and writing!

If you like this blog helpful then share it with your friends and give feedback through the comment section.

Reference:

[https://blog.prasadsuman.me/day-2-exploring-files-and-directories-with-bash-twsbashblazechallenge](https://blog.prasadsuman.me/day-2-exploring-files-and-directories-with-bash-twsbashblazechallenge)

[https://github.com/PurushotamSharma/BashBlaze-7-Days-of-Bash-Scripting-Challenge/blob/main/Challenges/Day\_2/day\_2.0\_explorer.md](https://github.com/PurushotamSharma/BashBlaze-7-Days-of-Bash-Scripting-Challenge/blob/main/Challenges/Day_2/day_2.0_explorer.md)

**<mark>Happy Learning...</mark>**