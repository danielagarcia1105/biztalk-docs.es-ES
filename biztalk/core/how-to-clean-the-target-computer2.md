---
title: "Cómo limpiar el Equipo2 destino | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: cleaning target computer
ms.assetid: 0d25930e-0bee-4658-80e7-4a1ab4a8131d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b15614af9a42489693d535896245254208379d76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-clean-the-target-computer"></a><span data-ttu-id="b7fa0-102">Cómo limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="b7fa0-102">How to Clean the Target Computer</span></span>
<span data-ttu-id="b7fa0-103">Implementación sobrescribe la configuración de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="b7fa0-103">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="b7fa0-104">Al implementar un archivo de enlace (y el ensamblado) en un equipo de destino, los puertos de envío y ubicaciones de recepción se sustituyen por los en el archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="b7fa0-104">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="b7fa0-105">Para limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="b7fa0-105">To clean the target computer</span></span>  
  
-   <span data-ttu-id="b7fa0-106">Quite los puertos de envío y las ubicaciones de recepción vinculadas a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="b7fa0-106">Remove any send ports and receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="b7fa0-107">Si no tiene Microsoft Visual Studio instalada en el equipo de destino, puede quitar los puertos ejecutando estas secuencias de comandos:</span><span class="sxs-lookup"><span data-stu-id="b7fa0-107">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
     <span data-ttu-id="b7fa0-108">\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove enviar Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="b7fa0-108">\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     <span data-ttu-id="b7fa0-109">\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove recibir Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="b7fa0-109">\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="b7fa0-110">Por ejemplo, en un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b7fa0-110">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="b7fa0-111">**cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío >**</span><span class="sxs-lookup"><span data-stu-id="b7fa0-111">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7fa0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7fa0-112">See Also</span></span>  
 [<span data-ttu-id="b7fa0-113">Implementación de puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="b7fa0-113">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies2.md)