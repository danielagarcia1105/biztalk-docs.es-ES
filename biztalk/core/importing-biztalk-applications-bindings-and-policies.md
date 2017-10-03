---
title: "Importación de aplicaciones de BizTalk, los enlaces y directivas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing, applications
- importing, policies
- applications, importing
- policies, importing
- importing, bindings
- bindings, importing
ms.assetid: 678bdb03-efaa-4053-9048-b71fc539d191
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18f7ea348fb34f4f8cc08e748799dcf8368a3c35
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importing-biztalk-applications-bindings-and-policies"></a><span data-ttu-id="7661a-102">Importar aplicaciones, enlaces y directivas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="7661a-102">Importing BizTalk Applications, Bindings, and Policies</span></span>
<span data-ttu-id="7661a-103">Los temas que figuran en esta sección describen cómo importar aplicaciones, enlaces y directivas de BizTalk en un grupo o aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7661a-103">The topics in this section describe how to import BizTalk applications, bindings and policies into a BizTalk group or application.</span></span> <span data-ttu-id="7661a-104">Como se mencionó en [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md), al exportar una aplicación crea un archivo de Windows Installer (.msi) que, a continuación, puede usar para importar los artefactos de la aplicación a una aplicación en un grupo de BizTalk diferente.</span><span class="sxs-lookup"><span data-stu-id="7661a-104">As mentioned in [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md), exporting an application creates a Windows Installer (.msi) file that you can then use to import the application's artifacts into an application in a different BizTalk group.</span></span> <span data-ttu-id="7661a-105">Si la aplicación especificada para la importación aún no existe en el grupo, se creará.</span><span class="sxs-lookup"><span data-stu-id="7661a-105">If the application that you specify for the import does not already exist in the group, the application is created.</span></span> <span data-ttu-id="7661a-106">Además, los artefactos de la aplicación se registran y sus datos se almacenan en las bases de datos del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7661a-106">In addition, application's artifacts are registered and their data stored in the BizTalk databases of the group.</span></span> <span data-ttu-id="7661a-107">Para obtener más información, consulte [¿qué ocurre cuando artefactos se importarán](../core/what-happens-when-artifacts-are-imported.md).</span><span class="sxs-lookup"><span data-stu-id="7661a-107">For more information, see [What Happens When Artifacts Are Imported](../core/what-happens-when-artifacts-are-imported.md).</span></span>  
  
 <span data-ttu-id="7661a-108">También puede importar en un grupo de BizTalk o una aplicación los enlaces que exportó desde un grupo de BizTalk, aplicación o ensamblado, tal como se describe en [exportar enlaces](../core/exporting-bindings6.md).</span><span class="sxs-lookup"><span data-stu-id="7661a-108">You can also import into a BizTalk group or application the bindings that you exported from a BizTalk group, application, or assembly, as described in [Exporting Bindings](../core/exporting-bindings6.md).</span></span> <span data-ttu-id="7661a-109">Al importar enlaces, éstos sobrescriben cualquier enlace con el mismo nombre que haya en el grupo, la aplicación o el ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="7661a-109">When you import bindings, they overwrite any bindings of the same name in the BizTalk group, application, or assembly.</span></span>  
  
 <span data-ttu-id="7661a-110">Además, puede importar una directiva a un grupo de BizTalk que exportó desde un grupo de BizTalk o una aplicación, como se describe en [cómo exportar una directiva](../core/how-to-export-a-policy.md).</span><span class="sxs-lookup"><span data-stu-id="7661a-110">In addition, you can import a policy into a BizTalk group that you exported from a BizTalk group or application, as described in [How to Export a Policy](../core/how-to-export-a-policy.md).</span></span> <span data-ttu-id="7661a-111">A continuación, las aplicaciones del grupo nuevo podrán utilizar la directiva.</span><span class="sxs-lookup"><span data-stu-id="7661a-111">Applications in the new group can then use the policy.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7661a-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7661a-112">In This Section</span></span>  
  
-   [<span data-ttu-id="7661a-113">Cómo importar una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="7661a-113">How to Import a BizTalk Application</span></span>](../core/how-to-import-a-biztalk-application.md)  
  
-   [<span data-ttu-id="7661a-114">Importar enlaces</span><span class="sxs-lookup"><span data-stu-id="7661a-114">Importing Bindings</span></span>](../core/importing-bindings2.md)  
  
-   [<span data-ttu-id="7661a-115">Cómo importar una directiva</span><span class="sxs-lookup"><span data-stu-id="7661a-115">How to Import a Policy</span></span>](../core/how-to-import-a-policy.md)