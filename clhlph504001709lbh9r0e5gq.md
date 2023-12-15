---
title: "Day 3 Task: Basic Linux Commands"
datePublished: Sat May 13 2023 08:08:45 GMT+0000 (Coordinated Universal Time)
cuid: clhlph504001709lbh9r0e5gq
slug: day-3-task-basic-linux-commands
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1683965315929/6317b0d4-6626-4742-9643-0ab7e18f25f3.jpeg
tags: cloud, linux, learning, devops, trainwithshubham

---

Hello Everyone, Welcome to my new blog, Hope you all are doing Great.

So our day 3 Task is .

Basic Linux Commands:

### Task: What is the Linux command to

### **1. To view what's written in a file.**

The file name is hello.txt

To view the contents of the file **hello.txt**, you can use the following command:

```powershell
cat hello.txt
```

This will display the contents of the file **hello.txt** in the terminal. If the file is too large to fit on one screen, you can use the **more** or **less** command to view it one screenful at a time. For example:

```powershell
cat helllo.txt | more 
```

This will display the contents of the **hello.txt** file one page at a time, with instructions for navigating through the file. To exit from **more**, press **q**.

**2\. To change the access permissions of files.**

To change the access permissions of the file **hello.txt**, you can use the **chmod** command in the following format:

```powershell
chmod [options] mode hello.txt
```

Replace **mode** with the permissions you want to set on the file. Here are some examples:

1. To give read, write, and execute permissions to the owner, and no permissions to anyone else, you can use the following command:
    

```powershell
chmod 700 hello.txt 
```

1. To give read and write permissions to the owner and group, and no permissions to anyone else, you can use the following command:
    

```powershell
chmod 660 hello.txt 
```

1. To give read and write permissions to the owner, and read-only permissions to the group and others, you can use the following command:
    

```powershell
chmod 644 hello.txt 
```

You can also use the **chmod** command with options to modify permissions recursively, for directories and their contents, and to specify permissions for different users and groups.

**3\. To check which commands you have run till now.**

The Linux command to check the list of commands that you have run in the current session is **history**.

You can use it as follows:

```powershell
history 
```

This will display a list of the most recent commands you have executed in the terminal session, along with a line number. The commands are listed in reverse chronological order, with the most recent commands at the end of the list.

**4\. To remove a directory/ Folder.**

The **rmdir** command can only be used to remove empty directories. If you want to remove a directory and all its contents, you can use the **rm** command with the **\-r** (recursive) option. Here's how you can use the **rmdir** command to remove an empty directory:

```powershell
rmdir DevopsChallange
```

This command will only remove the directory if it is empty. If the directory contains any files or subdirectories, the command will fail. If you want to remove a non-empty directory and all its contents, you can use the following command:

```powershell
rm -r fDevopsChallange
```

This command will remove the directory and all its contents, including any files and subdirectories within it. Be careful when using the **rm** command with the **\-r** option, as it will permanently delete the files and directories without moving them to the Trash or Recycle Bin. Always double-check the directory name before executing this command to avoid accidentally deleting important data.

**5\. To create a fruits.txt file and to view the content.**

Linux commands to create a "fruits.txt" file and view its contents:

To create an empty "fruits.txt" file using the **touch** command:

```powershell
touch fruits.txt
```

To add some content to the "fruits.txt" file using the **echo** command:

```powershell
echo -e "Apple\nMango\nBanana\nCherry\nKiwi\nOrange\nGuava" > fruits.txt
```

This command will write the fruit names to the file, separated by newlines (**\\n**). The **\-e** option enables the interpretation of escape sequences like **\\n**.

To view the contents of the "fruits.txt" file using the **cat** command:

```powershell
cat fruits.txt 
```

This command will display the contents of the file in the terminal. The fruit names should be listed on separate lines.

**6\. Add content in devops.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.**

you can use the following commands:

```powershell
echo "Apple" > devops.txt 
echo "Mango" >> devops.txt 
echo "Banana" >> devops.txt 
echo "Cherry" >> devops.txt 
echo "Kiwi" >> devops.txt 
echo "Orange" >> devops.txt 
echo "Guava" >> devops.txt 
```

