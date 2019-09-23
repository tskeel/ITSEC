**ITSEC Notes

Powershell

Ping a List of Computers, from Computers.txt

```
$ServerName = Get-Content "c:\Computers.txt"  
  
foreach ($Server in $ServerName) {  
  
        if (test-Connection -ComputerName $Server -Count 2 -Quiet ) {   
          
            "$Server is Pinging "  
          
                    } else  
                      
                    {"$Server not pinging"  
              
                    }      
          
}
```

Get IPv4 Address from a List
```
$Servername = Get-Content "C:\Computers.txt" 

ForEach ($Server in $Servername) {

 (Get-ADComputer -Properties IPv4Address).IPv4Address

 }
 ```

Unix Commands

Print/Split Certain Columns, Space delimited -F ' ' / Column 1 $1  

```
awk -F ' ' '{print $1}' Macs.txt > MacsNamesOnly.txt
```


