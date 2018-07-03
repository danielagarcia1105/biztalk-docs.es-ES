---
title: Administración de canalizaciones | Microsoft Docs
description: Vínculos rápidos para habilitar el seguimiento y las propiedades de canalización en un puerto de envío o ubicación de recepción en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60b54e0-0a5a-4264-b0e5-96bb187d782b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b15931468b5ba3bf43f227563dd270aabbfa29b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995261"
---
# <a name="managing-pipelines"></a><span data-ttu-id="83c69-103">Administrar canalizaciones</span><span class="sxs-lookup"><span data-stu-id="83c69-103">Managing Pipelines</span></span>

## <a name="overview"></a><span data-ttu-id="83c69-104">Información general</span><span class="sxs-lookup"><span data-stu-id="83c69-104">Overview</span></span>
<span data-ttu-id="83c69-105">En esta sección se proporcionan instrucciones acerca del uso de la consola de administración de BizTalk Server para administrar las canalizaciones de un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="83c69-105">This section provides instructions on using the BizTalk Server Administration console to manage the pipelines in a BizTalk group.</span></span> <span data-ttu-id="83c69-106">Puede configurar el seguimiento de eventos y mensajes, además de configurar propiedades de canalización para un puerto de envío o una ubicación de recepción concretos.</span><span class="sxs-lookup"><span data-stu-id="83c69-106">You can configure tracking for events and messages as well as configure pipeline properties for a specific send port or receive location.</span></span>  
  
 <span data-ttu-id="83c69-107">Las canalizaciones llevan a cabo acciones en mensajes entrantes y salientes, como transformarlos desde un formato nativo a XML, cifrar o descifrar datos, realizar la promoción de propiedades, etc.</span><span class="sxs-lookup"><span data-stu-id="83c69-107">Pipelines perform actions on incoming and outgoing messages, such as transforming them from a native format into XML, encrypting or unencrypting data, performing property promotion, and so on.</span></span>  
  
 <span data-ttu-id="83c69-108">No es posible agregar una canalización a una aplicación de manera individual; una canalización se agrega a una aplicación del modo que se especifica a continuación:</span><span class="sxs-lookup"><span data-stu-id="83c69-108">You cannot add a pipeline to an application individually; a pipeline is added to an application as follows:</span></span>  
  
- <span data-ttu-id="83c69-109">Cuando agrega un ensamblado de BizTalk que contiene una canalización a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="83c69-109">When you add a BizTalk assembly containing a pipeline to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="83c69-110">Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene una canalización, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="83c69-110">When you import an .msi file into an application that includes a BizTalk assembly containing a pipeline, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="83c69-111">Cuando un programador implementa en una aplicación un ensamblado que contiene una canalización desde Visual Studio, como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="83c69-111">When a developer deploys into an application an assembly containing a pipeline from Visual Studio, as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="83c69-112">Para obtener información general acerca de las canalizaciones, consulte [canalizaciones](../core/pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="83c69-112">For background information about pipelines, see [Pipelines](../core/pipelines.md).</span></span> <span data-ttu-id="83c69-113">Para obtener información sobre el desarrollo de canalizaciones, consulte [crear canalizaciones utilizando Diseñador de canalizaciones](../core/creating-pipelines-using-pipeline-designer.md).</span><span class="sxs-lookup"><span data-stu-id="83c69-113">For information about developing pipelines, see [Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83c69-114">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="83c69-114">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="83c69-115">Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="83c69-115">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="83c69-116">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="83c69-116">Next steps</span></span>
  
-   [<span data-ttu-id="83c69-117">Configurar el seguimiento de una canalización</span><span class="sxs-lookup"><span data-stu-id="83c69-117">Configure Tracking for a Pipeline</span></span>](../core/how-to-configure-tracking-for-a-pipeline.md)  
  
-   [<span data-ttu-id="83c69-118">Configurar propiedades de canalización por instancia para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="83c69-118">Configure Per-Instance Pipeline Properties for a Send Port</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [<span data-ttu-id="83c69-119">Configurar propiedades de canalización por instancia para una ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="83c69-119">Configure Per-instance Pipeline Properties for a Receive Location</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)