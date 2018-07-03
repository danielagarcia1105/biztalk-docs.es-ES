---
title: Administrar vínculos de rol | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8860e11-3d2c-450f-a7d2-cc116478999c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e31ec8af7f8c5dd785b471654e9a9cfd7446bbf3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998949"
---
# <a name="manage-role-links"></a><span data-ttu-id="762d1-102">Administrar vínculos de rol</span><span class="sxs-lookup"><span data-stu-id="762d1-102">Manage Role Links</span></span>

## <a name="overview"></a><span data-ttu-id="762d1-103">Información general</span><span class="sxs-lookup"><span data-stu-id="762d1-103">Overview</span></span>
<span data-ttu-id="762d1-104">Esta sección proporciona instrucciones sobre el uso de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para administrar vínculos de rol en una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="762d1-104">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage role links in a BizTalk application.</span></span> <span data-ttu-id="762d1-105">Un vínculo de rol define la relación entre entidades implicadas en una transacción empresarial, y especifica los tipos de puerto y mensaje utilizados en ambas direcciones de la interacción.</span><span class="sxs-lookup"><span data-stu-id="762d1-105">A role link defines the relationship between parties involved in a business transaction and specifies the message and port types used in the interaction in both directions.</span></span> <span data-ttu-id="762d1-106">Para obtener información general sobre los vínculos de rol, consulte [Using Role Links en orquestaciones](../core/using-role-links-in-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="762d1-106">For background information on role links, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  

## <a name="added-to-application"></a><span data-ttu-id="762d1-107">Agrega a la aplicación</span><span class="sxs-lookup"><span data-stu-id="762d1-107">Added to application</span></span>  
 <span data-ttu-id="762d1-108">Los vínculos de rol se generan en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se compilan en ensamblados de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="762d1-108">Role links are built in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="762d1-109">No es posible agregar vínculos de rol a una aplicación de forma individual; un vínculo de rol se agrega a una aplicación del modo que se especifica a continuación:</span><span class="sxs-lookup"><span data-stu-id="762d1-109">You cannot add role links to an application individually; a role link is added to an application as follows:</span></span>  
  
- <span data-ttu-id="762d1-110">Cuando agrega un ensamblado de BizTalk que contenga un vínculo de rol a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="762d1-110">When you add a BizTalk assembly containing a role link to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="762d1-111">Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene un vínculo de función, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="762d1-111">When you import an .msi file into an application that includes a BizTalk assembly containing a role link, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="762d1-112">Cuando un programador implementa en una aplicación un ensamblado que contiene un vínculo de rol de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tal y como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="762d1-112">When a developer deploys into an application an assembly containing a role link from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  

## <a name="deploy-to-production"></a><span data-ttu-id="762d1-113">Implementar en producción</span><span class="sxs-lookup"><span data-stu-id="762d1-113">Deploy to production</span></span>  
 <span data-ttu-id="762d1-114">El programador de aplicaciones de BizTalk crea vínculos de rol para implementar las comunicaciones entre dos o más entidades implicadas en una transacción empresarial (como, por ejemplo, su empresa y un proveedor).</span><span class="sxs-lookup"><span data-stu-id="762d1-114">The BizTalk application developer creates role links to implement communications between two or more parties involved in a business transaction, such as your organization and a supplier.</span></span> <span data-ttu-id="762d1-115">El programador no tiene que especificar necesariamente las entidades implicadas en la transacción, sino solo sus roles.</span><span class="sxs-lookup"><span data-stu-id="762d1-115">The developer does not necessarily specify the parties that are involved in the transaction, only their roles.</span></span> <span data-ttu-id="762d1-116">Para implementar una aplicación que incluye un vínculo de rol en un entorno de producción y habilitar la comunicación real entre las entidades, es preciso efectuar la configuración siguiente, tal y como se describe en esta sección:</span><span class="sxs-lookup"><span data-stu-id="762d1-116">To deploy an application that includes a role link to a production environment and enable actual communication between the parties, the following configuration must be performed, as described in this section:</span></span>  
  
- <span data-ttu-id="762d1-117">Si no se llevó a cabo durante el proceso de desarrollo, se debe asignar una entidad a cada uno de los roles definidos en el vínculo de rol.</span><span class="sxs-lookup"><span data-stu-id="762d1-117">If it wasn't done during the development process, a party must be assigned to each role defined in the role link.</span></span> <span data-ttu-id="762d1-118">Esta acción se denomina "dar de alta" una entidad para un rol.</span><span class="sxs-lookup"><span data-stu-id="762d1-118">This is called "enlisting" a party for a role.</span></span> <span data-ttu-id="762d1-119">Posteriormente, podrá dar de baja la entidad si no desea que ésta siga teniendo el rol asignado.</span><span class="sxs-lookup"><span data-stu-id="762d1-119">You can later unenlist the party if you no longer want the party to have the assigned role.</span></span>  
  
- <span data-ttu-id="762d1-120">Los puertos lógicos de cada una de las entidades definidas en el vínculo de rol deben estar enlazadas a los puertos físicos de las instancias de host de BizTalk que alojarán la aplicación.</span><span class="sxs-lookup"><span data-stu-id="762d1-120">The logical ports for each party defined within the role link must be bound to physical ports on the BizTalk host instances that will host the application.</span></span>  
  
  <span data-ttu-id="762d1-121">Para obtener más información sobre el desarrollo de vínculos de rol, consulte [Using Role Links en orquestaciones](../core/using-role-links-in-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="762d1-121">For more information about developing role links, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="762d1-122">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="762d1-122">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="762d1-123">Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="762d1-123">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="762d1-124">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="762d1-124">Next step</span></span>
  
-   [<span data-ttu-id="762d1-125">Cómo dar de alta o baja a una entidad para un rol</span><span class="sxs-lookup"><span data-stu-id="762d1-125">How to Enlist or Unenlist a Party for a Role</span></span>](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)