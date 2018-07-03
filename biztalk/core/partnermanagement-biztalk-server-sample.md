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
# <a name="partnermanagement-biztalk-server-sample"></a><span data-ttu-id="c0138-102">PartnerManagement (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="c0138-102">PartnerManagement (BizTalk Server Sample)</span></span>
<span data-ttu-id="c0138-103">El ejemplo PartnerManagement muestra cómo administrar entidades en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante el uso de la **ExplorerOM** objetos de administración.</span><span class="sxs-lookup"><span data-stu-id="c0138-103">The PartnerManagement sample demonstrates how to manage parties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment by using the **ExplorerOM** administration objects.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="c0138-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c0138-104">Prerequisites</span></span>  

- <span data-ttu-id="c0138-105">Debe disponer de privilegios administrativos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para usar los objetos de administración de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c0138-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="c0138-106">El script de Windows PowerShell requiere que la directiva de ejecución de Windows PowerShell permita la ejecución de scripts.</span><span class="sxs-lookup"><span data-stu-id="c0138-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="c0138-107">Para obtener más información, vea [Examinar la directiva de ejecución](http://go.microsoft.com/fwlink/?LinkId=128930).</span><span class="sxs-lookup"><span data-stu-id="c0138-107">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="c0138-108">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0138-108">What This Sample Does</span></span>  
 <span data-ttu-id="c0138-109">Este ejemplo muestra cómo utilizar las clases administrativas desde el **Microsoft.BizTalk.ExplorerOM** espacio de nombres para administrar entidades.</span><span class="sxs-lookup"><span data-stu-id="c0138-109">This sample demonstrates using the administrative classes from the **Microsoft.BizTalk.ExplorerOM** namespace to manage parties.</span></span> <span data-ttu-id="c0138-110">Las entidades representan socios comerciales o aplicaciones de servidor con las que puede interactuar un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="c0138-110">Parties represent trading partners or back-end applications with which a business process can interact.</span></span> <span data-ttu-id="c0138-111">Para obtener más información acerca de las entidades en general, vea la documentación de [partes](../core/parties.md) o [vínculos de rol y Roles de vínculo de servicio](../core/role-links-and-service-link-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c0138-111">For more information about parties in general, see the documentation for [Parties](../core/parties.md) or [Role Links and Service Link Roles](../core/role-links-and-service-link-roles.md).</span></span> <span data-ttu-id="c0138-112">El ejemplo está escrito en Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0138-112">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="c0138-113">En este tema también se incluye un script de ejemplo de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0138-113">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="c0138-114">El ejemplo muestra las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="c0138-114">The sample demonstrates the following operations:</span></span>  

- <span data-ttu-id="c0138-115">Crear una nueva entidad con un alias personalizado o estándar y agregar puertos de envío existentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a la entidad.</span><span class="sxs-lookup"><span data-stu-id="c0138-115">Creating a new party with a custom or standard alias and adding existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send ports to the party.</span></span>  

- <span data-ttu-id="c0138-116">Dar de alta a la nueva entidad con un vínculo de rol existente en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c0138-116">Enlisting the new party with an existing role link on the BizTalk server.</span></span>  

- <span data-ttu-id="c0138-117">Dar de baja la nueva entidad.</span><span class="sxs-lookup"><span data-stu-id="c0138-117">Un-enlisting the new party.</span></span>  

- <span data-ttu-id="c0138-118">Eliminar la nueva entidad.</span><span class="sxs-lookup"><span data-stu-id="c0138-118">Deleting the new party.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="c0138-119">Dónde encontrar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0138-119">Where To Find This Sample</span></span>  
 <span data-ttu-id="c0138-120">El ejemplo se encuentra en la siguiente ubicación del SDK:</span><span class="sxs-lookup"><span data-stu-id="c0138-120">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="c0138-121">\<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\PartnerManagement</span><span class="sxs-lookup"><span data-stu-id="c0138-121">\<*Samples Path*\>\Admin\ExplorerOM\PartnerManagement</span></span>  

 <span data-ttu-id="c0138-122">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="c0138-122">The following table shows the files in this sample and describes their purpose.</span></span>  


|                      <span data-ttu-id="c0138-123">Archivos</span><span class="sxs-lookup"><span data-stu-id="c0138-123">File(s)</span></span>                       |                                                 <span data-ttu-id="c0138-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0138-124">Description</span></span>                                                  |
|----------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                <span data-ttu-id="c0138-125">PartnerManagement.cs</span><span class="sxs-lookup"><span data-stu-id="c0138-125">PartnerManagement.cs</span></span>                | <span data-ttu-id="c0138-126">Archivo de origen de [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] para las operaciones que se muestran en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c0138-126">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="c0138-127">PartnerManagement.sln y PartnerManagement.csproj</span><span class="sxs-lookup"><span data-stu-id="c0138-127">PartnerManagement.sln and PartnerManagement.csproj</span></span> |                                  <span data-ttu-id="c0138-128">Archivos de solución y proyecto para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c0138-128">Solution and project files for the sample.</span></span>                                  |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="c0138-129">Generación y ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0138-129">Building and Running This Sample</span></span>  
 <span data-ttu-id="c0138-130">Antes de generar el ejemplo, debe realizar cuatro modificaciones de código para personalizar el ejemplo del servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c0138-130">Before you build the sample, you need to make four code modifications to customize the sample for the BizTalk server.</span></span> <span data-ttu-id="c0138-131">Esta acción es necesaria porque el ejemplo usa nombres arbitrarios para puertos de envío asociados con la entidad y un nombre de rol arbitrario para dar de alta.</span><span class="sxs-lookup"><span data-stu-id="c0138-131">This is necessary because the sample uses arbitrary names for send ports associated with the party and an arbitrary role name for the enlistment.</span></span> <span data-ttu-id="c0138-132">Por lo tanto, debe proporcionar nombres válidos para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c0138-132">Therefore you need to provide valid names to the sample.</span></span> <span data-ttu-id="c0138-133">Para demostrar este ejemplo, en este tema describe en primer lugar crear el ejemplo PartyResolution del siguiente directorio: \< *ruta de ejemplos*\>\Orchestrations\PartyResolution.</span><span class="sxs-lookup"><span data-stu-id="c0138-133">To demonstrate this sample, this topic describes first building the PartyResolution sample from the following directory: \<*Samples Path*\>\Orchestrations\PartyResolution.</span></span> <span data-ttu-id="c0138-134">Este enfoque se usa para asegurar que estén presentes un nombre de rol y nombres de puerto de envío válidos en BizTalk Server para mostrar los procedimientos del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c0138-134">This approach is used to make sure a valid role name and send port names are present on the BizTalk server to demonstrate the sample procedures.</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="c0138-135">Procedimiento para generar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0138-135">To build this sample</span></span>  

1. <span data-ttu-id="c0138-136">En primer lugar, asegúrese de que se ha generado e inicializado el ejemplo PartyResolution de modo que en él se puedan usar un nombre de rol y nombres de puerto de envío válidos.</span><span class="sxs-lookup"><span data-stu-id="c0138-136">First make sure the PartyResolution sample has been built and initialized so that a valid role name and send port names can be used by the sample.</span></span> <span data-ttu-id="c0138-137">Esto se documenta en la sección titulada "Crear e inicializar este ejemplo" en [PartyResolution (ejemplo de BizTalk Server)](../core/partyresolution-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="c0138-137">This is documented in the section entitled “Building and Initializing This Sample” in  [PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md).</span></span>  

2. <span data-ttu-id="c0138-138">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el archivo de solución PartnerManagement.sln.</span><span class="sxs-lookup"><span data-stu-id="c0138-138">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file PartnerManagement.sln.</span></span>  

3. <span data-ttu-id="c0138-139">En el Explorador de soluciones, abra el archivo de origen PartnerManagement.cs.</span><span class="sxs-lookup"><span data-stu-id="c0138-139">In Solution Explorer, open the source file PartnerManagement.cs.</span></span>  

4. <span data-ttu-id="c0138-140">Desplácese hacia abajo hasta la función denominada **CreateParty** e inserte los dos nombres de puerto partyresolution de ejemplo o use nombres válidos desde el entorno de BizTalk server de envío.</span><span class="sxs-lookup"><span data-stu-id="c0138-140">Scroll down into the function named **CreateParty** and insert the two send port names from the PartyResolution sample or use valid names from the BizTalk server environment.</span></span> <span data-ttu-id="c0138-141">En el ejemplo de código siguiente se muestra el cambio mediante los puertos de envío del ejemplo PartyResolution.</span><span class="sxs-lookup"><span data-stu-id="c0138-141">The following code example demonstrates the change using the send ports from the PartyResolution sample.</span></span>  

   ```  
   // Replacing arbitrary send port names with PartyResolution send port names ===  

   //            myParty.SendPorts.Add(catalog.SendPorts["NormalDelivery"]);  
   //            myParty.SendPorts.Add(catalog.SendPorts["ExpressDelivery"]);  
               myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency1"]);  
               myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency2"]);  

   ```  

5. <span data-ttu-id="c0138-142">Desplácese hacia abajo hasta la función denominada **EnlistParty** y cambie el bucle foreach para que busca en el ensamblado de proveedor para un rol denominado "ShipmentRole" para usar con la inscripción.</span><span class="sxs-lookup"><span data-stu-id="c0138-142">Scroll down into the function named **EnlistParty** and change the foreach loop so that it searches the Supplier assembly for a role named “ShipmentRole” to use with the enlistment.</span></span> <span data-ttu-id="c0138-143">En el ejemplo de código siguiente se muestra el cambio para usar el ShipmentRole del ejemplo PartyResolution.</span><span class="sxs-lookup"><span data-stu-id="c0138-143">The following code example demonstrates the change to use the ShipmentRole from the PartyResolution sample.</span></span>  

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

6. <span data-ttu-id="c0138-144">Desplácese hacia abajo hasta la función denominada **UnenlistParty** y cambie el bucle foreach para buscar ShipmentRole en el ensamblado de proveedor.</span><span class="sxs-lookup"><span data-stu-id="c0138-144">Scroll down into the function named **UnenlistParty** and change the foreach loop to search the Supplier assembly for the ShipmentRole.</span></span> <span data-ttu-id="c0138-145">En el siguiente ejemplo de código se muestra este cambio.</span><span class="sxs-lookup"><span data-stu-id="c0138-145">The following code example demonstrates this change.</span></span>  

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

7. <span data-ttu-id="c0138-146">Después de crear y dar de alta la nueva entidad con ShipmentRole, el ejemplo está diseñado para dar de baja inmediatamente a la entidad y eliminarla.</span><span class="sxs-lookup"><span data-stu-id="c0138-146">After creating and enlisting the new party with the ShipmentRole, the sample is designed to immediately un-enlist the party and delete it.</span></span> <span data-ttu-id="c0138-147">Agregue el cambio de código siguiente al procedimiento principal para realizar una pausa en la ejecución y permitirle ver la inscripción creada para la nueva entidad en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0138-147">Add the following code change to the main procedure to pause execution and allow you to view the created enlistment for the new party in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

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

8. <span data-ttu-id="c0138-148">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="c0138-148">On the **Build** menu, click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="c0138-149">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0138-149">To run this sample</span></span>  

1. <span data-ttu-id="c0138-150">Abra una ventana de comandos y desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="c0138-150">Open a command window and navigate to the following folder:</span></span>  

    <span data-ttu-id="c0138-151">\<*Ejemplos de la ruta de acceso*\>\Admin\ExplorerOM\PartnerManagement\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="c0138-151">\<*Samples Path*\>\Admin\ExplorerOM\PartnerManagement\bin\Debug</span></span>  

2. <span data-ttu-id="c0138-152">Ejecute el archivo PartnerManagement.exe.</span><span class="sxs-lookup"><span data-stu-id="c0138-152">Run the file PartnerManagement.exe.</span></span>  

3. <span data-ttu-id="c0138-153">Cuando el ejemplo muestra el mensaje que se crea y se da de alta la nueva entidad, abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración y ver la nueva entidad denominada **FedEx** bajo el **partes** nodo.</span><span class="sxs-lookup"><span data-stu-id="c0138-153">When the sample displays the message that the new party is created and enlisted, open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and view the new party named **FedEx** under the **Parties** node.</span></span>  

4. <span data-ttu-id="c0138-154">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, vaya a la vista de árbol del **ShipmentRole** en **Applications\BizTalk Application 1\Role Links**.</span><span class="sxs-lookup"><span data-stu-id="c0138-154">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, navigate the tree view to the **ShipmentRole** under **Applications\BizTalk Application 1\Role Links**.</span></span> <span data-ttu-id="c0138-155">Haga doble clic en **ShipmentRole** y observe **ShipmentAgency1** asignado a la **SupplierAdvice** operación y **ShipmentAgency2** asignado a la **SupplierOrder** operación en la inscripción.</span><span class="sxs-lookup"><span data-stu-id="c0138-155">Double-click **ShipmentRole** and notice **ShipmentAgency1** mapped to the **SupplierAdvice** operation and **ShipmentAgency2** mapped to the **SupplierOrder** operation in the enlistment.</span></span>  

5. <span data-ttu-id="c0138-156">En la ventana de comandos, presione ENTRAR para permitir que el ejemplo dé de baja y elimine la nueva entidad.</span><span class="sxs-lookup"><span data-stu-id="c0138-156">In the command window, press ENTER to allow the sample to un-enlist and delete the new party.</span></span>  

6. <span data-ttu-id="c0138-157">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de consola, compruebe que la entidad ha desde el **ShipmentRole** y eliminadas desde la **partes** nodo.</span><span class="sxs-lookup"><span data-stu-id="c0138-157">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, verify the party was un-enlisted from the **ShipmentRole** and deleted from the **Parties** node.</span></span>  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="c0138-158">Ejemplo de un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0138-158">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="c0138-159">El siguiente ejemplo de script de Windows PowerShell se puede usar para mostrar las mismas características de la **ExplorerOM** clases:</span><span class="sxs-lookup"><span data-stu-id="c0138-159">The following Windows PowerShell script example can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  

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

 <span data-ttu-id="c0138-160">A continuación se proporciona el resultado de la ejecución del script de ejemplo de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0138-160">Here is example output from running the PowerShell example script.</span></span> <span data-ttu-id="c0138-161">Si no se ejecuta el script, asegúrese de que el script de PowerShell está habilitado según la nota de requisitos que aparece en la parte superior de este tema.</span><span class="sxs-lookup"><span data-stu-id="c0138-161">If the script fails to run, make sure PowerShell scripting is enabled according to the requirements note at the top of this topic.</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="c0138-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0138-162">See Also</span></span>  
 <span data-ttu-id="c0138-163">[Partes](../core/parties.md) </span><span class="sxs-lookup"><span data-stu-id="c0138-163">[Parties](../core/parties.md) </span></span>  
 <span data-ttu-id="c0138-164">[Vínculos de rol y Roles de vínculo de servicio](../core/role-links-and-service-link-roles.md) </span><span class="sxs-lookup"><span data-stu-id="c0138-164">[Role Links and Service Link Roles](../core/role-links-and-service-link-roles.md) </span></span>  
 [<span data-ttu-id="c0138-165">Admin (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="c0138-165">Admin (BizTalk Server Samples Folder)</span></span>](../core/admin-biztalk-server-samples-folder.md)