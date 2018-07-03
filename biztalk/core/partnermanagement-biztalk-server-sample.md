---
title: PartnerManagement (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83e2a84f-ab25-4a7c-b8d7-0ba2dfa93095
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e0447a89929ba729de78b2e10f337f0a62b28e4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013685"
---
# <a name="partnermanagement-biztalk-server-sample"></a>PartnerManagement (ejemplo de BizTalk Server)
El ejemplo PartnerManagement muestra cómo administrar entidades en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante el uso de la **ExplorerOM** objetos de administración.  

## <a name="prerequisites"></a>Requisitos previos  

- Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.  

- El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts. Para obtener más información, vea [Examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).  

## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra cómo utilizar las clases administrativas desde el **Microsoft.BizTalk.ExplorerOM** espacio de nombres para administrar entidades. Las entidades representan socios comerciales o aplicaciones de servidor con las que puede interactuar un proceso empresarial. Para obtener más información acerca de las entidades en general, vea la documentación de [partes](../core/parties.md) o [vínculos de rol y Roles de vínculo de servicio](../core/role-links-and-service-link-roles.md). El ejemplo está escrito en Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]. En este tema también se incluye un script de ejemplo de Windows PowerShell. El ejemplo muestra las siguientes operaciones:  

- Crear una nueva entidad con un alias personalizado o estándar y agregar puertos de envío existentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a la entidad.  

- Dar de alta a la nueva entidad con un vínculo de rol existente en BizTalk Server.  

- Dar de baja la nueva entidad.  

- Eliminar la nueva entidad.  

## <a name="where-to-find-this-sample"></a>Dónde encontrar este ejemplo  
 El ejemplo se encuentra en la siguiente ubicación del SDK:  

 \<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\PartnerManagement  

 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  


|                      Archivos                       |                                                 Descripción                                                  |
|----------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                PartnerManagement.cs                | Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo. |
| PartnerManagement.sln y PartnerManagement.csproj |                                  Archivos de solución y proyecto para el ejemplo.                                  |

## <a name="building-and-running-this-sample"></a>Generación y ejecución del ejemplo  
 Antes de generar el ejemplo, debe realizar cuatro modificaciones de código para personalizar el ejemplo del servidor BizTalk Server. Esta acción es necesaria porque el ejemplo usa nombres arbitrarios para puertos de envío asociados con la entidad y un nombre de rol arbitrario para dar de alta. Por lo tanto, debe proporcionar nombres válidos para el ejemplo. Para demostrar este ejemplo, en este tema describe en primer lugar crear el ejemplo PartyResolution del siguiente directorio: \< *ruta de ejemplos*\>\Orchestrations\PartyResolution. Este enfoque se usa para asegurar que estén presentes un nombre de rol y nombres de puerto de envío válidos en BizTalk Server para mostrar los procedimientos del ejemplo.  

#### <a name="to-build-this-sample"></a>Procedimiento para generar este ejemplo  

1. En primer lugar, asegúrese de que se ha generado e inicializado el ejemplo PartyResolution de modo que en él se puedan usar un nombre de rol y nombres de puerto de envío válidos. Esto se documenta en la sección titulada "Crear e inicializar este ejemplo" en [PartyResolution (ejemplo de BizTalk Server)](../core/partyresolution-biztalk-server-sample.md).  

2. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución PartnerManagement.sln.  

3. En el Explorador de soluciones, abra el archivo de origen PartnerManagement.cs.  

4. Desplácese hacia abajo hasta la función denominada **CreateParty** e inserte los dos nombres de puerto partyresolution de ejemplo o use nombres válidos desde el entorno de BizTalk server de envío. En el ejemplo de código siguiente se muestra el cambio mediante los puertos de envío del ejemplo PartyResolution.  

   ```  
   // Replacing arbitrary send port names with PartyResolution send port names ===  

   //            myParty.SendPorts.Add(catalog.SendPorts["NormalDelivery"]);  
   //            myParty.SendPorts.Add(catalog.SendPorts["ExpressDelivery"]);  
               myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency1"]);  
               myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency2"]);  

   ```  

5. Desplácese hacia abajo hasta la función denominada **EnlistParty** y cambie el bucle foreach para que busca en el ensamblado de proveedor para un rol denominado "ShipmentRole" para usar con la inscripción. En el ejemplo de código siguiente se muestra el cambio para usar el ShipmentRole del ejemplo PartyResolution.  

   ```  
               // Search for the “Shipmentrole” instead of “shipperRole”  
               Role svcRole = null;  
   //===       foreach (Role role in catalog.Assemblies[0].Roles)  
               foreach (Role role in catalog.Assemblies["Supplier"].Roles)  
               {  
   //===          if (role.Name == "ShipperRole")  
                  if (role.Name == "ShipmentRole")  
                  {  
                     svcRole = role;  
                     break;  
                  }  
               }  

   ```  

6. Desplácese hacia abajo hasta la función denominada **UnenlistParty** y cambie el bucle foreach para buscar ShipmentRole en el ensamblado de proveedor. En el siguiente ejemplo de código se muestra este cambio.  

   ```  
               // Search for the “ShipmentRole” instead of “shipperRole”  
               Role svcRole = null;  
   //===       foreach (Role role in catalog.Assemblies[0].Roles)  
               foreach (Role role in catalog.Assemblies["Supplier"].Roles)  
               {  
   //===          if (role.Name == "ShipperRole")  
                  if (role.Name == "ShipmentRole")  
                  {  
                     svcRole = role;  
                     break;  
                  }  
               }  

   ```  

7. Después de crear y dar de alta la nueva entidad con ShipmentRole, el ejemplo está diseñado para dar de baja inmediatamente a la entidad y eliminarla. Agregue el cambio de código siguiente al procedimiento principal para realizar una pausa en la ejecución y permitirle ver la inscripción creada para la nueva entidad en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

   ```  
   static void Main(string[] args)  
   {  
      CreateParty();     
      EnlistParty();     

      Console.WriteLine("\nNew Party created and enlisted.\n\nPress <Enter> to unenlist and delete.\n");  
      Console.ReadLine();  

      UnenlistParty();   
      DeleteParty();  
   }  

   ```  

8. En el menú **Compilar** , haga clic en **Compilar solución**.  

#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  

1. Abra una ventana de comandos y desplácese a la siguiente carpeta:  

    \<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\PartnerManagement\bin\Debug  

2. Ejecute el archivo PartnerManagement.exe.  

3. Cuando el ejemplo muestra el mensaje que se crea y se da de alta la nueva entidad, abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración y ver la nueva entidad denominada **FedEx** bajo el **partes** nodo.  

4. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, vaya a la vista de árbol del **ShipmentRole** en **Applications\BizTalk Application 1\Role Links**. Haga doble clic en **ShipmentRole** y observe **ShipmentAgency1** asignado a la **SupplierAdvice** operación y **ShipmentAgency2** asignado a la **SupplierOrder** operación en la inscripción.  

5. En la ventana de comandos, presione ENTRAR para permitir que el ejemplo dé de baja y elimine la nueva entidad.  

6. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de consola, compruebe que la entidad ha desde el **ShipmentRole** y eliminadas desde la **partes** nodo.  

## <a name="windows-powershell-script-example"></a>Ejemplo de un script de Windows PowerShell  
 El siguiente ejemplo de script de Windows PowerShell se puede usar para mostrar las mismas características de la **ExplorerOM** clases:  

```  
#===============================================================#  
#===                                                         ===#  
#=== Create a new party named "FedEx" as an example.         ===#  
#===                                                         ===#  
#=== Two Shipment agency send ports from the PartyResolution ===#  
#=== sample will be added to the party.                      ===#  
#===                                                         ===#  
#===============================================================#  
Function CreateParty  
{  
  #=== Create a party =====================#  
  $myParty = $Catalog.AddNewParty()  
  $myParty.Name = "FedEx"  

  #=== create a standard alias ==========================#  
  $standardAlias = $myParty.AddNewAlias()  
  $standardAlias.Name = "D-U-N-S (Dun & Bradstreet)"  
  $standardAlias.Value = "Value1"  

  #=== Create a custom alias ==================#  
  $customAlias = $myParty.AddNewAlias()  
  $customAlias.Name = "Telephone"  
  $customAlias.Qualifier = "100"  
  $customAlias.Value = "4255550234"  

  #=== Add party send ports =====================================================#  

  #===============================================================#  
  #=== Have to use IList directly on this sendports collection ===#  
  #=== to work around a PowerShell issue.                      ===#  
  #===============================================================#  
  $iList = [System.Collections.IList]  

  $sendport1 = $Catalog.SendPorts["SP_FilesToShipmentAgency1"]  
  [void] $iList.GetMethod("Add").Invoke($myParty.SendPorts,$sendport1)  

  $sendport2 = $Catalog.SendPorts["SP_FilesToShipmentAgency2"]  
  [void] $iList.GetMethod("Add").Invoke($myParty.SendPorts,$sendport2)  

  #=== Specify a signature certificate, make sure the certificate is available ===#  
  #=== in the AddressBook store of the Local Machine                           ===#  

  foreach ($certificate in $Catalog.Certificates)  
  {  
    if ($certificate.ShortName -eq "BR, Certisign Certificadora Digital Ltda., Certisign - Autoridade Certificadora - AC2")  
    {  
      $myParty.SignatureCert = $certificate  
    }  
  }  

  #=== Commit the changes ===#  
  $catalog.SaveChanges()  
}  

#===============================================================#  
#===                                                         ===#  
#=== Delete the party named "FedEx"                          ===#  
#===                                                         ===#  
#===============================================================#  
Function DeleteParty  
{  
  $Catalog.RemoveParty($Catalog.Parties["FedEx"])  

  #=== Commit the changes ===#  
  $catalog.SaveChanges()  
}  

#===============================================================#  
#===                                                         ===#  
#=== Enlist the "FedEx" party with the "ShipmentRole"        ===#  
#===                                                         ===#  
#===============================================================#  
Function EnlistParty  
{  
  $myParty = $Catalog.Parties["FedEx"]  

  #=== Get the "ShipmentRole" in the Supplier assembly.        ===#  
  $svcRole = $Catalog.Assemblies["Supplier"].Roles["ShipmentRole"]  

  #=== Enlist the party under the shipper role ===#  
  $enlistedParty = $svcRole.AddNewEnlistedParty($myParty)  

  #===============================================================#  
  #=== Have to use IList directly on this sendports collection ===#  
  #=== to work around a PowerShell issue.                      ===#  
  #===============================================================#  
  $iList = [System.Collections.IList]   

  #===============================================================#  
  #=== Example port to be used for the role's "SupplierAdvice" ===#  
  #=== operation.                                              ===#  
  #=== Using the first send port added to the new party which  ===#  
  #=== is "SP_FilesToShipmentAgency1" at index 0 in the        ===#  
  #=== sendports collection.                                   ===#  
  #===============================================================#  
  $enlistedParty.Mappings[0].SendPort = $iList.GetProperty("Item").GetValue($myParty.SendPorts,0)  

  #===============================================================#  
  #=== Example port to be used for the role's "SupplierOrder"  ===#  
  #=== operation.                                              ===#  
  #=== Using the second send port added to the new party which ===#  
  #=== is "SP_FilesToShipmentAgency2" at index 1 in the        ===#  
  #=== sendports collection.                                   ===#  
  #===============================================================#  
  $enlistedParty.Mappings[1].SendPort = $iList.GetProperty("Item").GetValue($myParty.SendPorts,1)  

  #=== Commit the changes ===#  
  $Catalog.SaveChanges()  
}  

#===============================================================#  
#===                                                         ===#  
#=== Unenlist the "FedEx" party from the ShipmentRole        ===#  
#===                                                         ===#  
#===============================================================#  
Function UnenlistParty  
{  
  #=== Get the "ShipmentRole" from the Supplier assembly. ===#  
  $svcRole = $Catalog.Assemblies["Supplier"].Roles["ShipmentRole"]  

  #=== Remove the "FedEx" party ===#  
  foreach ($enlistedparty in $svcRole.EnlistedParties)  
  {  
    if ($enlistedparty.Party.Name -eq "FedEx")  
    {  
      $svcRole.RemoveEnlistedParty($enlistedparty)  
      break  
    }  
  }  

  #=== Commit the changes ===#  
  $Catalog.SaveChanges()  
}  

#===================#  
#=== Main Script ===#  
#===================#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

#=== This sample expects the PartyResolution sample to be built and deployed  ===#  
#=== to the BizTalk Server.                                                   ===#  

write-host `r`nMake sure the "PartyResolution" sample application from the Orchestrations   
write-host sample directory is deployed and running.  
write-host By default it will be listed in the BizTalk Server Administration Console  
write-host with the application name: `"BizTalk.Application.1`"`r`n  

$SupplierAssembly = $Catalog.Assemblies["Supplier"]  

#==================================================================#  
#=== Register a trap handler to discard changes on exceptions   ===#  
#=== Execution will continue in the event we want to unenlist,  ===#  
#=== and delete the party.                                      ===#  
#==================================================================#  

$Script:NoExceptionOccurred = $true  
$ErrorActionPreference="silentlycontinue"  
trap   
{   
  $Script:NoExceptionOccurred = $false  
  "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes and continuing execution so we can attempt to clean up the party...`r`n"  
  $Catalog.DiscardChanges()  
}  

CreateParty  
EnlistParty  

if ($Script:NoExceptionOccurred)  
{  
  Write-Host "`r`nExample Party `"FedEx`" should be created and enlisted with the `"ShipmentRole`".`r`n"  
  Write-Host You can view the results in the BizTalk Server Administration console.`r`n  
  Write-Host "Press <Enter> to unenlist and delete...`r`n"  
  Read-Host  
}  

UnenlistParty  
DeleteParty  

```  

 A continuación se proporciona el resultado de la ejecución del script de ejemplo de PowerShell. Si no se ejecuta el script, asegúrese de que el script de PowerShell está habilitado según la nota de requisitos que aparece en la parte superior de este tema.  

```  
PS C:\> .\PartnerManagement.ps1  

Make sure the PartyResolution sample application from the Orchestrations  
sample directory is deployed and running.  
By default it will be listed in the BizTalk Server Administration Console  
with the application name: "BizTalk.Application.1"  

Example Party "FedEx" should be created and enlisted with the "ShipmentRole".  

You can view the results in the BizTalk Server Administration console.  

Press <Enter> to unenlist and delete...  
```  

## <a name="see-also"></a>Vea también  
 [Partes](../core/parties.md)   
 [Vínculos de rol y Roles de vínculo de servicio](../core/role-links-and-service-link-roles.md)   
 [Admin (carpeta de ejemplos de BizTalk Server)](../core/admin-biztalk-server-samples-folder.md)