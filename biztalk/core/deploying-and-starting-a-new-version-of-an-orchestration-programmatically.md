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
# <a name="deploying-and-starting-a-new-version-of-an-orchestration-programmatically"></a>Implementar e iniciar una nueva versión de una orquestación mediante programación
El código de este tema ilustra cómo implementar e iniciar una nueva versión de la orquestación rápidamente. Puesto que las operaciones manuales pueden tardar varios segundos en llevarse a cabo, dar de baja una orquestación manualmente y después iniciar una nueva versión de ésta puede producir mensajes suspendidos o duplicados. El método mediante programación que se ilustra en este tema le permite llevar a cabo estas operaciones de un modo mucho más rápido y como una sola transacción, lo que reduce las probabilidades de generar mensajes suspendidos y duplicados, de modo que, si se produce un error en una transacción, ambas orquestaciones se mantienen en el estado que tenían al principio.  
  
> [!NOTE]
>  En raras ocasiones, cuando la orquestación que se va a actualizar con una nueva versión funciona bajo una carga alta, algunos mensajes pueden convertirse en suspende incluso al dar de baja y dar de alta las orquestaciones mediante programación.  Se recomienda que después de realizar estas operaciones, compruebe la cola de mensajes suspendidos y reanudar cualquier mensaje suspendido.  
  
 El siguiente ejemplo de código ilustra cómo usar la interfaz API del modelo de objetos del Explorador para dar de baja una orquestación existente e iniciar la nueva versión de la orquestación.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md)   
 [Cómo dar de alta una orquestación](../core/how-to-enlist-an-orchestration.md)   
 [Cómo dar de baja una orquestación](../core/how-to-unenlist-an-orchestration.md)