---
title: "Importación de enlace 3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- target computer, cleaning
- importing binding files
- cleaning target computer
ms.assetid: 955bb3e1-3dbc-43ce-9126-205d838ae662
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa1d95c40e3e556068e15a269ee4cbb7e995429a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="f1613-102">Importar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="f1613-102">Importing Binding Files</span></span>
<span data-ttu-id="f1613-103">Antes de utilizar el servidor BizTalk Server para importar un archivo de enlace, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1613-103">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="f1613-104">CLASSPATH apunta a una ubicación específica para los archivos específicos de JD Edwards.</span><span class="sxs-lookup"><span data-stu-id="f1613-104">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="f1613-105">Verifique si la ubicación de estos archivos es la misma en el equipo nuevo, o edite el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="f1613-105">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="f1613-106">Las carpetas para las respuestas existen y son idénticas en el equipo nuevo, o bien edite el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="f1613-106">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="f1613-107">Las contraseñas del sistema de JD Edwards, si hay en la configuración se guardan como ***** en el archivo de enlaces.</span><span class="sxs-lookup"><span data-stu-id="f1613-107">JD Edwards system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> <span data-ttu-id="f1613-108">Para obtener más información, consulte [limitaciones de la implementación](../core/deployment-limitations2.md).</span><span class="sxs-lookup"><span data-stu-id="f1613-108">For more information, see [Deployment Limitations](../core/deployment-limitations2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1613-109">La implementación sobrescribe la configuración de ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="f1613-109">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="f1613-110">Al implementar un archivo de enlace (y un ensamblado) en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="f1613-110">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
## <a name="importing-the-binding-files"></a><span data-ttu-id="f1613-111">Importar los archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="f1613-111">Importing the Binding Files</span></span>  
 <span data-ttu-id="f1613-112">Use el procedimiento siguiente para importar los archivos de enlace.</span><span class="sxs-lookup"><span data-stu-id="f1613-112">Use the following procedure to import the binding files.</span></span>  
  
#### <a name="to-import-the-binding-files"></a><span data-ttu-id="f1613-113">Para importar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="f1613-113">To import the binding files</span></span>  
  
1.  <span data-ttu-id="f1613-114">En el **iniciar** menú, elija **archivos de programa**, seleccione **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server** Para iniciar la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f1613-114">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="f1613-115">Expanda Administración de BizTalk Server, **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="f1613-115">Expand BizTalk Server Administration, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="f1613-116">Haga clic en la aplicación que desee, seleccione **importación**y, a continuación, haga clic en **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="f1613-116">Right-click the desired application, point to **Import**, and then click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="f1613-117">En el **importar enlaces** cuadro de diálogo, busque y seleccione los archivos de enlace y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="f1613-117">In the **Import Bindings** dialog box, browse and select the binding files, and then click **Open**.</span></span>  
  
## <a name="cleaning-the-target-computer"></a><span data-ttu-id="f1613-118">Limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="f1613-118">Cleaning the Target Computer</span></span>  
 <span data-ttu-id="f1613-119">Use el procedimiento siguiente para limpiar el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="f1613-119">Use the following procedure to clean the target computer.</span></span>  
  
#### <a name="to-clean-the-target-computer"></a><span data-ttu-id="f1613-120">Para limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="f1613-120">To clean the target computer</span></span>  
  
-   <span data-ttu-id="f1613-121">Quite los puertos de envío y las ubicaciones de recepción que están enlazados a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f1613-121">Remove the send ports and the receive locations that are bound to the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1613-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1613-122">See Also</span></span>  
 <span data-ttu-id="f1613-123">[Crear controladores de envío de OneWorld JD Edwards](../core/creating-jd-edwards-oneworld-send-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="f1613-123">[Creating JD Edwards OneWorld Send Handlers](../core/creating-jd-edwards-oneworld-send-handlers.md) </span></span>  
 [<span data-ttu-id="f1613-124">Implementación de puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="f1613-124">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies4.md)