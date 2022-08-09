# **ITSEC Notes**

## Tools
https://github.com/Cerbersec/Ares

https://github.com/cddmp/enum4linux-ng

https://github.com/0xsp-SRD/mortar

https://github.com/danielbohannon/Invoke-Obfuscation

https://github.com/aas-n/spraykatz


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

### Reformat usermames first.last@domain.com to last + first letter
```
while read LINE in; do
        EMAIL=`echo $LINE | awk -F\@ '{print $1}'`
        NAME=`echo $EMAIL | awk -F\. '{print $NF}'`
        CHAR1=`echo $LINE | cut -c1`
        echo ${NAME}${CHAR1}
done < emails.lst
```

### Get Ips from a file
```
egrep -o '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' list | sort | uniq > ips
```

## Nmap

### Useful Switches 
```
-p- all ports
--open only show open ports
-iL use a target list

Convert xml output to html files
&& xsltproc part1.xml -o part1.html 

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

## Notes
Identify Domain Controller
````
nslookup  
 type set type=all 
 _Idap._tcp.dc_msdcs."Domain_Name" 
 ````

# Initial Access
## Poisoning and Spoofing (LLMNR NBT-NS)
Responder
https://github.com/lgandx/Responder

Examples

``` responder -I eth0 ```

``` responder -I eth0 -A ``` Listen Only

``` responder -I eth0 -wF ``` WPAD
