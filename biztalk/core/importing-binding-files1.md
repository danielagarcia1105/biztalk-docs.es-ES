---
title: "Importación de enlace Files1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- CLASSPATH environment variable
- importing binding files
- cleaning target computer
ms.assetid: b2a9b19b-2d3d-45ea-bd92-a2501791b86a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fca64580b692f01834b48085aa2d88085fb743
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="7b054-102">Importar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="7b054-102">Importing Binding Files</span></span>
<span data-ttu-id="7b054-103">Antes de usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para importar un archivo de enlace, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b054-103">Before you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="7b054-104">CLASSPATH apunta a una ubicación concreta para los archivos específicos de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="7b054-104">The CLASSPATH is pointing to a specific location for the PeopleSoft-specific files.</span></span> <span data-ttu-id="7b054-105">Compruebe que la ubicación de estos archivos es el mismo en el nuevo equipo, o editar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="7b054-105">Verify that the location of these files is the same on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="7b054-106">Las carpetas para las respuestas deben existir y ser idénticas en el equipo nuevo, o editar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="7b054-106">The folders for the responses must exist and be identical on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="7b054-107">Las contraseñas del sistema PeopleSoft Enterprise, si están presentes en la configuración, se guardan como ***** en el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="7b054-107">PeopleSoft Enterprise system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> <span data-ttu-id="7b054-108">Para obtener más información, consulte [limitaciones de la implementación](../core/deployment-limitations3.md).</span><span class="sxs-lookup"><span data-stu-id="7b054-108">For more information, see [Deployment Limitations](../core/deployment-limitations3.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b054-109">La implementación sobrescribe la configuración de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="7b054-109">Deployment overwrites receive location configuration.</span></span> <span data-ttu-id="7b054-110">Al implementar un archivo de enlace y un ensamblado en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="7b054-110">When you deploy a binding file and assembly on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
 <span data-ttu-id="7b054-111">Para obtener instrucciones detalladas sobre la importación de archivos de enlace, consulte el tema "Cómo importar enlaces a un grupo de BizTalk" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b054-111">For step-by-step directions about importing binding files, see the topic "How to Import Bindings into a BizTalk Group" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
## <a name="cleaning-the-target-computer"></a><span data-ttu-id="7b054-112">Limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="7b054-112">Cleaning the Target Computer</span></span>  
 <span data-ttu-id="7b054-113">Para limpiar el equipo de destino e implementar la nueva aplicación, lleve a cabo los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="7b054-113">Follow these steps to clean the target computer for deploying the new application.</span></span>  
  
#### <a name="to-clean-the-target-computer"></a><span data-ttu-id="7b054-114">Para limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="7b054-114">To clean the target computer</span></span>  
  
-   <span data-ttu-id="7b054-115">Quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="7b054-115">Remove send ports and receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="7b054-116">Si Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no está instalado en el equipo de destino, puede ejecutar estos scripts para quitar los puertos:</span><span class="sxs-lookup"><span data-stu-id="7b054-116">If you do not have Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed on the target computer, you may remove the ports by running these scripts:</span></span>  
  
     <span data-ttu-id="7b054-117">**\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove enviar Port\VBScript\RemoveSendPort.vbs**</span><span class="sxs-lookup"><span data-stu-id="7b054-117">**\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span></span>  
  
     <span data-ttu-id="7b054-118">**\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove recibir Port\VBScript\RemoveReceivePort.vbs**</span><span class="sxs-lookup"><span data-stu-id="7b054-118">**\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span></span>  
  
     <span data-ttu-id="7b054-119">Por ejemplo, en un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="7b054-119">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="7b054-120">**cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío >**</span><span class="sxs-lookup"><span data-stu-id="7b054-120">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b054-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b054-121">See Also</span></span>  
 [<span data-ttu-id="7b054-122">Implementación de puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="7b054-122">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies5.md)