---
title: Sysprep un disco duro virtual (ejemplo de BizTalk Server) con el servidor BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35f0146d-60ed-4265-983a-0e3665ef2ae4
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc6ec29ece503f324758cdc08a6ff1351c066af4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="sysprep-a-biztalk-server-vhd-biztalk-server-sample"></a>Sysprep de un VHD de BizTalk Server (ejemplo de BizTalk Server)
Sysprep crea una instantánea de una máquina virtual con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalado, para una implementación rápida en otras máquinas virtuales.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de usar Sysprep, debe tener algunos conocimientos sobre el uso de máquinas virtuales con Hyper-V. También debe tener una máquina virtual con una instalación típica y limpia de BizTalk Server y todos sus requisitos previos.  
  
 Sysprep se ejecuta en Windows Server 2008 y Windows Vista con SP1.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Sysprep crea un VHD de una instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (incluido el sistema operativo y todos sus requisitos previos) para una implementación rápida en otras máquinas virtuales. Una imagen creada mediante Sysprep elegirá un nombre de equipo nuevo para unirse al dominio la primera vez que se inicie. Para que BizTalk Server se ejecute correctamente, es necesario actualizar las distintas instancias del nombre de equipo que se han almacenado en el registro y las bases de datos.  
  
 En este documento se da por supuesto que BizTalk Server está configurado para ejecutarse en un único equipo y se muestra cómo actualizar otras instancias del nombre de equipo con el mismo nombre.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  
  
 \<*Ejemplos de ruta de acceso*\>\Admin\Sysprep\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
> [!NOTE]
>  Los archivos .vbs y .cmd de la tabla siguiente están todos automatizados en los archivos de respuesta de Sysprep (Sysprep.xml y SetupCompletecmd.txt), y solo se enumeran como referencia. Si necesita ejecutar estos scripts manualmente, hágalo en el orden en que aparecen en la tabla.  
  
|Archivo|Description|  
|----------|-----------------|  
|Sysprep.xml|Archivo de respuesta|  
|SetupCompletecmd.txt|Archivo de respuesta|  
|ReplaceMachineName.vbs|Propósito: Abre un archivo y reemplaza todas las instancias de una cadena determinada con el nombre del equipo actual. Sirve para preparar los demás archivos de script y xml, así como para actualizar bm.exe.config.<br /><br /> Uso: ReplaceMachineName.vbs \<archivo para abrir\> \<cadena para reemplazar\>|  
|UpdateRegistry.vbs|Propósito: Actualiza el nombre de equipo almacenado en la configuración del registro de BizTalk.<br /><br /> Uso: UpdateRegistry.vbs \<UpdateInfo.xml\>. Asegúrese de reemplazar todas las instancias de $(OLDCOMPUTERNAME) y $(NEWCOMPUTERNAME) en este archivo xml.|  
|UpdateDatabase.vbs|Propósito: Actualiza el nombre de equipo almacenado en las bases de datos de administración de BizTalk.<br /><br /> Uso: UpdateDatabase.vbs \<UpdateInfo.xml\>|  
|UpdateBAMDb.vbs|Propósito: Actualiza el nombre de equipo almacenado en las bases de datos BAM.<br /><br /> Uso: UpdateBamDb.vbs \<UpdateInfo.xml\>|  
|UpdateSSO.cmd|Propósito: Vuelve a configurar el servidor secreto del inicio de sesión único empresarial (SSO).<br /><br /> Uso: sso.cmd \<UpdateInfo.xml\>|  
|UpdateSqlServerAndInstanceName.cmd|Propósito: Vuelve a configurar SQL y SQL Express, reinicia una serie de servicios dependientes y vuelve a registrar BAMAlerts.<br /><br /> Uso: Edite el script, reemplace todas las instancias de $(NEWCOMPUTERNAME) y actualice serviceusername y servicepassword para alertas de BAM. A continuación, ejecute UpdateSqlServerAndInstanceName.cmd y pase el nombre de equipo antiguo como el primer argumento.|  
  
