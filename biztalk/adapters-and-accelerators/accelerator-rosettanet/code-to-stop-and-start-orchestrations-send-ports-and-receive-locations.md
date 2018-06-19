---
title: Detener e iniciar orquestaciones, puertos de envío y ubicaciones de recepción mediante programación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- send ports, examples
- SDK samples, send ports
- examples, send ports
- SDK samples, orchestrations
- receive locations
- SDK samples, receive locations
- examples, receive locations
ms.assetid: 1c06e14d-44ec-4292-a2c2-ee2c8d07d948
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96b914129d9afb6dfd542f00a302e739e34dafbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210884"
---
# <a name="stopping-and-starting-orchestrations-send-ports-and-receive-locations-programmatically"></a><span data-ttu-id="7a08c-102">Detener e iniciar orquestaciones, puertos de envío y ubicaciones de recepción mediante programación</span><span class="sxs-lookup"><span data-stu-id="7a08c-102">Stopping and Starting Orchestrations, Send Ports, and Receive Locations Programmatically</span></span>
<span data-ttu-id="7a08c-103">Este tema proporciona código de ejemplo para detener mediante programación y a partir de orquestaciones, puertos de envío y ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="7a08c-103">This topic provides sample code for programmatically stopping and starting orchestrations, send ports, and receive locations.</span></span> <span data-ttu-id="7a08c-104">Puede realizar estas acciones en todas las orquestaciones, puertos de envío y recepción ubicaciones como un grupo o individualmente.</span><span class="sxs-lookup"><span data-stu-id="7a08c-104">You can perform these actions on all orchestrations, send ports, and receive locations as a group or individually.</span></span> <span data-ttu-id="7a08c-105">Puede incluir este código en un programa para realizar estas acciones de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="7a08c-105">You can include this code in a program to perform these actions dynamically.</span></span> <span data-ttu-id="7a08c-106">Realizar estas acciones en la interfaz gráfica de usuario en tiempo de diseño en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)], o en tiempo de ejecución en la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7a08c-106">You perform these actions in the graphical user interface at design time in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)], or at run time in the BizTalk Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a08c-107">Para que el código iniciar y detener orquestaciones, no es necesario designar las orquestaciones, puertos de envío o ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="7a08c-107">For the code to start and stop orchestrations, you do not have to designate the orchestrations, send ports, or receive locations.</span></span> <span data-ttu-id="7a08c-108">El código de ejemplo realiza la acción en todas las orquestaciones, puertos de envío y ubicaciones de recepción que [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] instalado en el conjunto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7a08c-108">The sample code performs the action on all orchestrations, send ports, and receive locations that [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] installed at set up.</span></span> <span data-ttu-id="7a08c-109">Para el código que actúa sobre una orquestación única, puerto de envío, ubicación de recepción, agregue un parámetro que indica en qué orquestación, puerto de envío o ubicación que desee para ejecutar el código de recepción.</span><span class="sxs-lookup"><span data-stu-id="7a08c-109">For the code that acts on a single orchestration, send port, or receive location, add a parameter indicating on which orchestration, send port, or receive location you want the code to run.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="7a08c-110">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="7a08c-110">Demonstrates</span></span>  
 <span data-ttu-id="7a08c-111">El código de ejemplo en este tema incluye las secciones de código independiente para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a08c-111">The sample code in this topic includes separate code sections to do the following:</span></span>  
  
-   <span data-ttu-id="7a08c-112">Iniciar orquestaciones: iniciar todos los puertos de envío y ubicaciones de recepción y dar de alta e iniciar todas las orquestaciones</span><span class="sxs-lookup"><span data-stu-id="7a08c-112">Start orchestrations—start all the send ports and receive locations, and enlist and start all orchestrations</span></span>  
  
-   <span data-ttu-id="7a08c-113">Detener orquestaciones, dar de baja todas las orquestaciones, dar de baja todos los puertos de envío y deshabilitar todas las ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="7a08c-113">Stop orchestrations—unenlist all orchestrations, unenlist all send ports, and disable all receive locations</span></span>  
  
-   <span data-ttu-id="7a08c-114">Iniciar un puerto de envío único</span><span class="sxs-lookup"><span data-stu-id="7a08c-114">Start a single send port</span></span>  
  
-   <span data-ttu-id="7a08c-115">Habilitar una única ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="7a08c-115">Enable a single receive location</span></span>  
  
