---
title: Mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- customizing, applications
- applications, customizing
- scripts, applications
- scripts, customizing
ms.assetid: 47627394-d594-491b-9098-38c5d028a378
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dc0afd7ed042f475a9a008125c968f401e6df92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287172"
---
# <a name="using-pre--and-post-processing-scripts-to-customize-application-deployment"></a><span data-ttu-id="6c8dc-102">Usar secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="6c8dc-102">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>
<span data-ttu-id="6c8dc-103">Los temas de esta sección describen cómo se crean secuencias de comandos previas y posteriores al procesamiento para realizar acciones cuando una aplicación se importa, se instala o se desinstala.</span><span class="sxs-lookup"><span data-stu-id="6c8dc-103">The topics in this section describe how to create pre- or post-processing scripts to perform actions when an application is imported, installed, or uninstalled.</span></span> <span data-ttu-id="6c8dc-104">Las secuencias de comandos previas al procesamiento realizan una acción o un conjunto de acciones antes de que comience la importación o la instalación de la aplicación y después de que finalice la desinstalación.</span><span class="sxs-lookup"><span data-stu-id="6c8dc-104">Pre-processing scripts perform an action or set of actions before application import or installation starts, and after uninstallation completes.</span></span> <span data-ttu-id="6c8dc-105">Por otro lado, las secuencias de comandos posteriores al procesamiento realizan una acción o un conjunto de acciones después de que finalice la importación o la instalación de la aplicación y antes de que se inicie la desinstalación.</span><span class="sxs-lookup"><span data-stu-id="6c8dc-105">Post-processing scripts perform an action or set of actions after application import or installation completes, or before uninstallation starts.</span></span>  
  
 <span data-ttu-id="6c8dc-106">Por ejemplo, podría incluir una secuencia de comandos previa al procesamiento que se ejecute antes de la instalación para hacer una copia de seguridad de los archivos de recurso antes de que se sobrescriban durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="6c8dc-106">You might, for example, want to include a pre-processing script that will run before installation to back up resource files before they are overwritten during installation.</span></span> <span data-ttu-id="6c8dc-107">O bien, podría ejecutar una secuencia de comandos posterior al procesamiento que se agregue un certificado al almacén de certificados una vez que la aplicación se ha instalado.</span><span class="sxs-lookup"><span data-stu-id="6c8dc-107">Or you might want to run a post-processing script to add a certificate to the certificate store after an application is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c8dc-108">BizTalk Server incluye ejemplos de secuencias de comandos previas y posteriores al procesamiento.</span><span class="sxs-lookup"><span data-stu-id="6c8dc-108">BizTalk Server includes sample pre- and post-processing scripts.</span></span> <span data-ttu-id="6c8dc-109">Para obtener información sobre el uso de las secuencias de comandos de ejemplo, vea [plantilla (ejemplo de implementación de aplicaciones)](../core/template-application-deployment-sample.md).</span><span class="sxs-lookup"><span data-stu-id="6c8dc-109">For information about using the sample scripts, see [Template (Application Deployment Sample)](../core/template-application-deployment-sample.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c8dc-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6c8dc-110">In This Section</span></span>  
  
-   [<span data-ttu-id="6c8dc-111">Crear una secuencia de comandos previa y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="6c8dc-111">Creating a Pre- or Post-processing Script</span></span>](../core/creating-a-pre-or-post-processing-script.md)  
  
-   [<span data-ttu-id="6c8dc-112">Cómo las Variables de entorno indican el estado de implementación</span><span class="sxs-lookup"><span data-stu-id="6c8dc-112">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)  
  
-   [<span data-ttu-id="6c8dc-113">Estado de artefactos de archivo durante la implementación</span><span class="sxs-lookup"><span data-stu-id="6c8dc-113">Status of File Artifacts During Deployment</span></span>](../core/status-of-file-artifacts-during-deployment.md)  
  
-   [<span data-ttu-id="6c8dc-114">Variables de entorno de secuencia de comandos previas y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="6c8dc-114">Pre- and Post-processing Script Environment Variables</span></span>](../core/pre-and-post-processing-script-environment-variables.md)