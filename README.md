# **ITSEC Notes**

## Powershell

### Ping a List of Computers

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

### Get IPv4 Address from a List
```
$Servername = Get-Content "C:\Computers.txt" 

ForEach ($Server in $Servername) {

 (Get-ADComputer -Properties IPv4Address).IPv4Address

 }
 ```

## Unix Commands

### Print/Split Certain Columns, Space delimited -F ' ' / Column 1 $1  

```
awk -F ' ' '{print $1}' Macs.txt > MacsNamesOnly.txt
```

## Nmap

### Useful Switches 
```
-p- all ports
--open only show open ports
-iL use a target list
```

## Metasploit

### Install Metasploit
````
curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall && chmod 755 msfinstall && ./msfinstall
````
