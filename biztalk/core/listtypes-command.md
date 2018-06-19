---
title: El comando ListTypes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94febe8a-4c1e-4581-a6d1-ef579633e745
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe2519fc5507ae0975d050a998faec78f2940a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262220"
---
# <a name="listtypes-command"></a><span data-ttu-id="176e6-102">ListTypes (comando)</span><span class="sxs-lookup"><span data-stu-id="176e6-102">ListTypes Command</span></span>
<span data-ttu-id="176e6-103">Enumera todos los tipos de artefactos que se pueden agregar a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el uso de la **AddResource** comando.</span><span class="sxs-lookup"><span data-stu-id="176e6-103">Lists all of the artifact types that you can add to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the **AddResource** command.</span></span> <span data-ttu-id="176e6-104">Para obtener más información sobre la **AddResource** command, consulte [comando AddResource](../core/addresource-command.md).</span><span class="sxs-lookup"><span data-stu-id="176e6-104">For more information about the **AddResource** command, see [AddResource Command](../core/addresource-command.md).</span></span>  
  
 <span data-ttu-id="176e6-105">Los nombres completos de los tipos de artefactos compatibles son los que se muestran a continuación:</span><span class="sxs-lookup"><span data-stu-id="176e6-105">The fully qualified names of the supported artifact types are as follows:</span></span>  
  
-   <span data-ttu-id="176e6-106">Ensamblado .NET: System.BizTalk:Assembly</span><span class="sxs-lookup"><span data-stu-id="176e6-106">.NET assembly: System.BizTalk:Assembly</span></span>  
  
-   <span data-ttu-id="176e6-107">Definición de BAM: BizTalk: BAM</span><span class="sxs-lookup"><span data-stu-id="176e6-107">BAM definition: System.BizTalk:Bam</span></span>  
  
-   <span data-ttu-id="176e6-108">Ensamblado de BizTalk: System.BizTalk:BizTalkAssembly</span><span class="sxs-lookup"><span data-stu-id="176e6-108">BizTalk assembly: System.BizTalk:BizTalkAssembly</span></span>  
  
-   <span data-ttu-id="176e6-109">Archivo de enlace de BizTalk: BizTalk: biztalkbinding</span><span class="sxs-lookup"><span data-stu-id="176e6-109">BizTalk binding file: System.BizTalk:BizTalkBinding</span></span>  
  
-   <span data-ttu-id="176e6-110">Certificado de seguridad: System.BizTalk:Certificate</span><span class="sxs-lookup"><span data-stu-id="176e6-110">Security certificate: System.BizTalk:Certificate</span></span>  
  
-   <span data-ttu-id="176e6-111">Componente COM: BizTalk: com</span><span class="sxs-lookup"><span data-stu-id="176e6-111">COM component: System.BizTalk:Com</span></span>  
  
-   <span data-ttu-id="176e6-112">Archivo ad hoc: BizTalk: File</span><span class="sxs-lookup"><span data-stu-id="176e6-112">Ad hoc file: System.BizTalk:File</span></span>  
  
-   <span data-ttu-id="176e6-113">Secuencias posteriores al procesamiento de secuencia de comandos: System.BizTalk:PostProcessingScript</span><span class="sxs-lookup"><span data-stu-id="176e6-113">Postprocessing script: System.BizTalk:PostProcessingScript</span></span>  
  
-   <span data-ttu-id="176e6-114">Secuencia de comandos de preprocesamiento: System.BizTalk:PreProcessingScript</span><span class="sxs-lookup"><span data-stu-id="176e6-114">Preprocessing script: System.BizTalk:PreProcessingScript</span></span>  
  
-   <span data-ttu-id="176e6-115">Directiva o regla: System.BizTalk:Rules</span><span class="sxs-lookup"><span data-stu-id="176e6-115">Policy or rule: System.BizTalk:Rules</span></span>  
  
-   <span data-ttu-id="176e6-116">Directorio virtual: System.BizTalk:WebDirectory</span><span class="sxs-lookup"><span data-stu-id="176e6-116">Virtual directory: System.BizTalk:WebDirectory</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="176e6-117">Para evitar conflictos de espacio de nombres, siempre debería utilizar el nombre de tipo completo (como, System.BizTalk:Assembly) en lugar del nombre de tipo solo (como Ensamblado).</span><span class="sxs-lookup"><span data-stu-id="176e6-117">To avoid namespace conflicts, you should always use the full type name (such as System.BizTalk:Assembly) rather than the type name alone (such as Assembly).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="176e6-118">Uso</span><span class="sxs-lookup"><span data-stu-id="176e6-118">Usage</span></span>  
 <span data-ttu-id="176e6-119">**BTSTask ListTypes**</span><span class="sxs-lookup"><span data-stu-id="176e6-119">**BTSTask ListTypes**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="176e6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="176e6-120">See Also</span></span>  
 [<span data-ttu-id="176e6-121">Referencia de línea de comandos de BTSTask</span><span class="sxs-lookup"><span data-stu-id="176e6-121">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)