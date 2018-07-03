---
title: 'AS2 no válido: nombre configurado para entidad | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a203e5f2-d1d9-433f-b2bb-d679bb8fea58
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84b97fc20ec6280557fdd050b25b17e2e068fc08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970669"
---
# <a name="invalid-as2-to-name-configured-for-party"></a><span data-ttu-id="c2f24-102">Nombre AS2-To no válido configurado para Entidad</span><span class="sxs-lookup"><span data-stu-id="c2f24-102">Invalid AS2-To name configured for Party</span></span>
## <a name="details"></a><span data-ttu-id="c2f24-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c2f24-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c2f24-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c2f24-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c2f24-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c2f24-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c2f24-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c2f24-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c2f24-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c2f24-107">Event Source</span></span>   | <span data-ttu-id="c2f24-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2f24-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="c2f24-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c2f24-109">Component</span></span>    |                                       <span data-ttu-id="c2f24-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="c2f24-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="c2f24-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c2f24-111">Symbolic Name</span></span>  |                            <span data-ttu-id="c2f24-112">InvalidAS2ToNameConfiguredError</span><span class="sxs-lookup"><span data-stu-id="c2f24-112">InvalidAS2ToNameConfiguredError</span></span>                             |
|  <span data-ttu-id="c2f24-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c2f24-113">Message Text</span></span>   |               <span data-ttu-id="c2f24-114">AS2 no válido: nombre configurado para entidad: {0} valor: {1}</span><span class="sxs-lookup"><span data-stu-id="c2f24-114">Invalid AS2-To name configured for Party: {0}   Value: {1}</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="c2f24-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c2f24-115">Explanation</span></span>  
 <span data-ttu-id="c2f24-116">Este evento de error,  indica que el codificador o descodificador de AS2 no pudo procesar el mensaje AS2 porque el valor del encabezado AS2-To configurado para la entidad identificada no se ajustaba a las especificaciones de AS2 RFC 4130.</span><span class="sxs-lookup"><span data-stu-id="c2f24-116">This Error/Warning/Information event indicates that the AS2 encoder or decoder could not process the AS2 message because the value of the AS2-To header configured for the identified party did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c2f24-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c2f24-117">User Action</span></span>  
 <span data-ttu-id="c2f24-118">Para resolver este error, asegúrese de que el encabezado AS2-To configurado para la entidad se ajusta a las especificaciones de la sección 6.2 de AS2 RFC 4130.</span><span class="sxs-lookup"><span data-stu-id="c2f24-118">To resolve this error, make sure that the AS2-To header configured for the party conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>