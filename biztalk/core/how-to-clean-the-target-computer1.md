---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 12e8a37da357693b97659c1717ead750e558e62b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018447"
---
# <a name="how-to-clean-the-target-computer"></a><span data-ttu-id="6738a-101">Cómo limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="6738a-101">How to Clean the Target Computer</span></span>
<span data-ttu-id="6738a-102">Implementación sobrescribe la configuración de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="6738a-102">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="6738a-103">Al implementar un archivo de enlace (y el ensamblado) en un equipo de destino, los puertos de envío y ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="6738a-103">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="6738a-104">Para limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="6738a-104">To clean the target computer</span></span>  
  
- <span data-ttu-id="6738a-105">Quite los puertos de envío y enlazadas a la orquestación de las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="6738a-105">Remove send ports and receive locations bound to the orchestration.</span></span>  
  
   <span data-ttu-id="6738a-106">Si no tiene Microsoft Visual Studio instalada en el equipo de destino, puede quitar los puertos ejecutando estas secuencias de comandos:</span><span class="sxs-lookup"><span data-stu-id="6738a-106">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
  - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="6738a-107">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="6738a-107">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
  - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="6738a-108">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="6738a-108">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="6738a-109">Por ejemplo, en un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6738a-109">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="6738a-110">**cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío\>**</span><span class="sxs-lookup"><span data-stu-id="6738a-110">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
