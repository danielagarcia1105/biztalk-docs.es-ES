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
# <a name="sysprep-a-biztalk-server-vhd-biztalk-server-sample"></a><span data-ttu-id="daca6-102">Sysprep de un VHD de BizTalk Server (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="daca6-102">Sysprep a BizTalk Server VHD (BizTalk Server Sample)</span></span>
<span data-ttu-id="daca6-103">Sysprep crea una instantánea de una máquina virtual con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalado, para una implementación rápida en otras máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="daca6-103">Sysprep creates a snapshot of a virtual machine with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installed for quick deployment on other virtual machines.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="daca6-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="daca6-104">Prerequisites</span></span>  
 <span data-ttu-id="daca6-105">Antes de usar Sysprep, debe tener algunos conocimientos sobre el uso de máquinas virtuales con Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="daca6-105">Before using Sysprep, you should have some knowledge of using virtual machines with Hyper-V.</span></span> <span data-ttu-id="daca6-106">También debe tener una máquina virtual con una instalación típica y limpia de BizTalk Server y todos sus requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="daca6-106">You should also have a virtual machine with a clean, typical installation of BizTalk Server and all of its prerequisites.</span></span>  
  
 <span data-ttu-id="daca6-107">Sysprep se ejecuta en Windows Server 2008 y Windows Vista con SP1.</span><span class="sxs-lookup"><span data-stu-id="daca6-107">Sysprep will run on Windows Server 2008 and Windows Vista with SP1.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="daca6-108">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="daca6-108">What This Sample Does</span></span>  
 <span data-ttu-id="daca6-109">Sysprep crea un VHD de una instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (incluido el sistema operativo y todos sus requisitos previos) para una implementación rápida en otras máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="daca6-109">Sysprep creates a VHD of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation (including the operating system and all prerequisites) for quick deployment on other virtual machines.</span></span> <span data-ttu-id="daca6-110">Una imagen creada mediante Sysprep elegirá un nombre de equipo nuevo para unirse al dominio la primera vez que se inicie.</span><span class="sxs-lookup"><span data-stu-id="daca6-110">An image created using Sysprep will choose a new computer name in order to join the domain the first time it starts.</span></span> <span data-ttu-id="daca6-111">Para que BizTalk Server se ejecute correctamente, es necesario actualizar las distintas instancias del nombre de equipo que se han almacenado en el registro y las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="daca6-111">To get BizTalk Server running properly, it is necessary to update various instances of the computer name that are stored in the registry and databases.</span></span>  
  
 <span data-ttu-id="daca6-112">En este documento se da por supuesto que BizTalk Server está configurado para ejecutarse en un único equipo y se muestra cómo actualizar otras instancias del nombre de equipo con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="daca6-112">This document assumes that BizTalk Server is configured to run on a single computer, and shows how to update other instances of the computer name with the new name.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="daca6-113">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="daca6-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="daca6-114">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="daca6-114">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="daca6-115">\<*Ejemplos de ruta de acceso*\>\Admin\Sysprep\\</span><span class="sxs-lookup"><span data-stu-id="daca6-115">\<*Samples Path*\>\Admin\Sysprep\\</span></span>  
  
 <span data-ttu-id="daca6-116">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="daca6-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="daca6-117">Los archivos .vbs y .cmd de la tabla siguiente están todos automatizados en los archivos de respuesta de Sysprep (Sysprep.xml y SetupCompletecmd.txt), y solo se enumeran como referencia.</span><span class="sxs-lookup"><span data-stu-id="daca6-117">The .vbs and .cmd files in the table below are all automated in the Sysprep answer files (Sysprep.xml and SetupCompletecmd.txt), and are listed here for reference only.</span></span> <span data-ttu-id="daca6-118">Si necesita ejecutar estos scripts manualmente, hágalo en el orden en que aparecen en la tabla.</span><span class="sxs-lookup"><span data-stu-id="daca6-118">If you do need to run these scripts manually, run them in the order that they appear in the table.</span></span>  
  
