---
title: Cómo usar el Asistente para vínculo de función | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- links [roles]
- Role Link Wizard [Orchestration Designer]
- roles, links
- Orchestration Designer, Role Link Wizard
- role links, Role Link Wizard [Orchestration Designer]
- links [roles], about links
ms.assetid: ddc33d87-c08d-4193-9483-4644ef302853
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d31abcc8fcc2bfaf1ebd641e1e52ad08d1c9c9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255860"
---
# <a name="how-to-use-the-role-link-wizard"></a><span data-ttu-id="344c7-102">Cómo usar al Asistente para vínculo de función</span><span class="sxs-lookup"><span data-stu-id="344c7-102">How to Use the Role Link Wizard</span></span>
<span data-ttu-id="344c7-103">El Asistente para vínculo de rol permite crear un vínculo de rol nuevo o modificar uno existente.</span><span class="sxs-lookup"><span data-stu-id="344c7-103">The Role Link Wizard enables you to create a new role link or modify an existing one.</span></span> <span data-ttu-id="344c7-104">Lo puede usar para establecer o ver el nombre, tipo y restricción de acceso del vínculo de rol, así como para ver el rol de implementaciones y el rol de usos que componen el tipo de vínculo de rol.</span><span class="sxs-lookup"><span data-stu-id="344c7-104">You can use it to set or view the name, type, and access restriction of the role link, as well as the implements role and the uses role that compose the role link type.</span></span> <span data-ttu-id="344c7-105">Para entender cómo funcionan los vínculos de rol, vea [Using Role Links en orquestaciones](../core/using-role-links-in-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="344c7-105">To understand how role links work, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="344c7-106">**Nombre de vínculo de rol**: el nombre de vínculo de función se rellena automáticamente y es el nombre actual de un vínculo de rol existente que está configurando o un nombre generado automáticamente si va a crear un nuevo vínculo de función.</span><span class="sxs-lookup"><span data-stu-id="344c7-106">**Role link name**: The role link name is filled in for you and is either the current name of an existing role link that you are configuring, or an automatically generated name if you are creating a new role link.</span></span> <span data-ttu-id="344c7-107">En cualquier caso, puede modificar el nombre.</span><span class="sxs-lookup"><span data-stu-id="344c7-107">In either case you can modify the name.</span></span>  
  
 <span data-ttu-id="344c7-108">**Tipo de vínculo de función**: puede seleccionar un tipo de vínculo de rol existente o cree uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="344c7-108">**Role link type**: You can select an existing role link type, or create a new one.</span></span> <span data-ttu-id="344c7-109">Tanto si configura un tipo de vínculo de rol nuevo como uno existente, puede especificar cómo participa la orquestación en el servicio.</span><span class="sxs-lookup"><span data-stu-id="344c7-109">Whether you are configuring a new or existing role link type, you can specify how your orchestration participates in the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="344c7-110">Se recomienda que cree el tipo de vínculo de rol y el tipo de puerto asociado antes de crear el vínculo de rol, de modo que pueda usar un tipo de vínculo de rol existente para la definición del vínculo de rol.</span><span class="sxs-lookup"><span data-stu-id="344c7-110">We recommend that you create the role link type and associated port type prior to create the role link so that you can use an existing role link type for defining your role link.</span></span> <span data-ttu-id="344c7-111">Para obtener más información, consulte [cómo crear vínculos de rol en orquestaciones](../core/how-to-create-role-links-in-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="344c7-111">For more information, see [How to Create Role Links in Orchestrations](../core/how-to-create-role-links-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="344c7-112">**Uso de vínculo de función**: si crea un nuevo vínculo de función, escriba, tanto la implementa y utiliza roles se crean automáticamente para usted.</span><span class="sxs-lookup"><span data-stu-id="344c7-112">**Role link usage**: If you create a new role link type, both the implements and uses roles are automatically created for you.</span></span> <span data-ttu-id="344c7-113">Puede seleccionar el rol que refleje cómo participa la orquestación en el servicio.</span><span class="sxs-lookup"><span data-stu-id="344c7-113">You can select the role that reflects how your orchestration participates in the service.</span></span> <span data-ttu-id="344c7-114">Tras finalizar los pasos del asistente, puede cambiar el nombre de los identificadores de rol o quitar un rol para acomodar mejor su implementación.</span><span class="sxs-lookup"><span data-stu-id="344c7-114">After you have completed the steps in the wizard, you can rename the role identifiers or remove a role to better match your implementation.</span></span> <span data-ttu-id="344c7-115">Un tipo de vínculo de rol debe contener un ejemplar de uno de los tipos de rol o un ejemplar de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="344c7-115">A role link type must contain one of either role type or one of each role type.</span></span> <span data-ttu-id="344c7-116">Al hacer clic en **Aceptar**, se crean roles sin configurar correspondientes a cada nombre.</span><span class="sxs-lookup"><span data-stu-id="344c7-116">When you click **OK**, unconfigured roles are created corresponding to each name.</span></span> <span data-ttu-id="344c7-117">También puede seleccionar tipos de puerto para los roles en la ventana Tipos.</span><span class="sxs-lookup"><span data-stu-id="344c7-117">You can also select port types for the roles in the Types window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="344c7-118">Si invoca el Asistente para configuración de puertos con el fin de crear un tipo de puerto para el tipo de vínculo de rol y desea seleccionar un tipo de puerto definido anteriormente, asegúrese de que las restricciones de acceso del tipo de puerto no entran en conflicto con las restricciones de acceso del tipo de vínculo de rol.</span><span class="sxs-lookup"><span data-stu-id="344c7-118">If you invoke the Port Configuration Wizard to create a port type for your role link type, and want to select a previously defined port type, ensure that the access restrictions of the port type do not conflict with the access restrictions of the role link type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="344c7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="344c7-119">See Also</span></span>  
 [<span data-ttu-id="344c7-120">Usar vínculos de rol en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="344c7-120">Using Role Links in Orchestrations</span></span>](../core/using-role-links-in-orchestrations.md)