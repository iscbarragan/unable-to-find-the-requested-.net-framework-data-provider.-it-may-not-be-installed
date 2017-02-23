# unable-to-find-the-requested-.net-framework-data-provider.-it-may-not-be-installed
Posible solution for "unable to find the requested .net framework data provider. it may not be installed" when you try to connecto to a database from Visual Studio. That was my problem.

You need to check in the two versions files 

(version 2)

1.- Go to C:\Windows\Microsoft.NET\Framework\v2.0.50727\CONFIG and open the 3 files: 
    -machine
    -machine.config.comments
    -machine.config.default
    
Search the <DbProviderFactories /> and delete it from machine.config.default
 <system.data>
      <DbProviderFactories /> (delete this line)  
 </system.data>
 
 (version 4)
 
 2.- Go to C:\Windows\Microsoft.NET\Framework\v4.0.30319\Config  and open the 3 files:
    -machine
    -machine.config.comments
    -machine.config.default
 
 Search the <DbProviderFactories /> and delete it from machine.config.comments
 
 <system.data>
       <DbProviderFactories /> (delete this line) 
 </system.data>
 
 
 
 Good luck!