The first command creates a new file called **devops.txt** and writes the string "Apple" to it. The **\&gt;** symbol is used to redirect the output of the **echo** command to the file **devops.txt**. The second to seventh commands append the strings "Mango", "Banana", "Cherry", "Kiwi", "Orange", and "Guava" to the end of the file **devops.txt**, respectively. The **\&gt;&gt;** symbol is used to append the output of the **echo** command to the end of the file.

Now, if you run the **cat** command to display the contents of the **devops.txt** file, you will see:

```powershell
Apple 
Mango 
Banana 
Cherry 
Kiwi 
Orange
Guava 
```

This is the list of fruits written to the **devops.txt** file, with each fruit on a new line.

**7\. To Show only top three fruits from the file.**

To show only the top three fruits from the **devops.txt** file, you can use the **head** command with the **\-n** option. Here's how you can do it:

```powershell
head -n 3 devops.txt 
```

This command will display the first three lines of the **devops.txt** file, which correspond to the top three fruits in the list. The output should be:

```powershell
Apple 
Mango 
Banana 
```

These are the top three fruits in the **devops.txt** file.

**8\. To Show only bottom three fruits from the file.**

To show only the bottom three fruits from the **devops.txt** file, you can use the **tail** command with the **\-n** option. Here's how you can do it:

```powershell
tail -n 3 devops.txt 
```

This command will display the last three lines of the **devops.txt** file, which correspond to the bottom three fruits in the list. The output should be:

```powershell
Kiwi
Orange
Guava 
```

These are the bottom three fruits in the **devops.txt** file.

**9\. To create another file Colors.txt and to view the content.**

**To create a new file called Colors.txt** and view its contents, you can use the following commands:

```powershell
touch Colors.txt 
cat Colors.txt 
```

The **touch** command creates a new empty file called **Colors.txt**. The **cat** command is used to display the contents of the **Colors.txt** file, which should be empty at this point.

**10\. Add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey.**

To add the colors "Red", "Pink", "White", "Black", "Blue", "Orange", "Purple", and "Grey" to the **Colors.txt** file, you can use the following commands:

```powershell
echo "Red" > Colors.txt echo "Pink" >> Colors.txt echo "White" >> Colors.txt echo "Black" >> Colors.txt echo "Blue" >> Colors.txt echo "Orange" >> Colors.txt echo "Purple" >> Colors.txt echo "Grey" >> Colors.txt 
```

The first command writes the string "Red" to the **Colors.txt** file. The **\&gt;** symbol is used to redirect the output of the **echo** command to the file **Colors.txt**. The second to eighth commands append the strings "Pink", "White", "Black", "Blue", "Orange", "Purple", and "Grey" to the end of the file **Colors.txt**, respectively. The **\&gt;&gt;** symbol is used to append the output of the **echo** command to the end of the file.

If you run the **cat** command again to display the contents of the **Colors.txt** file, you will see:

```powershell
Red 
Pink 
White
Black 
Blue 
Orange 
Purple 
Grey 
```

This is the list of colors written to the **Colors.txt** file, with each color on a new line.

11\. To find the difference between fruits.txt and Colors.txt file.

To find the difference between the **fruits.txt** and **Colors.txt** files, you can use the **diff** command. Here's how you can do it:

```powershell
diff fruits.txt Colors.txt 
```

This command will display the differences between the two files, if any. If there are no differences, the command will not produce any output.

If there are differences between the two files, the output will show the lines that are different between the two files. The output will look something like this:

```powershell
1c
< Apple
---
> Red
3c3
< Banana
---
> White
5c5
< Orange
---
> Purple
6a7
> Grey

1
```

This output indicates that the first line in **fruits.txt** ("Apple") is different from the first line in **Colors.txt** ("Red"), the third line in **fruits.txt** ("Banana") is different from the third line in **Colors.txt** ("White"), the fifth line in **fruits.txt** ("Orange") is different from the fifth line in **Colors.txt** ("Purple"), and the **Colors.txt** file has an additional line ("Grey") that is not present in the **fruits.txt** file.

Thanks for reading the blog.

Happy Learing..