|<span data-ttu-id="daca6-119">Archivo</span><span class="sxs-lookup"><span data-stu-id="daca6-119">File</span></span>|<span data-ttu-id="daca6-120">Description</span><span class="sxs-lookup"><span data-stu-id="daca6-120">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="daca6-121">Sysprep.xml</span><span class="sxs-lookup"><span data-stu-id="daca6-121">Sysprep.xml</span></span>|<span data-ttu-id="daca6-122">Archivo de respuesta</span><span class="sxs-lookup"><span data-stu-id="daca6-122">Answer file</span></span>|  
|<span data-ttu-id="daca6-123">SetupCompletecmd.txt</span><span class="sxs-lookup"><span data-stu-id="daca6-123">SetupCompletecmd.txt</span></span>|<span data-ttu-id="daca6-124">Archivo de respuesta</span><span class="sxs-lookup"><span data-stu-id="daca6-124">Answer file</span></span>|  
|<span data-ttu-id="daca6-125">ReplaceMachineName.vbs</span><span class="sxs-lookup"><span data-stu-id="daca6-125">ReplaceMachineName.vbs</span></span>|<span data-ttu-id="daca6-126">Propósito: Abre un archivo y reemplaza todas las instancias de una cadena determinada con el nombre del equipo actual.</span><span class="sxs-lookup"><span data-stu-id="daca6-126">Purpose: Opens a file and replaces all instances of a given string with the current computer name.</span></span> <span data-ttu-id="daca6-127">Sirve para preparar los demás archivos de script y xml, así como para actualizar bm.exe.config.</span><span class="sxs-lookup"><span data-stu-id="daca6-127">Useful to prepare the other script and xml files, and to update bm.exe.config.</span></span><br /><br /> <span data-ttu-id="daca6-128">Uso: ReplaceMachineName.vbs \<archivo para abrir\> \<cadena para reemplazar\></span><span class="sxs-lookup"><span data-stu-id="daca6-128">Usage: ReplaceMachineName.vbs \<file to open\> \<string to replace\></span></span>|  
|<span data-ttu-id="daca6-129">UpdateRegistry.vbs</span><span class="sxs-lookup"><span data-stu-id="daca6-129">UpdateRegistry.vbs</span></span>|<span data-ttu-id="daca6-130">Propósito: Actualiza el nombre de equipo almacenado en la configuración del registro de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="daca6-130">Purpose: Updates the computer name stored in the BizTalk registry settings.</span></span><br /><br /> <span data-ttu-id="daca6-131">Uso: UpdateRegistry.vbs \<UpdateInfo.xml\>.</span><span class="sxs-lookup"><span data-stu-id="daca6-131">Usage: UpdateRegistry.vbs \<UpdateInfo.xml\>.</span></span> <span data-ttu-id="daca6-132">Asegúrese de reemplazar todas las instancias de $(OLDCOMPUTERNAME) y $(NEWCOMPUTERNAME) en este archivo xml.</span><span class="sxs-lookup"><span data-stu-id="daca6-132">Make sure to replace all instances of $(OLDCOMPUTERNAME) and $(NEWCOMPUTERNAME) in this xml file.</span></span>|  
|<span data-ttu-id="daca6-133">UpdateDatabase.vbs</span><span class="sxs-lookup"><span data-stu-id="daca6-133">UpdateDatabase.vbs</span></span>|<span data-ttu-id="daca6-134">Propósito: Actualiza el nombre de equipo almacenado en las bases de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="daca6-134">Purpose: Updates the computer name stored in the BizTalk Management databases.</span></span><br /><br /> <span data-ttu-id="daca6-135">Uso: UpdateDatabase.vbs \<UpdateInfo.xml\></span><span class="sxs-lookup"><span data-stu-id="daca6-135">Usage: UpdateDatabase.vbs \<UpdateInfo.xml\></span></span>|  
|<span data-ttu-id="daca6-136">UpdateBAMDb.vbs</span><span class="sxs-lookup"><span data-stu-id="daca6-136">UpdateBAMDb.vbs</span></span>|<span data-ttu-id="daca6-137">Propósito: Actualiza el nombre de equipo almacenado en las bases de datos BAM.</span><span class="sxs-lookup"><span data-stu-id="daca6-137">Purpose: Updates the computer name stored in the BAM databases.</span></span><br /><br /> <span data-ttu-id="daca6-138">Uso: UpdateBamDb.vbs \<UpdateInfo.xml\></span><span class="sxs-lookup"><span data-stu-id="daca6-138">Usage: UpdateBamDb.vbs \<UpdateInfo.xml\></span></span>|  
|<span data-ttu-id="daca6-139">UpdateSSO.cmd</span><span class="sxs-lookup"><span data-stu-id="daca6-139">UpdateSSO.cmd</span></span>|<span data-ttu-id="daca6-140">Propósito: Vuelve a configurar el servidor secreto del inicio de sesión único empresarial (SSO).</span><span class="sxs-lookup"><span data-stu-id="daca6-140">Purpose: Reconfigures the Enterprise Single Sign-on (SSO) secret server.</span></span><br /><br /> <span data-ttu-id="daca6-141">Uso: sso.cmd \<UpdateInfo.xml\></span><span class="sxs-lookup"><span data-stu-id="daca6-141">Usage: sso.cmd \<UpdateInfo.xml\></span></span>|  
|<span data-ttu-id="daca6-142">UpdateSqlServerAndInstanceName.cmd</span><span class="sxs-lookup"><span data-stu-id="daca6-142">UpdateSqlServerAndInstanceName.cmd</span></span>|<span data-ttu-id="daca6-143">Propósito: Vuelve a configurar SQL y SQL Express, reinicia una serie de servicios dependientes y vuelve a registrar BAMAlerts.</span><span class="sxs-lookup"><span data-stu-id="daca6-143">Purpose: Reconfigures SQL and SQL Express, restarts a series of dependent services, and reregisters BAMAlerts.</span></span><br /><br /> <span data-ttu-id="daca6-144">Uso: Edite el script, reemplace todas las instancias de $(NEWCOMPUTERNAME) y actualice serviceusername y servicepassword para alertas de BAM.</span><span class="sxs-lookup"><span data-stu-id="daca6-144">Usage: Edit the script and replace all instances of $(NEWCOMPUTERNAME), and update the serviceusername and servicepassword for BAM Alerts.</span></span> <span data-ttu-id="daca6-145">A continuación, ejecute UpdateSqlServerAndInstanceName.cmd y pase el nombre de equipo antiguo como el primer argumento.</span><span class="sxs-lookup"><span data-stu-id="daca6-145">Then run UpdateSqlServerAndInstanceName.cmd passing the old computer name as the first argument.</span></span>|  
  
