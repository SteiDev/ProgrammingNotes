The virtual console can be accessed with **CTRL-ALT-F6** and exited with **CTRL-ALT-F7** on most Linux distributions.

Most commands look like:
```bash
command -options arguments
```
## Useful Commands Sorted By Function
### Executing Programs
#### Launch command with elevated privileges (sudo):
```bash
sudo (commands)
```
### Navigating System Files
#### Change directory to another address (cd):
```bash
cd (address)
```
##### Shortcuts
Change to home:
```bash
cd
```
Change to previous directory:
```bash
cd -
```
Change to home of a user:
```bash
cd ~(user_name)
```

#### Determine file type (file):
```bash
file (filename)
```
#### List directory contents (ls):
```bash
ls (dir_1) (dir_2) (dir_n)
```
Multiple files can be accessed at the same time by specifying the paths in the command

##### Options
| Name | Functionality                    |
| ---- | -------------------------------- |
| -a   | Shows hidden files               |
| -l   | Shows more details (long format) |


#### Print working directory (pwd):
```bash
pwd
```

#### View file contents (less):
```bash
less (filename)
```
## System File Operations
#### Copy file (cp):
```bash
cp (items) (location)
```

#### Make directory (mkdir):
```bash
mkdir (dir_name)
```

#### Move file (mv):
```bash
mv (filename) (location)
```

#### Remove file (rm):
```bash
rm (filename)
```
## Wildcards
- **\*** - matches any character
- **?** - matches a single character
- \[characters\] - matches any character in the brackets (that is a member of "characters")
- \[!characters\] - matches any character that is not in the brackets (that is not a member of "characters")
- \[:class:\] - matches any character that is a member of the specified class
### Commonly used classes
- \[:alnum:\] - matches any alphanumeric character
- \[:alpha:\] - matches any alphabetic character
- \[:digit:\] - matches any numeral
- \[:lower:\] - matches any lowercase character
- \[:upper:\] - matches any uppercase character