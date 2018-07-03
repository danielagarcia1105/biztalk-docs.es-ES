---
title: Administrar esquemas | Microsoft Docs
description: Use Administración de BizTalk para trabajar con esquemas en BizTalk Server, incluidos mostrando y ocultando las propiedades, ver la XSD, habilitar el seguimiento
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
ms.openlocfilehash: 400d6946235c2137a389b22f639159c9f92d6f4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973157"
---
# <a name="manage-schemas"></a><span data-ttu-id="b2ad5-103">Administrar esquemas</span><span class="sxs-lookup"><span data-stu-id="b2ad5-103">Manage Schemas</span></span>

## <a name="overiew"></a><span data-ttu-id="b2ad5-104">Información general</span><span class="sxs-lookup"><span data-stu-id="b2ad5-104">Overiew</span></span>
<span data-ttu-id="b2ad5-105">En esta sección, se proporcionan instrucciones acerca de la utilización de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para administrar esquemas.</span><span class="sxs-lookup"><span data-stu-id="b2ad5-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage schemas.</span></span> <span data-ttu-id="b2ad5-106">Las canalizaciones y orquestaciones usan esquemas para representar el mensaje que se procesará.</span><span class="sxs-lookup"><span data-stu-id="b2ad5-106">Schemas are used by pipelines and orchestrations to represent the message that will be processed.</span></span>  
  
 <span data-ttu-id="b2ad5-107">Los esquemas se crean en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se compilan en ensamblados de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b2ad5-107">Schemas are created in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="b2ad5-108">No es posible agregar un esquema a una aplicación de manera individual; un esquema se agrega a una aplicación del modo que se especifica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b2ad5-108">You cannot add a schema to an application individually; a schema is added to an application as follows:</span></span>  
  
- <span data-ttu-id="b2ad5-109">Cuando agrega un ensamblado de BizTalk que contiene un esquema a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="b2ad5-109">When you add a BizTalk assembly containing a schema to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="b2ad5-110">Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene un esquema, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="b2ad5-110">When you import an .msi file into an application that includes a BizTalk assembly containing a schema, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="b2ad5-111">Cuando un programador implementa en una aplicación un ensamblado que contiene un esquema de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tal y como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="b2ad5-111">When a developer deploys into an application an assembly containing a schema from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="b2ad5-112">Para obtener información general acerca de los esquemas, vea [esquemas](../core/schemas.md).</span><span class="sxs-lookup"><span data-stu-id="b2ad5-112">For background information about schemas, see [Schemas](../core/schemas.md).</span></span> <span data-ttu-id="b2ad5-113">Para obtener información sobre cómo desarrollar esquemas, vea [crear esquemas utilizando BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b2ad5-113">For information about developing schemas, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2ad5-114">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="b2ad5-114">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="b2ad5-115">Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="b2ad5-115">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="b2ad5-116">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b2ad5-116">Next steps</span></span> 
  
-   [<span data-ttu-id="b2ad5-117">Mostrar y ocultar esquemas de propiedades</span><span class="sxs-lookup"><span data-stu-id="b2ad5-117">Show and Hide Property Schemas</span></span>](../core/how-to-show-and-hide-property-schemas.md)  
  
-   [<span data-ttu-id="b2ad5-118">Ver la definición de esquemas (XSD) de un esquema</span><span class="sxs-lookup"><span data-stu-id="b2ad5-118">View the Schema Definition (XSD) of a Schema</span></span>](../core/how-to-view-the-schema-definition-xsd-of-a-schema.md)  
  
-   [<span data-ttu-id="b2ad5-119">Configurar el seguimiento de un esquema</span><span class="sxs-lookup"><span data-stu-id="b2ad5-119">Configure Tracking for a Schema</span></span>](../core/how-to-configure-tracking-for-a-schema.md)  
  
-   [<span data-ttu-id="b2ad5-120">Quitar un esquema de una aplicación</span><span class="sxs-lookup"><span data-stu-id="b2ad5-120">Remove a Schema from an Application</span></span>](../core/how-to-remove-a-schema-from-an-application.md)