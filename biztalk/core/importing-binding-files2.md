---
title: "Importación de enlace alternativos2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- assemblies, removing from database
- importing binding files
- target computers, cleaning
- BizTalk assemblies, removing from database
ms.assetid: 9e552a4b-06ec-4887-b17b-a625c137699f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3783b21385c210c454bcd3d4c951f2200a6ec866
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="dd97b-102">Importar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="dd97b-102">Importing Binding Files</span></span>
<span data-ttu-id="dd97b-103">En este tema se proporciona información relativa al proceso de importación al implementar BizTalk Adapter para JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="dd97b-103">This topic provides some information concerning the import process when you deploy BizTalk Adapter for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="dd97b-104">Al volver a implementar un archivo de enlace (y un ensamblado) en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se vuelven a importar.</span><span class="sxs-lookup"><span data-stu-id="dd97b-104">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="dd97b-105">Para limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="dd97b-105">To clean the target computer</span></span>  
  
-   <span data-ttu-id="dd97b-106">Quite los puertos de envío y las ubicaciones de recepción vinculados a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="dd97b-106">Remove Send ports and Receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="dd97b-107">Si Visual Studio no está instalado en el equipo de destino, puede quitar los puertos ejecutando estos scripts:</span><span class="sxs-lookup"><span data-stu-id="dd97b-107">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="dd97b-108">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="dd97b-108">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="dd97b-109">Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="dd97b-109">Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="dd97b-110">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="dd97b-110">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="dd97b-111">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="dd97b-111">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="dd97b-112">Por ejemplo, desde un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="dd97b-112">For example, from a command prompt run:</span></span>  
  
     <span data-ttu-id="dd97b-113">**cscript comandos RemoveSendPort.vbs \<nombre de puerto de envío >**</span><span class="sxs-lookup"><span data-stu-id="dd97b-113">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd97b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd97b-114">See Also</span></span>  
 [<span data-ttu-id="dd97b-115">Implementación de puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="dd97b-115">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies3.md)