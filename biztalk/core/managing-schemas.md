---
title: Administrar esquemas | Documentos de Microsoft
description: Usar administración de BizTalk para trabajar con esquemas en BizTalk Server, incluida la presentación y ocultación de propiedades, vea el esquema XSD, habilitar el seguimiento
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5632e79-b182-41c9-9138-eb88b44e3172
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0d7fe3eee97cf81c668ffe90fd9c0897af23cc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262604"
---
# <a name="manage-schemas"></a><span data-ttu-id="cde7e-103">Administrar esquemas</span><span class="sxs-lookup"><span data-stu-id="cde7e-103">Manage Schemas</span></span>

## <a name="overiew"></a><span data-ttu-id="cde7e-104">Información</span><span class="sxs-lookup"><span data-stu-id="cde7e-104">Overiew</span></span>
<span data-ttu-id="cde7e-105">En esta sección, se proporcionan instrucciones acerca de la utilización de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para administrar esquemas.</span><span class="sxs-lookup"><span data-stu-id="cde7e-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage schemas.</span></span> <span data-ttu-id="cde7e-106">Las canalizaciones y orquestaciones usan esquemas para representar el mensaje que se procesará.</span><span class="sxs-lookup"><span data-stu-id="cde7e-106">Schemas are used by pipelines and orchestrations to represent the message that will be processed.</span></span>  
  
 <span data-ttu-id="cde7e-107">Se crean esquemas en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se compilan en ensamblados de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cde7e-107">Schemas are created in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="cde7e-108">No es posible agregar un esquema a una aplicación de manera individual; un esquema se agrega a una aplicación del modo que se especifica a continuación:</span><span class="sxs-lookup"><span data-stu-id="cde7e-108">You cannot add a schema to an application individually; a schema is added to an application as follows:</span></span>  
  
-   <span data-ttu-id="cde7e-109">Al agregar un ensamblado de BizTalk que contiene un esquema a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="cde7e-109">When you add a BizTalk assembly containing a schema to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
-   <span data-ttu-id="cde7e-110">Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene un esquema, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="cde7e-110">When you import an .msi file into an application that includes a BizTalk assembly containing a schema, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="cde7e-111">Cuando un programador implementa en una aplicación un ensamblado que contiene un esquema de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tal y como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="cde7e-111">When a developer deploys into an application an assembly containing a schema from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="cde7e-112">Para obtener información general acerca de los esquemas, vea [esquemas](../core/schemas.md).</span><span class="sxs-lookup"><span data-stu-id="cde7e-112">For background information about schemas, see [Schemas](../core/schemas.md).</span></span> <span data-ttu-id="cde7e-113">Para obtener información acerca de cómo desarrollar esquemas, vea [crear esquemas de uso del Editor BizTalk](../core/creating-schemas-using-biztalk-editor.md).</span><span class="sxs-lookup"><span data-stu-id="cde7e-113">For information about developing schemas, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cde7e-114">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="cde7e-114">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="cde7e-115">Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="cde7e-115">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="cde7e-116">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cde7e-116">Next steps</span></span> 
  
-   [<span data-ttu-id="cde7e-117">Mostrar u ocultar esquemas de propiedades</span><span class="sxs-lookup"><span data-stu-id="cde7e-117">Show and Hide Property Schemas</span></span>](../core/how-to-show-and-hide-property-schemas.md)  
  
-   [<span data-ttu-id="cde7e-118">Ver la definición de esquema (XSD) de un esquema</span><span class="sxs-lookup"><span data-stu-id="cde7e-118">View the Schema Definition (XSD) of a Schema</span></span>](../core/how-to-view-the-schema-definition-xsd-of-a-schema.md)  
  
-   [<span data-ttu-id="cde7e-119">Configurar el seguimiento de un esquema</span><span class="sxs-lookup"><span data-stu-id="cde7e-119">Configure Tracking for a Schema</span></span>](../core/how-to-configure-tracking-for-a-schema.md)  
  
-   [<span data-ttu-id="cde7e-120">Quitar un esquema de una aplicación</span><span class="sxs-lookup"><span data-stu-id="cde7e-120">Remove a Schema from an Application</span></span>](../core/how-to-remove-a-schema-from-an-application.md)