---
title: Administrar secuencias de comandos previas y posteriores al procesamiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 107ada12-fef2-4b56-8ff8-228c13761104
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18926a0c51e5ab5f65b32373d20b2931ccaa627d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262476"
---
# <a name="manage-pre--and-post-processing-scripts"></a><span data-ttu-id="de5df-102">Administrar secuencias de comandos previas y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="de5df-102">Manage Pre- and Post-processing Scripts</span></span>

## <a name="overview"></a><span data-ttu-id="de5df-103">Información general</span><span class="sxs-lookup"><span data-stu-id="de5df-103">Overview</span></span>
<span data-ttu-id="de5df-104">Esta sección proporciona instrucciones sobre cómo utilizar la consola de administración de BizTalk Server o la herramienta de la línea de comandos BTSTask para administrar secuencias de comandos previas y posteriores al procesamiento.</span><span class="sxs-lookup"><span data-stu-id="de5df-104">This section provides instructions on using the BizTalk Server Administration console or the BTSTask command-line tool to manage pre- and post-processing scripts.</span></span> <span data-ttu-id="de5df-105">Puede crear una secuencia de comandos que deba ejecutarse cuando se importe, instale o desinstale (quite) una aplicación de BizTalk, y luego agregar esta secuencia de comandos a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="de5df-105">You can create a script that you want to have run when a BizTalk application is imported, installed, or uninstalled (removed), and then add the script to the application.</span></span> <span data-ttu-id="de5df-106">Al agregar una secuencia de comandos, debe especificar si es una secuencia de comandos previa al procesamiento (que se ejecuta antes de la importación o instalación, y después de la desinstalación), o posterior al procesamiento (que se ejecuta después de la importación o instalación, y antes de la desinstalación).</span><span class="sxs-lookup"><span data-stu-id="de5df-106">When you add a script, you specify whether it is a pre-preprocessing script, which runs before import, installation and after uninstallation, or a post-processing script, which runs after import or installation, and before uninstallation.</span></span>  
  
 <span data-ttu-id="de5df-107">Si selecciona la secuencia de comandos al exportar la aplicación, la secuencia de comandos se incluye en el archivo .msi de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="de5df-107">If you select the script when exporting the application, the script is included in the .msi file for the application.</span></span> <span data-ttu-id="de5df-108">Al instalar, desinstalar o importar la aplicación, la secuencia de comandos se ejecuta automáticamente, según cómo la haya escrito.</span><span class="sxs-lookup"><span data-stu-id="de5df-108">When you install, uninstall, or import the application, the script automatically runs, depending on how you have written the script.</span></span> <span data-ttu-id="de5df-109">Para obtener más información sobre cómo crear y utilizar secuencias de comandos, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="de5df-109">For more information about creating and using scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de5df-110">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="de5df-110">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="de5df-111">Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="de5df-111">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="de5df-112">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="de5df-112">Next steps</span></span> 
  
-   [<span data-ttu-id="de5df-113">Agregar una secuencia de comandos previa y posteriores al procesamiento a una aplicación</span><span class="sxs-lookup"><span data-stu-id="de5df-113">Add a Pre- or Post-processing Script to an Application</span></span>](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [<span data-ttu-id="de5df-114">Cambiar la ubicación de destino de una secuencia de comandos previa y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="de5df-114">Change the Destination Location of a Pre- or Post-processing Script</span></span>](../core/how-to-change-the-destination-location-of-a-pre-or-post-processing-script.md)  
  
-   [<span data-ttu-id="de5df-115">Quitar una secuencia de comandos previa y posteriores al procesamiento de una aplicación</span><span class="sxs-lookup"><span data-stu-id="de5df-115">Remove a Pre- or Post-processing Script from an Application</span></span>](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)