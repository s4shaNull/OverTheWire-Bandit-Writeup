# :shipit: OverTheWire: Bandit, Level 0-15 Writeup

<p align="center">
  <img width="833" height="455" src="https://user-images.githubusercontent.com/84661482/132093151-7b225882-2b7c-4973-8150-4df05617ea59.png">
</p>

## Table of Contents


## :open_book: Introduction

OverTheWire is a community that can help you to learn and practice security concepts in the form of fun-filled games. They offer lots of wargames to practice your skills.

![image](https://user-images.githubusercontent.com/84661482/132092828-c917b13e-0df0-4052-b7a7-a7a9d7162d8f.png)

The first set of challenges is named "Bandit," and it's more of a tutorial to the Linux CLI, with each level's goal being to discover the password to move to the next. 

![image](https://user-images.githubusercontent.com/84661482/132092898-322b815b-674e-4dd7-a457-e824d910ae43.png)

The follwing content is a comprehensive write-up of my solutions for this challenge (Level 0 - 15). Before looking at the answers, I recommend doing it yourself because you won't learn anything unless you try. My primary idea is to demonstrate you how I handled it and to compare your solutions to mine. 

## :triangular_flag_on_post: Bandit Level 0

### Problem Description:
Level 0 is a welcome gift to get you started with the real difficulties. 

![image](https://user-images.githubusercontent.com/84661482/132093444-428e2ad1-dba7-44ac-be13-ae2561b4ee94.png)

### Solution & Explanation:
To begin, you must understand how to use the secure shell (SSH) protocol to connect to the bandit.labs.overthewire.org server. If you're using Linux, you may access the server by running the following command: 

```
sasha@SecurityBox:~$ ssh bandit.labs.overthewire.org -l bandit0 -p 2220
```
If you're using Windows, though, you won't find an SSH client by default. While there are several great SSH clients available for use in Windows environments, I like PuTTY since it is straightforward and relatively compact. 

<p align="center">
  <img width="452" height="437" src="https://user-images.githubusercontent.com/84661482/132094175-36de91a1-df1b-413f-af47-54a7e660dcc5.png">
</p>

When you're finished, hit "Open," and you'll be able to access the bandit0 shell. 

![image](https://user-images.githubusercontent.com/84661482/132094368-4fb40674-9827-4514-ad0c-2d2dabbb62c6.png)

## :triangular_flag_on_post: Bandit Level 0 - 1

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132094626-39a1e512-5658-4feb-bd4f-187f34b17514.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132095287-b57a70c6-9da9-49d7-b866-5fdc4bb5535c.png)

### Explanation:
This level is also a straightforward giveaway. As suggested by the level's hint, run **ls** to examine the current directory, then **cat** the **readme** file to view its information. 

If you don't understand the meaning behind any of these commands. Well, try to read the manual pages! **man** is the name of the command that pulls up manpages. So you use **man** by doing this:

```
$ man [name of program you are interested in]
```
Here is the manpages of **ls** and **cat**:

![image](https://user-images.githubusercontent.com/84661482/132094920-0aff3cb2-39e4-4e06-8574-6f2fc68ceef1.png)
![image](https://user-images.githubusercontent.com/84661482/132094944-74dbbc26-2820-4743-8860-a39e2ac2a0c6.png)

### Summary
```
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme 
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
 ```
The password to level 1 box is **boJ9jbbUNNfktd78OOpsqOltutMc3MY1**

## :triangular_flag_on_post: Bandit Level 1 - 2

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132095632-36c26f4f-fb81-4d88-b24e-a99d61969ad7.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132095451-5e70e4bb-ee33-4120-b751-61495d4f9a88.png)

### Explanation:
To acquire the password for stage 2, we have to print the content of the file called – (a dash sign), as recommended by the hint.

If you just use the **cat** command to read and print the contents of the file called – (a dash sign), unfortunately, your terminal will become stuck. 

![image](https://user-images.githubusercontent.com/84661482/132095836-3a04ea80-ed4a-4e20-b2b6-a7a0bd326dc3.png)

When **cat** encounters the filename – (a dash symbol), it interprets it as a synonym for **STDIN**. You must supply the full path of the file rather than just the file name to avoid being regarded as an **STDIN** and your terminal getting nothing. 

### Summary
```
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```
The password to gain access to level 2 box is **CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9**

## :triangular_flag_on_post: Bandit Level 2 - 3

### Problem Description:
![image](https://user-images.githubusercontent.com/84661482/132096087-ff16cc31-aa39-4460-8923-a2ef74034e4f.png)

### Solution:
![image](https://user-images.githubusercontent.com/84661482/132096150-93de2a1d-86a4-44c0-949c-fb5989953c43.png)

### Explanation:
You'll see the "spaces in this filename" file after running a **ls** command to examine the files in the directory. You will encounter issues if you **cat** the file directly.

Either use a backslash before each space or write the full file name as a string. As an example: 
1. Adding backslash before each space:    
```
bandit2@bandit:~$ cat spaces\ in\ this\ filename
```
2. Adding double quote:
```
bandit2@bandit:~$ cat "spaces in this filename"
```
When can also use tab completion by pressing tab, which makes the program automatically fills in partially typed commands. 

### Summary
```
bandit2@bandit:~$ ls 
spaces in this filename
bandit2@bandit:~$ cat spaces\ in\ this\ filename 
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```
The password to gain access to level 3 box is **UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK**


