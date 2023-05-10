## scriptblock
```PowerShell

$myblock = { get-service | format table Name, Status } -- defines a scriptblock

& $myblock --- runs scriptblock

```

## Sort-Object
```powershell

get-service | Get-Member

get-service | Sort-Object -Property Status -- sorts output by status

Get-NetTCPConnection | Sort-Object -Property State | Format-Table -Property state, LocalAddress, localport -- sorts output by state and only displays state, address, and port

([int]('1','7','10','8','2','3' | sort-object -property {[int]$_})[1]).gettype() --- returns an int

1,2,3,3,2,1,1,2,3,3,2,1 | sort-object | get-unique -- sorts it numerically and only grab unique instances (Have to sort first)

```

## Group-Object
```powershell

Get-ChildItem | Group-Object {$_.Length -lt 1KB} -- returns files that are less than 1kb

```

## Select-Object
```powershell

Get-Process | Select-Object -property ProcessName, ID -- only shows processname and id

Get-Service | Select-Object -ExpandProperty DisplayName -- expands display name to see all info (CAN ONLY EXPAND 1 PROPERTY)

```

## Where-Object
```powershell

Get-Service | Where-Object {$_.Status -eq "Running"} -- only grabs the running services (when grabbing stuff from the pipeline use {} )

Get-process | Where-Object {$_.Company -like "micro*"} | format-table Name, Description, Company -- grabs only processes owned by microsoft and only display name, description, and company

```

## Measure-Object
```powershell

get-childitem | measure-object Length -average -max -min -sum


```

## .count
```powershell

(get-childitem).count -- counts how many files and directories are in specified directory

```

## Custom Objects
```powershell

"sussssssss" > test.txt

$before = get-childitem

"42" > test.txt

$after = get-childitem 

compare-object $before $after -property Length, Name


$MyTruck = new-object Object

add-member -membertype noteproperty -name color -value red -inputobject $MyTruck

add-member -inputobject $MyTruck Noteproperty Model "F-150 Raptor"

$MyTruck.model
F-150 Raptor

add-member -membertype scriptmethod -inputobject $MyTruck -name Drive -value { "Going on a roadtrip" }
$MyTruck.Drive()
Going on a roadtrip

```

## PSDrive / PSProvider
```powershell

Get-PSProvider

New-PSDrive -Name HKU -PSProvider Regestry -Root HKEY_USERS

New-PSDrive -Name Z -PSProvider FileSystem -Root \\live.sysinternals.com\tools

```

## Conditions / Compirison operators
```powershell

-eq, -ieq, -ceq
equals

-like, -ilike, -clike
string matches wildcard pattern

-notlike, -inotlike, -cnotlike
string does not match wildcard pattern

-match, -imatch, -cmatch
string matches regex pattern

-notmatch, -inotmatch, -cnotmatch
string does not match regex pattern

-replace, -ireplace, -creplace
replaces strings matching a regex pattern

-contains
contains (use for a collection of information)

-in
returns true when value is contained within a collection

-notin
value is not in a collection

1,2,3 -eq 2
2


```

## Hash Table
```powershell

$soldier = [PSCustomObject]@{
  "FirstName"   =   "Joe"
}


$mylist = @{First = "John"; Last = "Doe"; Mid = "Bon"; Age = 35}
$mylist.Last
$mylist["First", "Mid", "Last"]
$mylist.keys
$mylist.values
$mylist.date = Get-date
$mylist["Location"] = "Germany"
$mylist.Remove("Date")

```

## Switches
```powershell

$fruit = "b"
switch($fruit){
  a { "apple" }
  b { "banana" }
  c { "cranberry" }
  default { "Nobody cares" }
}
  
```

## For Each Loop
```powershell

$nums = 1,2,3,4,5
$nums | foreach-object {$_ * 2}

```

## while
```powershell



```

## do while
```powershell

do {


} while ()

```

## do until
```powershell

do {


}until()

```

## for 
```powershell

for($num = 1; $num -le 3; $num++){$num}

for($i = 0; $i -le 255; $i++) {
  write-host 192.168.0.$i
}

```

## Array
```powershell

(get-process)[0]
(get-process)[0..9] -- first 10

$array2 = "World", "hello", 5, 10, (Get-Date)
$array2[-1] -- last item
$array2[0,2,4]

$array = (1..5)
[array]

jagggedarrays == nested arrays
$array[0][2][2] -- how to access arrays in arrays


MULTIDIMENSIONAL ARRAYS

$TargetingArray = @(
    (35.7219, 51.3347, "Tehran"), 
    (), 
    ()
)

```

## Powershell Scripts 
```powershell

.\<scriptname>
.ps1 extension

```

## strings
```powershell

@('boom') * 20 --- newlines after each boom
('boom') * 20 ---- boom smashed together 20 times

```

## 
```powershell



```
