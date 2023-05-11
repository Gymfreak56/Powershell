## Day 2 Review
```powershell

$hashtable = [ordered]@{


}

```

## Powershell Special Chars
```powershell

`n -- Escape 'n' for a newline
`t -- tab
`' -- escapes single quote
`" -- escapes double quote

$test1 = "One Terabyte is $(1TB/1GB) Gigabytes"
One Terabyte is 1024 Gigabytes

```

## String formatting
```powershell

$var = 6
$var2 = 43
$sum = $var1 + $var2
 
"{0} + {1} + {2}" -f $var1, $var2, $sum
6  43 = 49
 
"{0:n3}" -f 123.45678
123.457
 
"{0:d5}" -f 123
00123
 
get-service | select-object -first 10 | foreach-object{"The Service {0} is called '{1}': {2}" -f $_.name, $_.DisplayName, $_.Status

```
## (STRING MANIPULATION -join, -split, and -replace USE REGEX)

## -replace/.replace
```powershell

Hello John" -replace "John", "World"
 Hello World
 
"Server1, Server2,Server3.Server4" -replace '[\.,]', ";"\
"Server1;Server2;Server3;Server4"
'[      Jon         Bon       Doe     ]' -replace '\s+', ' '
[ John Bon Doe ]

```

## -split/.split
```powershell

$profile gives you a string of the path to your profile -- makes it an array of strings
($prifile -split "\\")[0] -- makes it an array of strings
C:

$ip = "8.8.8.8"
[int]($ip.split('\.')[0]) -lt 9
True

```

## -join/.join
```powershell

"cat","dog" -join ":"
cat:dog
"cat","dog" -join ""
catdog

```

## -as
```powershell

"8.8.8.8" -as [IPAddress]
8.8.8.8
"12/18/1963" -as [DateTime]
{datetime}
"808" -as [int]
808

("12/18/1963" -as [DateTime]).DayOfWeek

"256.255.255.255" -as [IPAddress]
**nothing**

if ($ip -as [IPAddress]){ ----- easy input validation
	"This is an IP"
}

```

## MISC.
```powershell

("8.8.8.8").replace(".","/")
8/8/8/8

("America").StartsWith("A") -- regex
("America").EndsWith("ca") -- regex
().toupper -- all capital letters
().lower -- all lowercase letters

```

## REGEX
```powershell

Regex
* -- Any (0-1000000000.....)
? -- 0 or 1
+ -- 1-100000000000000000000...
{} -- any number ({0,10} -- 0-10)({n,} -- atleast n times)
^ -- beginning of line
$ -- end of line
\b -- word boundary(white space)
papaya😍️🤤️

```

## Functions
```powershell

function <name> {
	param(
		[switch]
		<param variable>
	)

}

function do-switch {
	param(
		[switch]
		$doswitch
	)
	
	if ($doswitch) {
		"Switch is on"
	}
	else {
		"Switch is off"
	}
}

function mandatory {
	param(
		[parameter(mandatory=$True)]
		$name
	)
	"your name is $name"
}
[math]::floor == #of whole cakes you can buy

```
## cmdletbinding
```powershell

treat a function like a cmdlet

```
## 
```powershell

function bare-bones {
	Begin {
		<code(EX. Variables)>
	}
	Process {
		<code(EX. What you want to happen)(If passed an array it will iterate through the array)>
	}
	End {
		<code(EX. Obtain output)>
	}
}

```
## 
```powershell



```
## 
```powershell



```
## 
```powershell



```
## 
```powershell



```
## 
```powershell



```
## 
```powershell



```
## 
```powershell



```
