---
title: Solución de administración de asociado de bloques de creación de una negociación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0dabb562-7065-44b8-a26f-658d70b126eb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e72d0fc6ff852b18d6cfe18e8c1a6fe9eb9839
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993093"
---
# <a name="building-blocks-of-a-trading-partner-management-solution"></a><span data-ttu-id="afd87-102">Creación de bloques de una solución de administración de socios comerciales</span><span class="sxs-lookup"><span data-stu-id="afd87-102">Building Blocks of a Trading Partner Management Solution</span></span>
## <a name="overview"></a><span data-ttu-id="afd87-103">Información general</span><span class="sxs-lookup"><span data-stu-id="afd87-103">Overview</span></span>
<span data-ttu-id="afd87-104">Una de las principales propuestas de valor de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es permitir que los clientes puedan habilitar la comunicación entre empresas (B2B) con sus socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="afd87-104">One of the core value propositions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to empower customers to enable business-to-business (B2B) communication with their business partners.</span></span> <span data-ttu-id="afd87-105">Para satisfacer dichas necesidades empresariales, las empresas deben modelizar, almacenar y administrar información acerca de:</span><span class="sxs-lookup"><span data-stu-id="afd87-105">To fulfill such business needs, enterprises need to model, store, and manage information about:</span></span>  
  
- <span data-ttu-id="afd87-106">Los socios y sus negocios</span><span class="sxs-lookup"><span data-stu-id="afd87-106">Partners and their businesses</span></span>  
  
- <span data-ttu-id="afd87-107">Reglas de compromiso con los socios: son detalles tales como el protocolo de codificación de mensajes que van a usar (normas EDI), el protocolo de transporte que van a usar (AS2), etc.</span><span class="sxs-lookup"><span data-stu-id="afd87-107">Rules of engagement with the partners – These include details such as which message encoding protocol to use (EDI standards), which transport protocol to use (AS2), etc.</span></span>  
  
  <span data-ttu-id="afd87-108">Mientras [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sigue proporcionando compatibilidad para EDI y AS2, lo agrega a los conceptos fundamentales acerca de cómo administrar y almacenar información acerca de los socios y sus negocios.</span><span class="sxs-lookup"><span data-stu-id="afd87-108">While [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] continues to provide support for EDI and AS2, it adds to the fundamental concepts around how to manage and store information about partners and their business.</span></span> <span data-ttu-id="afd87-109">Los estándares EDI, los mensajes AS2 y los conceptos reunidos forman los bloques de creación de una comunicación B2B o una solución de administración de socios comerciales (TPM).</span><span class="sxs-lookup"><span data-stu-id="afd87-109">EDI standards, AS2 messaging, and the concepts put together form the building blocks of a B2B communication or a Trading Partner Management (TPM) solution.</span></span> <span data-ttu-id="afd87-110">Esta sección proporciona una explicación detallada acerca de estos conceptos.</span><span class="sxs-lookup"><span data-stu-id="afd87-110">This section provides detailed explanation about these concepts.</span></span> 
 
  <span data-ttu-id="afd87-111">Para obtener información acerca de cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es compatible con EDI y AS2, consulte:</span><span class="sxs-lookup"><span data-stu-id="afd87-111">For information about how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] supports EDI and AS2, see:</span></span>
 
  - [<span data-ttu-id="afd87-112">Funcionalidad EDI de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="afd87-112">BizTalk Server EDI functionality</span></span>](../core/biztalk-server-edi-functionality.md)
  - [<span data-ttu-id="afd87-113">Funcionalidad de AS2 de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="afd87-113">BizTalk Server AS2 functionality</span></span>](../core/biztalk-server-as2-functionality.md)
  
## <a name="in-this-section"></a><span data-ttu-id="afd87-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="afd87-114">In This Section</span></span>  
  
-   [<span data-ttu-id="afd87-115">Perfiles de negocio y socios comerciales</span><span class="sxs-lookup"><span data-stu-id="afd87-115">Trading partners and business profiles</span></span>](../core/trading-partners-and-business-profiles.md)
  
-   [<span data-ttu-id="afd87-116">Configuración del protocolo</span><span class="sxs-lookup"><span data-stu-id="afd87-116">Protocol settings</span></span>](../core/protocol-settings.md)  
  
-   [<span data-ttu-id="afd87-117">acuerdo de socio comercial</span><span class="sxs-lookup"><span data-stu-id="afd87-117">Trading partner agreement</span></span>](../core/trading-partner-agreement.md)  
  
-   [<span data-ttu-id="afd87-118">En resumen: definir un comerciales de solución de administración de asociados</span><span class="sxs-lookup"><span data-stu-id="afd87-118">Putting it all together: Defining a trading partner management solution</span></span>](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="afd87-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="afd87-119">See Also</span></span>  
 [<span data-ttu-id="afd87-120">Administración de socios comerciales mediante BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="afd87-120">Trading Partner Management Using BizTalk Server</span></span>](../core/trading-partner-management-using-biztalk-server.md)