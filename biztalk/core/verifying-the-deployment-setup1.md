---
title: "Comprobar la implementación Setup1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLASSPATH, verifying
- deployment, verifying setup
ms.assetid: 6c719e4c-9a61-480f-a4e4-0a1c518d1364
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5799d164dc2470236c3ab0286e38d19986a4d5a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="verifying-the-deployment-setup"></a><span data-ttu-id="c7695-102">Comprobar la configuración de implementación</span><span class="sxs-lookup"><span data-stu-id="c7695-102">Verifying the Deployment Setup</span></span>
<span data-ttu-id="c7695-103">Antes de usar BizTalk Server para importar un archivo de enlace, debe comprobar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7695-103">Before you use the BizTalk Server to import a binding file, you must verify the following:</span></span>  
  
-   <span data-ttu-id="c7695-104">CLASSPATH apunta a una ubicación concreta para los archivos específicos de JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="c7695-104">The CLASSPATH is pointing to a specific location for the JD Edwards EnterpriseOne-specific files.</span></span> <span data-ttu-id="c7695-105">Verifique si la ubicación de estos archivos es la misma en el equipo nuevo, o edite el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="c7695-105">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="c7695-106">Las carpetas para las respuestas existen y son idénticas en el equipo nuevo, o bien edite el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="c7695-106">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="c7695-107">Las contraseñas del sistema JD Edwards EnterpriseOne, si están presentes en la configuración, se guardan como ***** en el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="c7695-107">JD Edwards EnterpriseOne system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> <span data-ttu-id="c7695-108">Para obtener más información, consulte [limitaciones de la implementación](../core/deployment-limitations4.md).</span><span class="sxs-lookup"><span data-stu-id="c7695-108">For more information see [Deployment Limitations](../core/deployment-limitations4.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7695-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7695-109">See Also</span></span>  
 [<span data-ttu-id="c7695-110">Implementación de puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="c7695-110">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies3.md)