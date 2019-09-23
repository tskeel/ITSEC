# ITSEC
ITSEC Notes

Powershell Ping a List of Computers, from Computers.txt

```$ServerName = Get-Content "c:\Computers.txt"  
  
foreach ($Server in $ServerName) {  
  
        if (test-Connection -ComputerName $Server -Count 2 -Quiet ) {   
          
            "$Server is Pinging "  
          
                    } else  
                      
                    {"$Server not pinging"  
              
                    }      
          
}
'''
