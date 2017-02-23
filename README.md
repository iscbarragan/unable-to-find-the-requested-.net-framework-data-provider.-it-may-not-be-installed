# unable-to-find-the-requested-.net-framework-data-provider.-it-may-not-be-installed
Posible solution for "unable to find the requested .net framework data provider. it may not be installed" when you try to connect to a database from Visual Studio 2012. That was my problem in the first time.

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
 
 machine.config you need to delete <DbProviderFactories /> 

<system.data>
    <DbProviderFactories>

<add name="Microsoft SQL Server Compact Data Provider" invariant="System.Data.SqlServerCe.3.5" description=".NET Framework Data Provider for Microsoft SQL Server Compact" type="System.Data.SqlServerCe.SqlCeProviderFactory, System.Data.SqlServerCe, Version=3.5.0.0, Culture=neutral, PublicKeyToken="/>
<add name="Microsoft SQL Server Compact Data Provider 4.0" invariant="System.Data.SqlServerCe.4.0" description=".NET Framework Data Provider for Microsoft SQL Server Compact" type="System.Data.SqlServerCe.SqlCeProviderFactory, System.Data.SqlServerCe, Version=4.0.0.0, Culture=neutral, PublicKeyToken=\"/>

    </DbProviderFactories> 
    <DbProviderFactories /> (delete this)
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