## <a name="creating-the-answer-files-and-running-sysprep"></a><span data-ttu-id="daca6-146">Creación de los archivos de respuesta y ejecución de Sysprep</span><span class="sxs-lookup"><span data-stu-id="daca6-146">Creating the Answer Files and Running Sysprep</span></span>  
  
#### <a name="to-create-the-answer-files"></a><span data-ttu-id="daca6-147">Para crear los archivos de respuesta</span><span class="sxs-lookup"><span data-stu-id="daca6-147">To create the answer files</span></span>  
  
1.  <span data-ttu-id="daca6-148">Instalar y configurar BizTalk Server en una máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="daca6-148">Install and configure BizTalk Server on a virtual machine.</span></span> <span data-ttu-id="daca6-149">Asegúrese de usar las opciones de instalación y configuración predeterminadas, porque Sysprep no es compatible con la instalación personalizada.</span><span class="sxs-lookup"><span data-stu-id="daca6-149">Be sure to use default installation and configuration options, since Sysprep does not support customized installation.</span></span>  
  
2.  <span data-ttu-id="daca6-150">En la máquina virtual, copie el contenido de la carpeta incluida “scripts” en C:\Scripts.</span><span class="sxs-lookup"><span data-stu-id="daca6-150">Copy the contents of the included “scripts” folder to C:\Scripts on the virtual machine.</span></span>  
  
