---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 907c21377a6affd5a99576137a5babaa1626c135
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="import-binding-files"></a><span data-ttu-id="f253e-101">Importar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="f253e-101">Import Binding Files</span></span>

## <a name="overview"></a><span data-ttu-id="f253e-102">Información general</span><span class="sxs-lookup"><span data-stu-id="f253e-102">Overview</span></span>
<span data-ttu-id="f253e-103">Antes de usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para importar un archivo de enlace, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f253e-103">Before you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="f253e-104">CLASSPATH apunta a una ubicación concreta para los archivos específicos de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="f253e-104">The CLASSPATH is pointing to a specific location for the PeopleSoft-specific files.</span></span> <span data-ttu-id="f253e-105">Compruebe que la ubicación de estos archivos es el mismo en el nuevo equipo, o editar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="f253e-105">Verify that the location of these files is the same on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="f253e-106">Las carpetas para las respuestas deben existir y ser idénticas en el equipo nuevo, o editar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="f253e-106">The folders for the responses must exist and be identical on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="f253e-107">Las contraseñas del sistema PeopleSoft Enterprise, si están presentes en la configuración, se guardan como ***** en el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="f253e-107">PeopleSoft Enterprise system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="f253e-108">La implementación sobrescribe la configuración de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="f253e-108">Deployment overwrites receive location configuration.</span></span> <span data-ttu-id="f253e-109">Al implementar un archivo de enlace y un ensamblado en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="f253e-109">When you deploy a binding file and assembly on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
 <span data-ttu-id="f253e-110">Para obtener instrucciones detalladas sobre la importación de archivos de enlace, consulte el tema "Cómo importar enlaces a un grupo de BizTalk" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f253e-110">For step-by-step directions about importing binding files, see the topic "How to Import Bindings into a BizTalk Group" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="f253e-111">Limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="f253e-111">Clean the Target Computer</span></span>  
<span data-ttu-id="f253e-112">Para limpiar el equipo de destino para la implementación de la nueva aplicación, quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f253e-112">To clean the target computer for deploying the new application, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="f253e-113">Si Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no está instalado en el equipo de destino, puede ejecutar estos scripts para quitar los puertos:</span><span class="sxs-lookup"><span data-stu-id="f253e-113">If you do not have Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed on the target computer, you may remove the ports by running these scripts:</span></span>  
  
<span data-ttu-id="f253e-114">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove enviar Port\VBScript\RemoveSendPort.vbs**</span><span class="sxs-lookup"><span data-stu-id="f253e-114">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span></span>  
  
<span data-ttu-id="f253e-115">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove recibir Port\VBScript\RemoveReceivePort.vbs**</span><span class="sxs-lookup"><span data-stu-id="f253e-115">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span></span>  
  
<span data-ttu-id="f253e-116">Por ejemplo, en un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f253e-116">For example, at a command prompt, run:</span></span>  
  
<span data-ttu-id="f253e-117">**cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío\>**</span><span class="sxs-lookup"><span data-stu-id="f253e-117">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
