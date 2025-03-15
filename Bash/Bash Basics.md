The virtual console can be accessed with **CTRL-ALT-F6** and exited with **CTRL-ALT-F7** on most Linux distributions.

Most commands look like:
```bash
command -options arguments
```
## Useful commands
### Launch command with elevated privileges (sudo):
```bash
sudo # commands
```
### Print working directory (pwd):
```bash
pwd
```
#### Shortcuts
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
cd ~#user_name
```
### Change directory to another address (cd):
```bash
cd # address
```
### List directory contents (ls):
```bash
ls
```
Multiple files cand be accessed at the same time by specifying the paths in the command
Show hidden files:
```bash
ls -a
```
More details (long format):
```bash
ls -l
```
### Determine file type (file):
```bash
file # filename
```
### View file contents (less):
```bash
less # filename
```
### Copy file (cp):
```bash
cp # items location
```
### Move file (mv):
```bash
mv # filename location
```
### Remove file (rm):
```bash
rm # filename
```
### Make directory (mkdir):
```bash
mkdir # directoryname
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