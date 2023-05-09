## misc.
```powershell
get-command                     #Gives list of commands from installed PoSh modules
get-verb                        #Gives list of cmdlet verbs
get-command -verb <verb>        #Gives list of commands that start with that <verb>
get-command -noun <noun>        #Gives list of commands that contain <noun>

cmdlet: c#
function: PoSh
Workflows: specialized function for automation
Application: ping, ipconfig

#PoSh Search Order Execution
#1. Aliases
#2. Functions
#3. Cmdlets
#4. Path Environment Commands

[] = parameters
<> = arguments

```
## get-help
```powershell

get-help - gives help about help

get-help <command> -- gives help about command

update-help -force -erroraction silentlyconinue -- force powershell to update help

get-help *<anything>* -- list docs related to string

get-help <command> - examples -- w/ examples
get-help <command> - detailed -- more info
get-help <command> - full -- help doc with everything offered
get-help <command> - online -- full help doc in browser window
get-help <command> - showwindow -- full help doc in searchable, scrollable window

```
### f5 runs script.
### f8 + highlight runs highlighted section.

## parameters
```powershell

get-childitem -path C:\windows -filter *.exe -recurse -name
-recurse == switch parameter(on/off)
positional == comes in a certain order
-erroraction silentlycontinue == 

```

## aliases
```powershell

get-alias -- gives list of all aliases
$Alias:<alias> -- tells you what the alias actually is
get-alias -definition <command> -- reverse search for aliases
set-alias edit notepad.exe

```

## objects/members
```powershell

get-member -inputobject <object> -- lists members of the object
<object> | get-member -- lists members of the output of the object

get-childitem C:\windows\system32 | where-object -Property extension -eq .dll | Select-Object -Property name | Get-Member
(get-childitem C:\windows\system32 | where-object -Property extension -eq .dll | Select-Object -Property name).name
(get-childitem C:\windows\system32 | where-object -Property extension -eq .dll | Select-Object -Property name).GetType() --- tels you what type it is (array)


```

## pipeline
```powershell

get-process | out-default -- 

command string | format-table -- table with default properties
command string | format-list -- list with default properties
command string | format-wide -- wide table with default properties
command string | format-custom -- custom format
command string | format-<style> -property <property>,<property>,<property> -- formatted output

format has to be the last thing in pipeline

```

## functions
```powershell

write-host goes line by line(cant sort)
wite-output goes through the pipeline(can sort)

```

## varriables
```powershell

nammed location in memmory that can store a value
get-varriable -- lists all variables
get-childitem varriable: -- lists all variables listed in PSDrive

        Python        BASH          PoSh
Inst    var           var           $var

call    var           $var          $var

$a,$b,$c=7,8,9
$a = 7
$b = 8
$c = 9

$a = $b = $c = 20
$a
$b
$c
all = 20

remove-variable <variable>

```

## test-path
```powershell

test-path <path> -- verifies path existsre

```

## automatic variables
```powershell

$args ----- array of declared parameters
$false ---- False
$true ----- True
$input ---- Enumerate all input passed to a function (iterate through everything) (through pipeline into a function)
$matches -- hashtable of current match for a 'match' comparison
$null ----- black hole
$profile -- string of default powershell profiles
$PWD ------ current working directory
$_   or  $PSItem -------- object in current pipeline

function <arg1> <arg2> <arg3>
function Make-Numbers{
$args[0]*2
$args[1]*3
}

```

## environmental variables
```powershell

get-childitem env: -- lists all env variables in env PSDrive

cd $env:HOMEDRIVE -- 

```
## variable types
```powershell

string ---- fixed length string of unicode chars
char ------ 16-bit unicode char
byte ------ 8-but unsigned char
int ------- 32-bit signed char
long ------ 64-bit signed char
single ---- 32-bit floating point num
double ---- 64-bit floating point num
float ----- 32-bit floating point num
datetime -- date & time
array ----- array
hashtable - hashtable

```

## typecasting
```powershell

[int]86.51
87

$x.gettype()

$var = read-host; [int]$var
converts string to int

```

## floats typecasted into integers round to the nearest even number 
