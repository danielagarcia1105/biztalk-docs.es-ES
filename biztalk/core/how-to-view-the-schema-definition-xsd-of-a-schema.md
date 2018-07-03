---
title: Cómo ver la definición de esquema (XSD) de un esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, viewing
- managing [schemas], viewing
- viewing, schema definitions
- schemas, schema definition (XSD)
- managing [schemas], schema definition (XSD)
ms.assetid: 21b6d9e6-5737-4334-9fe6-15ae01f90c0d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 558c87b4ed8d9a5504725c17a7f8d36bb10e821d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985397"
---
# <a name="how-to-view-the-schema-definition-xsd-of-a-schema"></a><span data-ttu-id="2e44e-102">Cómo ver la definición de esquemas (XSD) de un esquema</span><span class="sxs-lookup"><span data-stu-id="2e44e-102">How to View the Schema Definition (XSD) of a Schema</span></span>
<span data-ttu-id="2e44e-103">En este tema se describe cómo utilizar la consola de administración de BizTalk Server para ver la definición de esquemas (XSD) de un esquema.</span><span class="sxs-lookup"><span data-stu-id="2e44e-103">This topic describes how to use the BizTalk Server Administration console to view the schema definition (XSD) of a schema.</span></span> <span data-ttu-id="2e44e-104">Puede que desee hacerlo para solucionar errores de validación de esquemas o para validar que se ha implementado el esquema correcto.</span><span class="sxs-lookup"><span data-stu-id="2e44e-104">You might want to do this to troubleshoot schema validation errors or validate that the correct schema is deployed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2e44e-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2e44e-105">Prerequisites</span></span>  
 <span data-ttu-id="2e44e-106">Para llevar a cabo el procedimiento descrito en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server o del grupo de operadores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2e44e-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> <span data-ttu-id="2e44e-107">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="2e44e-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-xsd-of-a-schema"></a><span data-ttu-id="2e44e-108">Para ver la XSD de un esquema</span><span class="sxs-lookup"><span data-stu-id="2e44e-108">To view the XSD of a schema</span></span>  
  
1. <span data-ttu-id="2e44e-109">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2e44e-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="2e44e-110">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene el esquema para el que desea ver la XSD y, a continuación, expanda la aplicación que contiene el esquema.</span><span class="sxs-lookup"><span data-stu-id="2e44e-110">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema for which you want to view the XSD, and then expand the application containing the schema.</span></span>  
  
3. <span data-ttu-id="2e44e-111">Haga clic en **esquemas**, haga clic en el esquema y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2e44e-111">Click **Schemas**, right-click the schema, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="2e44e-112">En el panel izquierdo, haga clic en **vista esquema**.</span><span class="sxs-lookup"><span data-stu-id="2e44e-112">In the left pane, click **Schema View**.</span></span>  
  
    <span data-ttu-id="2e44e-113">La XSD se muestra en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="2e44e-113">The XSD displays in the right pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e44e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e44e-114">See Also</span></span>  
 [<span data-ttu-id="2e44e-115">Administración de esquemas</span><span class="sxs-lookup"><span data-stu-id="2e44e-115">Managing Schemas</span></span>](../core/managing-schemas.md)