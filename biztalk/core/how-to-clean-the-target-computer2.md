---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 93cb3a1420b60183ff42108c32224cf4707b9cd7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-clean-the-target-computer"></a><span data-ttu-id="770f1-101">Cómo limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="770f1-101">How to Clean the Target Computer</span></span>
<span data-ttu-id="770f1-102">Implementación sobrescribe la configuración de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="770f1-102">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="770f1-103">Al implementar un archivo de enlace (y el ensamblado) en un equipo de destino, los puertos de envío y ubicaciones de recepción se sustituyen por los en el archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="770f1-103">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="770f1-104">Para limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="770f1-104">To clean the target computer</span></span>  
  
-   <span data-ttu-id="770f1-105">Quite los puertos de envío y las ubicaciones de recepción vinculadas a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="770f1-105">Remove any send ports and receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="770f1-106">Si no tiene Microsoft Visual Studio instalada en el equipo de destino, puede quitar los puertos ejecutando estas secuencias de comandos:</span><span class="sxs-lookup"><span data-stu-id="770f1-106">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
     <span data-ttu-id="770f1-107">\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove enviar Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="770f1-107">\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     <span data-ttu-id="770f1-108">\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove recibir Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="770f1-108">\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="770f1-109">Por ejemplo, en un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="770f1-109">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="770f1-110">**cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío >**</span><span class="sxs-lookup"><span data-stu-id="770f1-110">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
