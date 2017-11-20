---
title: Importar enlaces para TIBCO Rendezvous | Documentos de Microsoft
description: "Implementar el adaptador de BizTalk para aplicaciones de TIBCO Rendezvous mediante la característica Importar enlaces en BizTalk Server"
ms.custom: 
ms.date: 10/24/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec5751a9-0a08-4cf8-a3ef-e51e488a4180
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e880bcbce388bb15924e96739c8bb617c04d0e24
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="deploy-tibco-rendezvous-ports-and-assemblies"></a><span data-ttu-id="8af53-103">Implementar ensamblados y puertos de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="8af53-103">Deploy TIBCO Rendezvous ports and assemblies</span></span>
  
## <a name="overview"></a><span data-ttu-id="8af53-104">Información general</span><span class="sxs-lookup"><span data-stu-id="8af53-104">Overview</span></span>
<span data-ttu-id="8af53-105">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede duplicar puertos y ensamblados en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="8af53-105">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="8af53-106">El asistente exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="8af53-106">The wizard exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="8af53-107">Mediante BizTalk Server se pueden realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="8af53-107">You use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="8af53-108">Implementar o quitar ensamblados de BizTalk Server en una base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8af53-108">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="8af53-109">Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="8af53-109">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="8af53-110">Importar o exportar información de enlace de ensamblado de BizTalk Server desde archivos de enlace o a archivos de enlace.</span><span class="sxs-lookup"><span data-stu-id="8af53-110">Import or export BizTalk Server assembly binding information to and from binding files.</span></span>  
  
 <span data-ttu-id="8af53-111">Para obtener información sobre cómo usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="8af53-111">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8af53-112">El adaptador de Microsoft BizTalk para TIBCO Rendezvous solo necesita que tenga Visual Studio en un equipo de origen (desarrollo).</span><span class="sxs-lookup"><span data-stu-id="8af53-112">Microsoft BizTalk Adapter for TIBCO Rendezvous only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="8af53-113">Visual Studio no es necesario en el equipo de producción.</span><span class="sxs-lookup"><span data-stu-id="8af53-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="8af53-114">Confirme la configuración</span><span class="sxs-lookup"><span data-stu-id="8af53-114">Confirm your setup</span></span>

<span data-ttu-id="8af53-115">Antes de usar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para importar un archivo de enlace, confirme que las carpetas para las respuestas existen y que son idénticas en el nuevo equipo o debe editar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="8af53-115">Before you use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, confirm that the folders for the responses exist, and that they are identical on the new computer, or you must edit the binding file.</span></span>  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="8af53-116">Limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="8af53-116">Clean the target computer</span></span>
<span data-ttu-id="8af53-117">Implementación sobrescribe la configuración de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="8af53-117">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="8af53-118">Al implementar un archivo de enlace (y el ensamblado) en un equipo de destino, los puertos de envío y ubicaciones de recepción se sustituyen por los en el archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="8af53-118">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
<span data-ttu-id="8af53-119">Antes de importar, quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="8af53-119">Before you import, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="8af53-120">Si no tiene Microsoft Visual Studio instalada en el equipo de destino, puede quitar los puertos ejecutando estas secuencias de comandos:</span><span class="sxs-lookup"><span data-stu-id="8af53-120">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="8af53-121">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="8af53-121">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="8af53-122">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="8af53-122">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
<span data-ttu-id="8af53-123">Por ejemplo, en un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="8af53-123">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name>
```
  
## <a name="next-steps"></a><span data-ttu-id="8af53-124">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8af53-124">Next steps</span></span>
[<span data-ttu-id="8af53-125">Usar el control de excepciones de BizTalk Server en la orquestación</span><span class="sxs-lookup"><span data-stu-id="8af53-125">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling4.md)  
[<span data-ttu-id="8af53-126">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="8af53-126">Troubleshoot</span></span>](../core/troubleshooting-tibco-rendezvous.md)