## scriptblock
```powershell

$myblock = { get-service | format table Name, Status } -- defines a scriptblock

& $myblock --- runs scriptblock

get-service | Get-Member

get-service | Sort-Object -Property Status -- sorts output by status

Get-NetTCPConnection | Sort-Object -Property State | Format-Table -Property state, LocalAddress, localport -- sorts output by state and only displays state, address, and port

Get-ChildItem | Group-Object {$_.Length -lt 1KB} -- returns files that are less than 1kb

([int]('1','7','10','8','2','3' | sort-object -property {[int]$_})[1]).gettype() --- returns an int

Get-Process | Select-Object -property ProcessName, ID -- only shows processname and id

Get-Service | Select-Object -ExpandProperty DisplayName -- expands display name to see all info (CAN ONLY EXPAND 1 PROPERTY)



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

