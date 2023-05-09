# Lab Report 3 - Command-line Options

For this lab report, I will be investigating the `find` command's options. I found all of the options I used in [this website](https://www.redhat.com/sysadmin/linux-find-command)

## Option 1: `-name`

First Example:
```
$ find ./technical -name "911report"
./technical/911report
```

In this example, the terminal is finding anything in the **technical** directory with the name "911report" and printing the path to the object found. 

___

Second Example:
```
$ find ./technical -name "chapter-1.txt"
./technical/911report/chapter-1.txt
```

In this example, the terminal is finding anything in the **technical** directory with the name "chapter-1.txt" and printing the path to the object found. 

___

This option for the `find` command could be very useful in looking for the path to a specific file we want to find, whether it is a normal file or directory.

___

## Option 2: `-type`

First Example:
```
$ find ./technical -type d
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```

In this example, the terminal is finding anything in the **technical** directory that is a directory and printing the path to the directories found.

___

Second Example:
```
$ find ./technical -name "Legal_Aid*.txt" -type f
./technical/government/Media/Legal_Aid_attorney.txt
./technical/government/Media/Legal_Aid_campaign.txt
./technical/government/Media/Legal_Aid_in_Clay_County.txt
./technical/government/Media/Legal_Aid_looks_to_legislators.txt
./technical/government/Media/Legal_Aid_Society.txt
```

In this example, the terminal is finding any regular file following the name pattern "Legal_Aid*.txt" in the **government** directory and printing the path to every file found.

___

This option for the `find` command can prove to be very useful in combination with other options to find a specific file based on its type. For example, this option can differentiate two files with the same name by their type.

___

## Option 3: `-iname`

First Example:
```
$ find ./technical -iname "*government*txt"
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
```

In this example, the terminal is finding any txt file in the **technical** directory whose name is approximately "government" and printing the path to every file found. 

___

Second Example:
```
$ find ./technical -iname "*PLOS*"
./technical/plos
```

In this example, the terminal is finding any file in the **technical** directory whose name is approximately "PLOS", regardless of case, and printing the path to every file found.

___

This option for the `find` command can be helpful in searching for a file when you do not remember the exact name of the file. Also, being able to specify the file type can also help narrow down the search further.

___

## Option 4: `-exec`

First Example:
```
$ find ./technical -name "chapter-2.txt" -exec grep claim {} \;
            He claimed it was more important for Muslims to kill Americans than to kill other
            Bin Ladin's Worldview Despite his claims to universal leadership, Bin Ladin offers an
            Three basic themes emerge from Qutb's writings. First, he claimed that the world was
                Quds al Arabi. One proclaimed "the formation of the Islamic Army for the Liberation
```

In this example, the terminal is finding the "chapter-2.txt" file in the **technical** directory, then executing `grep` for the word "claim" on the file found, and printing the lines containing the word "claim".

___

Second Example:
```
$ find ./technical -iname "*PrEFacE*txt" -exec grep aviation {} \;
                aviation, the role of congressional oversight and resource allocation, and other
            We learned that the institutions charged with protecting our borders, civil aviation,
```

In this example, the terminal is finding the txt file that is approximately named "PrEFacE", regardless of case, in the **technical** directory, then executing `grep` for the word "aviation" on the file found, and printing the lines containing the word "aviation".

___

This option for the `find` command can be helpful in using multiple bash commands in the terminal all in one line to shorten the commands needed.
