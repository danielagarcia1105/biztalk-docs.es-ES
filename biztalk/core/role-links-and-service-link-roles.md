---
title: Vínculos de función y el servicio vinculan Roles | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, orchestrations
- service link roles
- role links
- roles, orchestrations
- roles
- roles, about roles
- service link roles, about service link roles
- orchestrations, roles
- role links, about role links
- orchestrations, deleting
ms.assetid: 23b4ca34-a1a5-44d4-a50d-661277681c72
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6630b1ad22ba86f3efe8a19409f3b731880c8a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268684"
---
# <a name="role-links-and-service-link-roles"></a><span data-ttu-id="40cc0-102">Vínculos de rol y roles de vínculo de servicio</span><span class="sxs-lookup"><span data-stu-id="40cc0-102">Role Links and Service Link Roles</span></span>
<span data-ttu-id="40cc0-103">A *rol* es una colección de tipos de puerto que utiliza un servicio o implementa un servicio.</span><span class="sxs-lookup"><span data-stu-id="40cc0-103">A *role* is a collection of port types that either uses a service or implements a service.</span></span> <span data-ttu-id="40cc0-104">Una función representa el tipo de interacción que una entidad puede tener con una o muchas orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="40cc0-104">A role represents the type of interaction that a party can have with one or many orchestrations.</span></span> <span data-ttu-id="40cc0-105">Las funciones proporcionan flexibilidad y facilidad de administración cuando aumenta el número de entidades.</span><span class="sxs-lookup"><span data-stu-id="40cc0-105">Roles provide flexibility and ease of management as the number of parties increase.</span></span> <span data-ttu-id="40cc0-106">Por ejemplo, una orquestación puede que utilice la función de un remitente.</span><span class="sxs-lookup"><span data-stu-id="40cc0-106">For example, an orchestration might use the role of a Shipper.</span></span> <span data-ttu-id="40cc0-107">El remitente tendría una o dos entidades asociadas con él.</span><span class="sxs-lookup"><span data-stu-id="40cc0-107">The Shipper would have one or two parties associated with it.</span></span> <span data-ttu-id="40cc0-108">Cuando la orquestación decide qué compañía remitente se va a utilizar para enviar un elemento, compara los precios de las entidades de la función del remitente.</span><span class="sxs-lookup"><span data-stu-id="40cc0-108">When the orchestration decides which shipping company to use to ship an item, it compares the prices of the parties in the Shipper role.</span></span>  
  
 <span data-ttu-id="40cc0-109">A *tipo de vínculo de rol* es una propiedad que caracteriza la relación entre dos servicios u orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="40cc0-109">A *role link type* is a property that characterizes the relationship between two services or orchestrations.</span></span> <span data-ttu-id="40cc0-110">Define el papel que desempeña cada servicio en la relación y especifica los tipos de puerto que proporciona cada función.</span><span class="sxs-lookup"><span data-stu-id="40cc0-110">It defines the part played by each of the services in the relationship and specifies the port types provided by each role.</span></span>  
  
 <span data-ttu-id="40cc0-111">Una entidad, o unidad de organización, representa una entidad externa a BizTalk Server que interactúa con una orquestación.</span><span class="sxs-lookup"><span data-stu-id="40cc0-111">A party, or organizational unit, represents an entity outside of BizTalk Server that interacts with an orchestration.</span></span> <span data-ttu-id="40cc0-112">En BizTalk Server, cada organización con la que intercambia mensajes está representada por una entidad.</span><span class="sxs-lookup"><span data-stu-id="40cc0-112">In BizTalk Server, each organization with which you exchange messages is represented by a party.</span></span> <span data-ttu-id="40cc0-113">Es necesario dar de alta una entidad en una función para definir cómo interactúa.</span><span class="sxs-lookup"><span data-stu-id="40cc0-113">You can define how the party interacts by enlisting it in a role.</span></span>  
  
 <span data-ttu-id="40cc0-114">Puede implementar o quitar un tipo de vínculo de función cuando está asociado con una orquestación.</span><span class="sxs-lookup"><span data-stu-id="40cc0-114">You can deploy or remove a role link type when it is associated with an orchestration.</span></span>  
  
## <a name="orchestrations-and-roles"></a><span data-ttu-id="40cc0-115">Orquestaciones y funciones</span><span class="sxs-lookup"><span data-stu-id="40cc0-115">Orchestrations and Roles</span></span>  
 <span data-ttu-id="40cc0-116">Cuando implementa una orquestación que utiliza un tipo de vínculo de función, la base de datos de configuración guarda la función.</span><span class="sxs-lookup"><span data-stu-id="40cc0-116">When you deploy an orchestration that uses a role link type, the Configuration database saves the role.</span></span> <span data-ttu-id="40cc0-117">Puesto que más de una orquestación pueden utilizar una función, la base de datos de administración guarda sólo una copia del tipo de vínculo de función.</span><span class="sxs-lookup"><span data-stu-id="40cc0-117">Because a role can be used by more than one orchestration, the Management database saves only one copy of the role link type.</span></span>  
  
 <span data-ttu-id="40cc0-118">Si el proyecto de BizTalk contiene dos tipos de vínculo de función en distintos archivos de orquestación (.odx) que tienen el mismo nombre y espacio de nombres, el proyecto de BizTalk no se compila.</span><span class="sxs-lookup"><span data-stu-id="40cc0-118">If your BizTalk project contains two role link types in separate orchestration (.odx) files that have the same name and namespace, your BizTalk project does not compile.</span></span>  
  
### <a name="orchestration-removals-that-use-roles"></a><span data-ttu-id="40cc0-119">Eliminaciones de orquestaciones que utilizan funciones</span><span class="sxs-lookup"><span data-stu-id="40cc0-119">Orchestration Removals that use Roles</span></span>  
 <span data-ttu-id="40cc0-120">Puesto que más de una orquestación pueden utilizar un tipo de vínculo de función, cuando anula la implementación de un ensamblado que contiene una orquestación que utiliza una función, la base de datos de administración quita la función sólo en el caso de que ninguna orquestación la esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="40cc0-120">Because a role link type can be used by more than one orchestration, when you undeploy an assembly that contains an orchestration that uses a role, the Management database removes the role only if no other orchestrations are using the role.</span></span>  
  
 <span data-ttu-id="40cc0-121">Asimismo, la base de datos de administración sólo quita una función si no tiene entidades dadas de alta.</span><span class="sxs-lookup"><span data-stu-id="40cc0-121">Additionally, the Management database removes a role only if there are no parties enlisted with it.</span></span> <span data-ttu-id="40cc0-122">Al igual que no puede sobrescribir una función que tenga entidades dadas de alta, no puede quitar una función en la misma situación.</span><span class="sxs-lookup"><span data-stu-id="40cc0-122">Just as you cannot overwrite a role that has parties enlisted with it, you cannot remove a role that has parties enlisted with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40cc0-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="40cc0-123">See Also</span></span>  
 <span data-ttu-id="40cc0-124">[Usar vínculos de rol en orquestaciones](../core/using-role-links-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="40cc0-124">[Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="40cc0-125">Artefactos</span><span class="sxs-lookup"><span data-stu-id="40cc0-125">Artifacts</span></span>](../core/artifacts.md)