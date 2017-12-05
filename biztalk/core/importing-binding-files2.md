---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 7dbc9ef8624404b9fa7bdcb7b6a21b2d2a4c69f2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="b84cb-101">Importar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="b84cb-101">Importing Binding Files</span></span>
<span data-ttu-id="b84cb-102">En este tema se proporciona información relativa al proceso de importación al implementar BizTalk Adapter para JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="b84cb-102">This topic provides some information concerning the import process when you deploy BizTalk Adapter for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="b84cb-103">Al volver a implementar un archivo de enlace (y un ensamblado) en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se vuelven a importar.</span><span class="sxs-lookup"><span data-stu-id="b84cb-103">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="b84cb-104">Para limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="b84cb-104">To clean the target computer</span></span>  
  
-   <span data-ttu-id="b84cb-105">Quite los puertos de envío y las ubicaciones de recepción vinculados a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="b84cb-105">Remove Send ports and Receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="b84cb-106">Si Visual Studio no está instalado en el equipo de destino, puede quitar los puertos ejecutando estos scripts:</span><span class="sxs-lookup"><span data-stu-id="b84cb-106">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="b84cb-107">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="b84cb-107">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="b84cb-108">Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="b84cb-108">Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="b84cb-109">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="b84cb-109">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="b84cb-110">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="b84cb-110">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="b84cb-111">Por ejemplo, desde un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b84cb-111">For example, from a command prompt run:</span></span>  
  
     <span data-ttu-id="b84cb-112">**cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío\>**</span><span class="sxs-lookup"><span data-stu-id="b84cb-112">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b84cb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b84cb-113">See Also</span></span>  
 [<span data-ttu-id="b84cb-114">Importar JD Edwards EnterpriseOne aplicación</span><span class="sxs-lookup"><span data-stu-id="b84cb-114">Import the JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)