-   <span data-ttu-id="7a08c-116">Dar de baja un puerto de envío único</span><span class="sxs-lookup"><span data-stu-id="7a08c-116">Unenlist a single send port</span></span>  
  
-   <span data-ttu-id="7a08c-117">Deshabilitar una única ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="7a08c-117">Disable a single receive location</span></span>  
  
-   <span data-ttu-id="7a08c-118">Iniciar una orquestación única</span><span class="sxs-lookup"><span data-stu-id="7a08c-118">Start a single orchestration</span></span>  
  
-   <span data-ttu-id="7a08c-119">Dar de baja una orquestación única</span><span class="sxs-lookup"><span data-stu-id="7a08c-119">Unenlist a single orchestration</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a08c-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a08c-120">Example</span></span>  
 <span data-ttu-id="7a08c-121">El código de ejemplo en este tema incluye las secciones de código independiente para realizar las funciones enumeradas en la sección "Demonstrates".</span><span class="sxs-lookup"><span data-stu-id="7a08c-121">The sample code in this topic includes separate code sections to do the functions listed in the "Demonstrates" section.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.ExplorerOM;  
  
namespace Control  
{  
class Control  
{  
BtsCatalogExplorer bceExplorer;  
string[] sOrchestrations;  
string[] sReceiveLocations;  
string[] sSendPorts;  
  
[STAThread]  
static void Main(string[] args)  
{  
Control controlInstance = new Control();  
if(args.Length>0 && args[0].ToUpper()=="STOP")  
controlInstance.StopOrchestrations();  
else  
controlInstance.StartOrchestrations();  
}  
  
public Control()  
{  
bceExplorer = new BtsCatalogExplorer();  
//Edit the following connection string to point to the correct database and server  
bceExplorer.ConnectionString = "Integrated Security=SSPI;database=BizTalkMgmtDb;server=localhost";  
  
//Orchestrations  
sOrchestrations = new string[9];  
sOrchestrations[0]="Microsoft.Solutions.BTARN.CommonTypes.OdxTypes,Microsoft.Solutions.BTARN.CommonTypes, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[1]="Microsoft.Solutions.BTARN.CommonTypes.SendExceptionToLOB,Microsoft.Solutions.BTARN.CommonTypes, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[2]="Microsoft.Solutions.BTARN.CommonTypes.SendExceptionToPrivateProcess,Microsoft.Solutions.BTARN.CommonTypes, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[3]="Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess,Microsoft.Solutions.BTARN.PrivateInitiator, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[4]="Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess,Microsoft.Solutions.BTARN.PrivateResponder, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[5]="Microsoft.Solutions.BTARN.PublicInitiator.PublicInitiatorV11,Microsoft.Solutions.BTARN.PublicInitiator, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[6]="Microsoft.Solutions.BTARN.PublicInitiator.PublicInitiatorProcess,Microsoft.Solutions.BTARN.PublicInitiator, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[7]="Microsoft.Solutions.BTARN.PublicResponder.PublicResponderV11,Microsoft.Solutions.BTARN.PublicResponder, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[8]="Microsoft.Solutions.BTARN.PublicResponder.PublicResponderProcess,Microsoft.Solutions.BTARN.PublicResponder, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
  
//Send Ports  
sSendPorts = new string[2];  
sSendPorts[0]="PrivateInitiator_To_LOB";  
sSendPorts[1]="PrivateResponder_To_LOB";  
  
//Receive Locations  
sReceiveLocations = new string[4];  
sReceiveLocations[0]="LOB_To_PrivateInitiator";  
sReceiveLocations[1]="LOB_To_PrivateResponder";  
sReceiveLocations[2]="RNIF_Async_Receive";  
sReceiveLocations[3]="RNIF_Sync_Receive";  
}  
  
public void StartOrchestrations()  
{     
bool bSuccess=true;  
  
//Start all the send ports  
for(int i=0;i<sSendPorts.Length;i++)  
{  
Console.WriteLine("Starting send port: " + sSendPorts[i]);  
bSuccess=StartSendPort(sSendPorts[i]);  
}  
  
//Start all the receive locations  
for(int i=0;i<sReceiveLocations.Length;i++)  
{  
Console.WriteLine("Enabling receive location: " + sReceiveLocations[i]);  
bSuccess=EnableReceiveLocation(sReceiveLocations[i]);  
}  
  
//Enlist and start all orchestrations  
for(int i=0;i<sOrchestrations.Length;i++)  
{  
Console.WriteLine("Starting orchestration: " + sOrchestrations[i].Split(',')[0]);  
bSuccess=StartOrchestration(sOrchestrations[i]);  
}  
  
if(bSuccess)  
Console.WriteLine("All artifacts successfully started");  
else  
Console.WriteLine("Not all artifacts were started");  
}  
  
public void StopOrchestrations()  
{     
bool bSuccess=true;  
  
//Unenlist all orchestrations  
for(int i=sOrchestrations.Length-1;i>=0;i--)  
{  
Console.WriteLine("Unelisting orchestration: " + sOrchestrations[i].Split(',')[0]);  
bSuccess=UnenlistOrchestration(sOrchestrations[i]);  
}  
  
//Unenlist all the send ports  
for(int i=sSendPorts.Length-1;i>=0;i--)  
{  
Console.WriteLine("Unenlisting send port: " + sSendPorts[i]);  
bSuccess=UnenlistSendPort(sSendPorts[i]);  
}  
  
//Disable all the receive locations  
for(int i=sReceiveLocations.Length-1;i>=0;i--)  
{  
Console.WriteLine("Disabling receive location: " + sReceiveLocations[i]);  
bSuccess=DisableReceiveLocation(sReceiveLocations[i]);  
}  
  
if(bSuccess)  
Console.WriteLine("All artifacts successfully stopped");  
else  
Console.WriteLine("Not all artifacts were stopped");  
}  
  
public bool StartSendPort(string sSendPortName)  
{  
try  
{  
SendPort sp = bceExplorer.SendPorts[sSendPortName];  
sp.Status = PortStatus.Started;  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
public bool EnableReceiveLocation(string sReceivePortName)  
{  
try  
{  
ReceivePort rp = bceExplorer.ReceivePorts[sReceivePortName];  
              foreach(ReceiveLocation rl in rp.ReceiveLocations)  
rl.Enable = true;  
  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
public bool UnenlistSendPort(string sSendPortName)  
{  
try  
{  
SendPort sp = bceExplorer.SendPorts[sSendPortName];  
sp.Status = PortStatus.Bound;  
  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
public bool DisableReceiveLocation(string sReceivePortName)  
{  
try  
{  
ReceivePort rp = bceExplorer.ReceivePorts[sReceivePortName];  
  
foreach(ReceiveLocation rl in rp.ReceiveLocations)  
rl.Enable = false;  
  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
private bool StartOrchestration(string sOrchestrationName)  
{  
  
BtsAssemblyCollection btsAssemblyCollection = bceExplorer.Assemblies;  
  
foreach (Microsoft.BizTalk.ExplorerOM.BtsAssembly btsAssembly in btsAssemblyCollection)  
{  
if(sOrchestrationName.Split(',')[1]==btsAssembly.DisplayName.Split(',')[0])  
{  
foreach (Microsoft.BizTalk.ExplorerOM.BtsOrchestration btsOrchestration in btsAssembly.Orchestrations)  
{  
if(sOrchestrationName==btsOrchestration.AssemblyQualifiedName)  
{  
btsOrchestration.Status=OrchestrationStatus.Started;  
try  
{  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
}  
}  
}  
return false;  
}  
  
private bool UnenlistOrchestration(string sOrchestrationName)  
{  
  
BtsAssemblyCollection btsAssemblyCollection = bceExplorer.Assemblies;  
  
foreach (Microsoft.BizTalk.ExplorerOM.BtsAssembly btsAssembly in btsAssemblyCollection)  
{  
if(sOrchestrationName.Split(',')[1]==btsAssembly.DisplayName.Split(',')[0])  
{  
foreach (Microsoft.BizTalk.ExplorerOM.BtsOrchestration btsOrchestration in btsAssembly.Orchestrations)  
{  
if(sOrchestrationName==btsOrchestration.AssemblyQualifiedName)  
{  
btsOrchestration.AutoTerminateInstances=true;  
btsOrchestration.Status=OrchestrationStatus.Unenlisted;  
try  
{  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
}  
}  
}  
return false;  
}  
  
}  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a08c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a08c-122">See Also</span></span>  
 [<span data-ttu-id="7a08c-123">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7a08c-123">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)