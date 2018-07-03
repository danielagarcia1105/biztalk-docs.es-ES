---
title: 'De sesión único: Evento 10757 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24765a25-560b-4391-9839-a325894c679f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08a75a95a3804ee429baaf24c6b89bbb68a0ce6a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008149"
---
# <a name="single-sign-on-event-10757"></a><span data-ttu-id="339ad-102">De sesión único: Evento 10757</span><span class="sxs-lookup"><span data-stu-id="339ad-102">Single Sign-On: Event 10757</span></span>
## <a name="details"></a><span data-ttu-id="339ad-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="339ad-103">Details</span></span>  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="339ad-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="339ad-104">Product Name</span></span>   |                                  <span data-ttu-id="339ad-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="339ad-105">Enterprise Single Sign-On</span></span>                                   |
| <span data-ttu-id="339ad-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="339ad-106">Product Version</span></span> |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    <span data-ttu-id="339ad-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="339ad-107">Event ID</span></span>     |                                            <span data-ttu-id="339ad-108">10757</span><span class="sxs-lookup"><span data-stu-id="339ad-108">10757</span></span>                                             |
|  <span data-ttu-id="339ad-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="339ad-109">Event Source</span></span>   |                                            <span data-ttu-id="339ad-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="339ad-110">ENTSSO</span></span>                                            |
|    <span data-ttu-id="339ad-111">Componente</span><span class="sxs-lookup"><span data-stu-id="339ad-111">Component</span></span>    |                                             <span data-ttu-id="339ad-112">N/D</span><span class="sxs-lookup"><span data-stu-id="339ad-112">N/A</span></span>                                              |
|  <span data-ttu-id="339ad-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="339ad-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="339ad-114">ENTSSO_E_NO_MAPPING</span><span class="sxs-lookup"><span data-stu-id="339ad-114">ENTSSO_E_NO_MAPPING</span></span>                                      |
|  <span data-ttu-id="339ad-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="339ad-115">Message Text</span></span>   | <span data-ttu-id="339ad-116">La asignación no existe.</span><span class="sxs-lookup"><span data-stu-id="339ad-116">The mapping does not exist.</span></span> <span data-ttu-id="339ad-117">No se estableció la información de configuración para aplicaciones de almacén de configuración.</span><span class="sxs-lookup"><span data-stu-id="339ad-117">For Config Store applications, the config info has not been set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="339ad-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="339ad-118">Explanation</span></span>  
 <span data-ttu-id="339ad-119">Si se trata de una aplicación del tipo "Individual" o "Grupo", la asignación no existe.</span><span class="sxs-lookup"><span data-stu-id="339ad-119">If this is an Individual or Group type application, then the mapping does not exist.</span></span>  
  
 <span data-ttu-id="339ad-120">Si se trata de una aplicación de almacén de configuración, no se establecieron los datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="339ad-120">If this is a Config Store application, then the configuration data has not been set.</span></span> <span data-ttu-id="339ad-121">Esto puede ocurrir cuando se ha vuelto a inicializar la base de datos de SSO pero no la base de datos de administración de BizTalk o viceversa.</span><span class="sxs-lookup"><span data-stu-id="339ad-121">This can occur when the SSO database has been reinitialized but the BizTalk Management database has not, or vice versa.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="339ad-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="339ad-122">User Action</span></span>  
 <span data-ttu-id="339ad-123">Si se trata de una aplicación del tipo "Individual" o "Grupo", cree la asignación deseada.</span><span class="sxs-lookup"><span data-stu-id="339ad-123">If this is an Individual or Group type application, create the desired mapping.</span></span> <span data-ttu-id="339ad-124">Para obtener más información, consulte [cómo crear asignaciones de usuario](../core/how-to-create-user-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="339ad-124">For more information, see [How to Create User Mappings](../core/how-to-create-user-mappings.md).</span></span>