---
title: "Artefactos que deben ser únicos en una aplicación o grupo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- groups, artifacts
- artifacts, requirements
- applications, artifacts
ms.assetid: a758cd74-a962-4e75-aea2-47752ab72a64
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfe9ff033621ed491b7f1deae9e3f2e467e54f83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="artifacts-that-must-be-unique-in-an-application-or-group"></a><span data-ttu-id="cc989-102">Artefactos que deben ser únicos en una aplicación o en un grupo</span><span class="sxs-lookup"><span data-stu-id="cc989-102">Artifacts That Must Be Unique in an Application or Group</span></span>
<span data-ttu-id="cc989-103">Ciertos tipos de artefactos de un grupo o una aplicación de BizTalk deben ser únicos, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="cc989-103">Certain types of artifacts in a BizTalk group or application must be unique, as follows:</span></span>  
  
-   <span data-ttu-id="cc989-104">Los ensamblados de BizTalk y los ensamblados .NET que no son de BizTalk deben tener un nombre completo único en el grupo.</span><span class="sxs-lookup"><span data-stu-id="cc989-104">Both BizTalk assemblies and non-BizTalk .NET assemblies must have a unique full name in the group.</span></span> <span data-ttu-id="cc989-105">El nombre completo consta de un nombre de archivo, del token de clave pública, de la referencia cultural y de la versión.</span><span class="sxs-lookup"><span data-stu-id="cc989-105">The full name consists of a file name, public key token, culture, and version.</span></span>  
  
-   <span data-ttu-id="cc989-106">Las reglas y las directivas deben tener un nombre y un número de versión únicos en el grupo.</span><span class="sxs-lookup"><span data-stu-id="cc989-106">Rules and policies must have a unique name and version number in the group.</span></span>  
  
-   <span data-ttu-id="cc989-107">Los puertos de envío, grupos de puertos de envío, puertos de recepción y ubicaciones de recepción deben tener un nombre único en el grupo.</span><span class="sxs-lookup"><span data-stu-id="cc989-107">Send ports, send port groups, receive ports, and receive locations must have a unique name in the group.</span></span>  
  
-   <span data-ttu-id="cc989-108">Los sitios Web deben tener un nombre de directorio virtual único en el grupo.</span><span class="sxs-lookup"><span data-stu-id="cc989-108">Web sites must have a unique virtual directory name in the group.</span></span>  
  
-   <span data-ttu-id="cc989-109">Los recursos de BAM deben tener un nombre de archivo único en el grupo.</span><span class="sxs-lookup"><span data-stu-id="cc989-109">BAM resources must have a unique file name in the group.</span></span>  
  
-   <span data-ttu-id="cc989-110">Los certificados deben tener una huella digital única en el grupo.</span><span class="sxs-lookup"><span data-stu-id="cc989-110">Certificates must have a unique thumbprint in the group.</span></span>  
  
-   <span data-ttu-id="cc989-111">Los componentes COM deben tener un nombre de archivo único en el grupo.</span><span class="sxs-lookup"><span data-stu-id="cc989-111">COM components must have a unique file name in the group.</span></span>  
  
-   <span data-ttu-id="cc989-112">Los artefactos basados en archivos, como secuencias de comandos y otros archivos sin formato, deben tener nombres de archivo únicos en la aplicación, pero no en el grupo.</span><span class="sxs-lookup"><span data-stu-id="cc989-112">File-based artifacts, such as scripts and other flat files, must have unique file names in the application, but not in the group.</span></span>  
  
 <span data-ttu-id="cc989-113">Puede especificar la opción de sobrescritura para importar o agregar un artefacto a una aplicación si el artefacto ya existe en la aplicación y es de un tipo que debe ser único.</span><span class="sxs-lookup"><span data-stu-id="cc989-113">You can specify the overwrite option to import or add an artifact to an application if the artifact already exists in the application and it is of a type that must be unique in an application.</span></span> <span data-ttu-id="cc989-114">Si el artefacto ya existe en otra aplicación del grupo y es de un tipo que debe ser único en el grupo, no podrá ni agregarlo ni importarlo.</span><span class="sxs-lookup"><span data-stu-id="cc989-114">If the artifact already exists in another application in the group, and it is a type that must be unique in the group, you can neither add nor import it.</span></span>  
  
 <span data-ttu-id="cc989-115">Si necesita usar un artefacto en una aplicación y ya existe en otra aplicación del grupo, puede crear una referencia a la aplicación que contiene el artefacto.</span><span class="sxs-lookup"><span data-stu-id="cc989-115">If you need to use an artifact in one application and it already exists in another application in the group, you can create a reference to the application containing the artifact.</span></span> <span data-ttu-id="cc989-116">Para obtener más información, consulte [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).</span><span class="sxs-lookup"><span data-stu-id="cc989-116">For more information see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc989-117">Puede ver el nombre completo de la mayoría de los tipos de artefactos de una aplicación mediante el comando ListApp de BTSTask, como se describe en [comando ListApp](../core/listapp-command.md).</span><span class="sxs-lookup"><span data-stu-id="cc989-117">You can view the full name of most types of artifacts in an application by using the ListApp command of BTSTask, as described in [ListApp Command](../core/listapp-command.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc989-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc989-118">See Also</span></span>  
 [<span data-ttu-id="cc989-119">Descripción de la implementación de aplicaciones de BizTalk y administración</span><span class="sxs-lookup"><span data-stu-id="cc989-119">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)