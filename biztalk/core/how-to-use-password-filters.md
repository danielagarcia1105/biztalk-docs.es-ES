---
title: Cómo usar contraseña filtra | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb429f8b-c301-45a3-8a4f-bbe6f2c566a3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ad35e2c3bec5b2ece69911b8de8c7fd13c9b790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255940"
---
# <a name="how-to-use-password-filters"></a><span data-ttu-id="1f53a-102">Cómo usar filtros de contraseña</span><span class="sxs-lookup"><span data-stu-id="1f53a-102">How to Use Password Filters</span></span>
<span data-ttu-id="1f53a-103">La característica de sincronización de contraseñas de ENTSSO sincroniza contraseñas entre los sistemas Microsoft Windows Active Directory y otros ajenos a Windows.</span><span class="sxs-lookup"><span data-stu-id="1f53a-103">The ENTSSO Password Synchronization feature synchronizes passwords between Microsoft Windows Active Directory and non-Windows systems.</span></span> <span data-ttu-id="1f53a-104">Sin embargo, muchos sistemas externos tiene requisitos de política de contraseñas diferentes de los de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1f53a-104">However, many external systems have password policy requirements which differ from those in Active Directory.</span></span> <span data-ttu-id="1f53a-105">(Por ejemplo, es posible que un sistema IBM requiera que la contraseña se escriba en mayúsculas y tenga un límite de 8 caracteres.) Esto fuerza a ENTSSO a usar el “denominador común mínimo” entre los dos sistemas, lo que limita la seguridad de las contraseñas.</span><span class="sxs-lookup"><span data-stu-id="1f53a-105">(For example, an IBM system may require a password to be upper case and limited to 8 characters.) This forces ENTSSO to use the “lowest common denominator” between the two systems, limiting password security.</span></span>  
  
 <span data-ttu-id="1f53a-106">La característica de filtro de contraseña de ENTSSO aborda esta limitación.</span><span class="sxs-lookup"><span data-stu-id="1f53a-106">The ENTSSO Password Filter feature addresses this limitation.</span></span> <span data-ttu-id="1f53a-107">Un filtro de contraseñas es simplemente un adaptador de sincronización de contraseñas con otras propiedades definidas.</span><span class="sxs-lookup"><span data-stu-id="1f53a-107">A Password Filter is merely a Password Sync Adapter with additional properties defined.</span></span> <span data-ttu-id="1f53a-108">Éstas (por ejemplo, longitud máximo o mínima, mayúsculas o minúsculas y restricciones de número de caracteres) sirven para filtrar las contraseñas de modo que cumplan los criterios requeridos en el sistema externo.</span><span class="sxs-lookup"><span data-stu-id="1f53a-108">These additional properties (such as maximum or minimum length, case, and character restrictions) serve to filter the passwords so that they meet the criteria of the external system.</span></span>  
  
 <span data-ttu-id="1f53a-109">Tenga en cuenta que al crear un filtro de contraseña, el grupo de administrador especificado se usa de forma automática como la cuenta de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="1f53a-109">Note that when you create a Password Filter, the Administrator group specified is automatically used as the SSO Administrators account.</span></span> <span data-ttu-id="1f53a-110">Si cambia el grupo de administradores de SSO, deberá asegurarse de que el filtro de contraseñas también se actualiza con la nueva cuenta de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="1f53a-110">If you change the SSO Administrator group, you will need to make sure the Password Filter is also updated with the new SSO Administrators account.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f53a-111">Igual que con todos los elementos del sistema ENTSSO, los filtros de contraseñas contienen información muy confidencial y deberían conocerlos el menor número de personas posible.</span><span class="sxs-lookup"><span data-stu-id="1f53a-111">As with all elements of the ENTSSO system, Password Filters contain highly sensitive information and should be exposed to the minimum number of people possible.</span></span>  
  
### <a name="to-create-a-password-filter"></a><span data-ttu-id="1f53a-112">Para crear un filtro de contraseñas</span><span class="sxs-lookup"><span data-stu-id="1f53a-112">To Create a Password Filter</span></span>  
  
1.  <span data-ttu-id="1f53a-113">En el **consola de administración de SSO**, haga clic en el **administración de contraseñas** nodo y, a continuación, haga clic en **Crear filtro**.</span><span class="sxs-lookup"><span data-stu-id="1f53a-113">In the **SSO Management Console**, right-click the **Password Management** node, and then click **Create Filter**.</span></span>  
  
     <span data-ttu-id="1f53a-114">El **Asistente de filtro de contraseña** aparece.</span><span class="sxs-lookup"><span data-stu-id="1f53a-114">The **Password Filter Wizard** appears.</span></span>  
  
2.  <span data-ttu-id="1f53a-115">Siga las instrucciones del asistente para crear el filtro de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="1f53a-115">Follow the directions on the Wizard to create the Password Filter.</span></span>  
  
### <a name="to-assign-an-affiliate-application-to-a-password-filter"></a><span data-ttu-id="1f53a-116">Para asignar una aplicación afiliada a un filtro de contraseñas</span><span class="sxs-lookup"><span data-stu-id="1f53a-116">To Assign an Affiliate Application to a Password Filter</span></span>  
  
1.  <span data-ttu-id="1f53a-117">Haga clic en el filtro apropiado y, a continuación, haga clic en **asignar**...</span><span class="sxs-lookup"><span data-stu-id="1f53a-117">Right-click the appropriate filter, and then click **Assign**….</span></span>  
  
2.  <span data-ttu-id="1f53a-118">Seleccione la **aplicación afiliada**.</span><span class="sxs-lookup"><span data-stu-id="1f53a-118">Select the appropriate **Affiliate Application**.</span></span>