## <a name="creating-the-answer-files-and-running-sysprep"></a>Creación de los archivos de respuesta y ejecución de Sysprep  
  
#### <a name="to-create-the-answer-files"></a>Para crear los archivos de respuesta  
  
1.  Instalar y configurar BizTalk Server en una máquina virtual. Asegúrese de usar las opciones de instalación y configuración predeterminadas, porque Sysprep no es compatible con la instalación personalizada.  
  
2.  En la máquina virtual, copie el contenido de la carpeta incluida “scripts” en C:\Scripts.  
  
3.  Prepare un archivo de respuesta de sysprep mediante la modificación de las siguientes líneas en Sysprep.xml. (Nota: estas líneas se marcan con un "!" antes de ellos). Puede usar como una plantilla, o crear unas propias y copiar a través de la \<FirstLogonCommands\> sección.  
  
    -   $(OLDCOMPUTERNAME) Reemplácelo con el nombre del equipo de la máquina virtual.  
  
    -   Cuentas de usuario  
  
    -   Contraseñas  
  
    -   También se deben actualizar los detalles de la compañía en UpdateSqlServerAndInstance.cmd y el Sysprep.xml.  
  
     Como alternativa, puede crear un archivo de respuesta de Sysprep desde cero mediante el uso del [Kit de instalación automatizada (AIK)](http://www.microsoft.com/downloads/details.aspx?FamilyID=94bb6e34-d890-4932-81a5-5b50c657de08&DisplayLang=en) en Windows Server 2008. Asegúrese de que su \<FirstLogonCommands\> sección coincide con los ejemplos para las secuencias de comandos de BizTalk se ejecutarán en el primer arranque.  
  
#### <a name="to-run-sysprep"></a>Para ejecutar Sysprep  
  
1.  Abra un símbolo del sistema y ejecute Sysprep. El comando será similar a:  
  
    ```  
    C:\windows\system32\sysprep\sysprep.exe /oobe /generalize /shutdown /unattend:c:\scripts\unattend_Win2K8x64.xml  
    ```  
  
2.  Sysprep tarda aproximadamente media hora en ejecutarse. Cuando haya finalizado, se apagará automáticamente la máquina virtual.  
  
3.  Una vez se haya apagado la máquina virtual, combine las instantáneas y copie el archivo VHD en una ubicación segura.  
  
4.  El VHD está ahora listo para implementarse en otras máquinas virtuales, completo con el sistema operativo, BizTalk Server y todos los requisitos previos.  
  
 **SetupCompletecmd.txt**  
  
```  
del /Q /F c:\windows\system32\sysprep\sysprep.xml  
SqlCmd -s . -d Repository -A -Q "drop login [PDC08-CSD\Administrator]"  
SqlCmd -s . -d Repository -A -Q "create login [$(COMPUTERNAME)\Administrator] from windows"  
SqlCmd -s . -d Repository -A -Q "EXEC sp_changedbowner [$(COMPUTERNAME)\Administrator]"  
  
```  
  
 **Sysprep.Xml**  
  
```  
- <!--   
References:  
"Unattended Installation Settings Reference" @ http://technet.microsoft.com/library/cc749204.aspx  
"How to Sysprep in Windows 2008 " @ http://briandesmond.com/blog/how-to-sysprep-in-windows-2008  
  
Make sure to modify the values specified for the   
<Credentials> and <DomainAccounts> sections of this unattend file.  
  
SetupComplete.cmd should be copied to the C:\Windows\Setup\Scripts\ folder before running sysprep.  
Contents of SetupComplete.cmd:  
  
del /Q /F c:\windows\system32\sysprep\sysprep.xml   
SqlCmd -s . -d Repository -A -Q "drop login [PDC08-CSD\Administrator]"  
SqlCmd -s . -d Repository -A -Q "create login [$(COMPUTERNAME)\Administrator] from windows"  
SqlCmd -s . -d Repository -A -Q "EXEC sp_changedbowner [$(COMPUTERNAME)\Administrator]"  
  
Sysprep.xml (this file) should be copied to the C:\Windows\System32\sysprep\ folder.  
  
Run sysprep with the following options:  
  
sysprep /generalize /oobe /shutdown /unattend:sysprep.xml  
  -->   
  <?xml version="1.0" encoding="utf-8" ?>   
- <unattend xmlns="urn:schemas-microsoft-com:unattend">  
- <settings pass="oobeSystem">  
- <component name="Microsoft-Windows-International-Core" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <InputLocale>0409:00000409</InputLocale>   
  <SystemLocale>en-US</SystemLocale>   
  <UILanguage>en-US</UILanguage>   
  <UILanguageFallback>en-US</UILanguageFallback>   
  <UserLocale>en-US</UserLocale>   
  </component>  
- <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
- <UserAccounts>  
- <!--   
This sets the password for the Administrator account back to pass@word1   
  -->   
- <AdministratorPassword>  
  <Value>pass@word1</Value>   
  <PlainText>true</PlainText>   
  </AdministratorPassword>  
- <!--   
Enter the appropriate value for the <Name> and <Domain> elements here,   
this group/account will be added to the local Administrators and Remote Desktop Users groups.  
  -->   
- <DomainAccounts>  
- <DomainAccountList wcm:action="add">  
- <DomainAccount wcm:action="add">  
  <Name>MSMQ4TR</Name>   
  <Group>Administrators;RemoteDesktopUsers</Group>   
  </DomainAccount>  
  <Domain>Northamerica.corp.microsoft.com</Domain>   
  </DomainAccountList>  
- <!--   
Additional DomainAccountList section. Uncomment/modify this section if you need to add   
groups / users from multiple domains to the local Administrators and Remote Desktop Users groups.  
                    <DomainAccountList wcm:action="add">  
                        <DomainAccount wcm:action="add">  
                            <Name>OsloVM_NTDev</Name>  
                            <Group>Administrators;RemoteDesktopUsers</Group>  
                        </DomainAccount>  
                        <Domain>Ntdev.corp.microsoft.com</Domain>  
                    </DomainAccountList>  
  -->   
  </DomainAccounts>  
  </UserAccounts>  
- <!--   
The new computer name is generated using a combination of <RegisteredOwner>, <RegisteredOrganization>, and random alphanumeric characters. Since <RegisteredOrganization> is blank, the new computer name will be OsloVPC-*******.  
  -->   
  <RegisteredOwner>OsloVPC</RegisteredOwner>   
  <TimeZone>Pacific Standard Time</TimeZone>   
- <Display>  
  <ColorDepth>16</ColorDepth>   
  <HorizontalResolution>1024</HorizontalResolution>   
  <VerticalResolution>768</VerticalResolution>   
  </Display>  
  <RegisteredOrganization />   
  <StartPanelOff>true</StartPanelOff>   
  <ShowWindowsLive>false</ShowWindowsLive>   
  <DoNotCleanTaskBar>true</DoNotCleanTaskBar>   
  <DisableAutoDaylightTimeSet>false</DisableAutoDaylightTimeSet>   
  <BluetoothTaskbarIconEnabled>false</BluetoothTaskbarIconEnabled>   
- <VisualEffects>  
  <FontSmoothing>ClearType</FontSmoothing>   
  </VisualEffects>  
  </component>  
  </settings>  
- <settings pass="specialize">  
- <component name="Microsoft-Windows-IE-ESC" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <IEHardenAdmin>false</IEHardenAdmin>   
  <IEHardenUser>false</IEHardenUser>   
  </component>  
- <component name="Microsoft-Windows-UnattendedJoin" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
- <!--   
Enter credentials for a user account that has permissions to join a computer to the domain specified in the <JoinDomain> element. (Note: you must enter your password in plaintext here. This file will be deleted at the conclusion of Windows setup by SetupComplete.cmd in the C:\Windows\Setup\Scripts\ folder. For more information see the bottom of "How to Sysprep in Windows 2008" @ http://briandesmond.com/blog/how-to-sysprep-in-windows-2008)  
  -->   
- <Identification>  
- <Credentials>  
  <Domain>northamerica</Domain>   
  <Username>davidhamilton</Username>   
  <Password>******</Password>   
  </Credentials>  
  <JoinDomain>Redmond.corp.microsoft.com</JoinDomain>   
  </Identification>  
  </component>  
- <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
- <!--   
By specifying a value of "*" for <ComputerName>, Windows setup will generate a new computer name using a combination of <RegisteredOwner>, <RegisteredOrganization>, and random alphanumeric characters. Since <RegisteredOrganization> is blank, the new computer name will be OsloVPC-*******  
  -->   
  <ComputerName>*</ComputerName>   
  <RegisteredOrganization />   
- <!--   
The new computer name is generated using a combination of <RegisteredOwner>, <RegisteredOrganization>, and random alphanumeric characters. Since <RegisteredOrganization> is blank, the new computer name will be OsloVPC-*******.   
  -->   
  <RegisteredOwner>OsloVPC</RegisteredOwner>   
  <ShowWindowsLive>false</ShowWindowsLive>   
  <BluetoothTaskbarIconEnabled>false</BluetoothTaskbarIconEnabled>   
- <!--   
This setting will copy the profile of the original image to the renamed image when set to true   
  -->   
  <CopyProfile>true</CopyProfile>   
  <DisableAutoDaylightTimeSet>false</DisableAutoDaylightTimeSet>   
  <DoNotCleanTaskBar>true</DoNotCleanTaskBar>   
  </component>  
  </settings>  
- <settings pass="generalize">  
- <component name="Microsoft-Windows-Security-Licensing-SLC" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <SkipRearm>1</SkipRearm>   
  </component>  
- <component name="Microsoft-Windows-OutOfBoxExperience" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <DoNotOpenInitialConfigurationTasksAtLogon>true</DoNotOpenInitialConfigurationTasksAtLogon>   
  </component>  
- <component name="Microsoft-Windows-ServerManager-SvrMgrNc" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <DoNotOpenServerManagerAtLogon>true</DoNotOpenServerManagerAtLogon>   
  </component>  
  </settings>  
  <cpi:offlineImage cpi:source="catalog:e:/sources/install_windows longhorn serverenterprise.clg" xmlns:cpi="urn:schemas-microsoft-com:cpi" />   
  </unattend>  
- <!--   
When the virtual machine is started, Windows setup will:  
  
 - Assign the copy a random computer name: "OsloVPC-*****"  
 - Reset the local Administrators password to pass@word1  
 - Join the domain specified in the sysprep.xml file (under Microsoft-Windows-UnattendedJoin\Identification\JoinDomain)  
 - Add the groups/users specified under <DomainAccounts> to the local Administrators and the local Remote Desktop Users group.  
  
Known issues:  
  
 - Sysprep removes the Server Manager icon from the Quick Launch toolbar, investigating how to prevent this.  
 - To start SQL Server Management Studio, either connect to the new server name (OsloVPC-*******) or else connect to ".".  The "Server name:" drop-down box in SQL Server Management Studio is pre-populated with "PDC08-CSD" which will not work since the computer name has been changed by sysprep.  
 - There are some known issues associated with changing the computer name; renaming the computer after everything was installed was not a design, development or test requirement for this milestone.  
  -->  
```  
  
## <a name="comments"></a>Comentarios  
 Estos scripts no modifican Microsoft Office SharePoint Server. Si usa el adaptador de Windows SharePoint Services, probablemente será necesario volver a configurar Microsoft Office SharePoint Server y, a continuación, actualizar la clave SharePointAdapterManagementGroup en HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\TPM.