3.  <span data-ttu-id="daca6-151">Prepare un archivo de respuesta de sysprep mediante la modificación de las siguientes líneas en Sysprep.xml.</span><span class="sxs-lookup"><span data-stu-id="daca6-151">Prepare a sysprep answer file by modifying the following lines in Sysprep.xml.</span></span> <span data-ttu-id="daca6-152">(Nota: estas líneas se marcan con un "!"</span><span class="sxs-lookup"><span data-stu-id="daca6-152">(Note: These lines are marked with a “!”</span></span> <span data-ttu-id="daca6-153">antes de ellos). Puede usar como una plantilla, o crear unas propias y copiar a través de la \<FirstLogonCommands\> sección.</span><span class="sxs-lookup"><span data-stu-id="daca6-153">before them.) You can use these as a template, or make your own and copy over the \<FirstLogonCommands\> section.</span></span>  
  
    -   <span data-ttu-id="daca6-154">$(OLDCOMPUTERNAME) Reemplácelo con el nombre del equipo de la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="daca6-154">$(OLDCOMPUTERNAME) Replace with the current computer name of the virtual machine.</span></span>  
  
    -   <span data-ttu-id="daca6-155">Cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="daca6-155">User accounts</span></span>  
  
    -   <span data-ttu-id="daca6-156">Contraseñas</span><span class="sxs-lookup"><span data-stu-id="daca6-156">Passwords</span></span>  
  
    -   <span data-ttu-id="daca6-157">También se deben actualizar los detalles de la compañía en UpdateSqlServerAndInstance.cmd y el Sysprep.xml.</span><span class="sxs-lookup"><span data-stu-id="daca6-157">Any company details should also be updated in UpdateSqlServerAndInstance.cmd and your Sysprep.xml.</span></span>  
  
     <span data-ttu-id="daca6-158">Como alternativa, puede crear un archivo de respuesta de Sysprep desde cero mediante el uso del [Kit de instalación automatizada (AIK)](http://www.microsoft.com/downloads/details.aspx?FamilyID=94bb6e34-d890-4932-81a5-5b50c657de08&DisplayLang=en) en Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="daca6-158">Alternatively, you can create a Sysprep answer file from scratch using use the [Automated Installation Kit (AIK)](http://www.microsoft.com/downloads/details.aspx?FamilyID=94bb6e34-d890-4932-81a5-5b50c657de08&DisplayLang=en) on Windows Server 2008.</span></span> <span data-ttu-id="daca6-159">Asegúrese de que su \<FirstLogonCommands\> sección coincide con los ejemplos para las secuencias de comandos de BizTalk se ejecutarán en el primer arranque.</span><span class="sxs-lookup"><span data-stu-id="daca6-159">Ensure that your \<FirstLogonCommands\> section matches the samples so the BizTalk scripts will run on the first boot.</span></span>  
  
#### <a name="to-run-sysprep"></a><span data-ttu-id="daca6-160">Para ejecutar Sysprep</span><span class="sxs-lookup"><span data-stu-id="daca6-160">To run Sysprep</span></span>  
  
1.  <span data-ttu-id="daca6-161">Abra un símbolo del sistema y ejecute Sysprep.</span><span class="sxs-lookup"><span data-stu-id="daca6-161">Open a command prompt and run Sysprep.</span></span> <span data-ttu-id="daca6-162">El comando será similar a:</span><span class="sxs-lookup"><span data-stu-id="daca6-162">The command will look something like:</span></span>  
  
    ```  
    C:\windows\system32\sysprep\sysprep.exe /oobe /generalize /shutdown /unattend:c:\scripts\unattend_Win2K8x64.xml  
    ```  
  
2.  <span data-ttu-id="daca6-163">Sysprep tarda aproximadamente media hora en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="daca6-163">Sysprep takes about half an hour to run.</span></span> <span data-ttu-id="daca6-164">Cuando haya finalizado, se apagará automáticamente la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="daca6-164">When it is complete, it will automatically shut down the virtual machine.</span></span>  
  
3.  <span data-ttu-id="daca6-165">Una vez se haya apagado la máquina virtual, combine las instantáneas y copie el archivo VHD en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="daca6-165">After the virtual machine has been shut down, merge any snapshots, and copy your VHD file to a safe location.</span></span>  
  
4.  <span data-ttu-id="daca6-166">El VHD está ahora listo para implementarse en otras máquinas virtuales, completo con el sistema operativo, BizTalk Server y todos los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="daca6-166">Your VHD is now ready to be deployed on other virtual machines, complete with operating system, BizTalk Server, and all prerequisites.</span></span>  
  
 <span data-ttu-id="daca6-167">**SetupCompletecmd.txt**</span><span class="sxs-lookup"><span data-stu-id="daca6-167">**SetupCompletecmd.txt**</span></span>  
  
```  
del /Q /F c:\windows\system32\sysprep\sysprep.xml  
SqlCmd -s . -d Repository -A -Q "drop login [PDC08-CSD\Administrator]"  
SqlCmd -s . -d Repository -A -Q "create login [$(COMPUTERNAME)\Administrator] from windows"  
SqlCmd -s . -d Repository -A -Q "EXEC sp_changedbowner [$(COMPUTERNAME)\Administrator]"  
  
```  
  
 <span data-ttu-id="daca6-168">**Sysprep.Xml**</span><span class="sxs-lookup"><span data-stu-id="daca6-168">**Sysprep.xml**</span></span>  
  
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
  
## <a name="comments"></a><span data-ttu-id="daca6-169">Comentarios</span><span class="sxs-lookup"><span data-stu-id="daca6-169">Comments</span></span>  
 <span data-ttu-id="daca6-170">Estos scripts no modifican Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="daca6-170">These scripts do not modify Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="daca6-171">Si usa el adaptador de Windows SharePoint Services, probablemente será necesario volver a configurar Microsoft Office SharePoint Server y, a continuación, actualizar la clave SharePointAdapterManagementGroup en HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\TPM.</span><span class="sxs-lookup"><span data-stu-id="daca6-171">If you are using the Windows SharePoint Services adapter, you will probably need to reconfigure Microsoft Office SharePoint Server and then update the SharePointAdapterManagementGroup key under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\TPM.</span></span>