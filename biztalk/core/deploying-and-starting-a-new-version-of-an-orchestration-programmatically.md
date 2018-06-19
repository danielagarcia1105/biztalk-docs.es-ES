---
title: Implementar e iniciar una nueva versión de una orquestación mediante programación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f90025ec-3641-49ef-8918-88238d6ad420
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26887b70a09d4a7af8d41a4385dffda20e964690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239028"
---
# <a name="deploying-and-starting-a-new-version-of-an-orchestration-programmatically"></a><span data-ttu-id="04c2d-102">Implementar e iniciar una nueva versión de una orquestación mediante programación</span><span class="sxs-lookup"><span data-stu-id="04c2d-102">Deploying and Starting a New Version of an Orchestration Programmatically</span></span>
<span data-ttu-id="04c2d-103">El código de este tema ilustra cómo implementar e iniciar una nueva versión de la orquestación rápidamente.</span><span class="sxs-lookup"><span data-stu-id="04c2d-103">The code in this topic illustrates how to quickly deploy and start a new version of the orchestration.</span></span> <span data-ttu-id="04c2d-104">Puesto que las operaciones manuales pueden tardar varios segundos en llevarse a cabo, dar de baja una orquestación manualmente y después iniciar una nueva versión de ésta puede producir mensajes suspendidos o duplicados.</span><span class="sxs-lookup"><span data-stu-id="04c2d-104">Because manual operations can take a few seconds to perform, manually unenlisting an orchestration and then starting a new version of it can result in suspended or duplicate messages.</span></span> <span data-ttu-id="04c2d-105">El método mediante programación que se ilustra en este tema le permite llevar a cabo estas operaciones de un modo mucho más rápido y como una sola transacción, lo que reduce las probabilidades de generar mensajes suspendidos y duplicados, de modo que, si se produce un error en una transacción, ambas orquestaciones se mantienen en el estado que tenían al principio.</span><span class="sxs-lookup"><span data-stu-id="04c2d-105">The programmatic method illustrated in this topic allows you to perform these operations much more quickly – reducing the likelihood of suspended and duplicate messages – and as a single transaction, so that if one operation fails, both orchestrations are left in the same state as they were at the beginning.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04c2d-106">En raras ocasiones, cuando la orquestación que se va a actualizar con una nueva versión funciona bajo una carga alta, algunos mensajes pueden convertirse en suspende incluso al dar de baja y dar de alta las orquestaciones mediante programación.</span><span class="sxs-lookup"><span data-stu-id="04c2d-106">In rare cases, when the orchestration you are updating with a new version is operating under high load, some messages can become suspended even when you unenlist and enlist the orchestrations programmatically.</span></span>  <span data-ttu-id="04c2d-107">Se recomienda que después de realizar estas operaciones, compruebe la cola de mensajes suspendidos y reanudar cualquier mensaje suspendido.</span><span class="sxs-lookup"><span data-stu-id="04c2d-107">We recommend that after performing these operations, you check your suspended message queue and resume any suspended messages.</span></span>  
  
 <span data-ttu-id="04c2d-108">El siguiente ejemplo de código ilustra cómo usar la interfaz API del modelo de objetos del Explorador para dar de baja una orquestación existente e iniciar la nueva versión de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="04c2d-108">The following code sample illustrates how to use the Explorer OM API to unenlist an existing orchestration and start the new version of the orchestration.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.ExplorerOM;  
#endregion  
namespace OrchestrationBinding  
{  
class OrchestrationBinding  
{  
static void Main(string[] args)  
{  
            UpdateOrchestration();  
}  
        static public void UpdateOrchestration()  
        {  
            // Create the root object and set the connection string  
            BtsCatalogExplorer catalog = new BtsCatalogExplorer();  
            catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI";  
            string orchestrationAssemblyV1 = "HelloWorld, Version=1.0.0.0, Culture=neutral, PublicKeyToken=99561c477e487f14";  
            string orchestrationAssemblyV2 = "HelloWorld, Version=2.0.0.0, Culture=neutral, PublicKeyToken=99561c477e487f14";  
            string orchestrationName = "Microsoft.Samples.BizTalk.HelloWorld.HelloSchedule";  
            try  
            {  
                BtsAssembly assemblyV1 = FindAssemblyByFullName(catalog.Assemblies, orchestrationAssemblyV1);  
                BtsAssembly assemblyV2 = FindAssemblyByFullName(catalog.Assemblies, orchestrationAssemblyV2);  
                BtsOrchestration orchestrationV1 = assemblyV1.Orchestrations[orchestrationName];  
                BtsOrchestration orchestrationV2 = assemblyV2.Orchestrations[orchestrationName];  
                orchestrationV1.Status = OrchestrationStatus.Unenlisted;  
                orchestrationV2.Status = OrchestrationStatus.Started;  
                // Commit the accumulated changes transactionally  
                catalog.SaveChanges();  
            }  
            catch (Exception e)  
            {  
                catalog.DiscardChanges();  
                throw;  
            }  
        }  
        static BtsAssembly FindAssemblyByFullName(BtsAssemblyCollection assemblies, string fullName)  
        {  
            foreach (BtsAssembly assembly in assemblies)  
            {  
                if (assembly.DisplayName == fullName)  
                    return assembly;  
            }  
            return null;  
        }  
}  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="04c2d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="04c2d-109">See Also</span></span>  
 <span data-ttu-id="04c2d-110">[Actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="04c2d-110">[Updating BizTalk Applications](../core/updating-biztalk-applications.md) </span></span>  
 <span data-ttu-id="04c2d-111">[Cómo dar de alta una orquestación](../core/how-to-enlist-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="04c2d-111">[How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) </span></span>  
 [<span data-ttu-id="04c2d-112">Cómo dar de baja una orquestación</span><span class="sxs-lookup"><span data-stu-id="04c2d-112">How to Unenlist an Orchestration</span></span>](../core/how-to-unenlist-an-orchestration.md)