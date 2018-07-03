---
title: 'AS2 no válido: nombre detectado durante el procesamiento | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84d848b5-b2a3-460d-85d4-c3576e4e3aaf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32ba8039d57bdc88f2aeed8e2654c5dc738f3d69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002677"
---
# <a name="invalid-as2-to-name-encountered-during-processing"></a><span data-ttu-id="3fd96-102">Se encontró un nombre de AS2-To no válido durante el procesamiento</span><span class="sxs-lookup"><span data-stu-id="3fd96-102">Invalid AS2-To name encountered during processing</span></span>
## <a name="details"></a><span data-ttu-id="3fd96-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3fd96-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="3fd96-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="3fd96-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="3fd96-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="3fd96-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="3fd96-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="3fd96-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="3fd96-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="3fd96-107">Event Source</span></span>   | <span data-ttu-id="3fd96-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fd96-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="3fd96-109">Componente</span><span class="sxs-lookup"><span data-stu-id="3fd96-109">Component</span></span>    |                                       <span data-ttu-id="3fd96-110">Motor AS2</span><span class="sxs-lookup"><span data-stu-id="3fd96-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="3fd96-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3fd96-111">Symbolic Name</span></span>  |                            <span data-ttu-id="3fd96-112">InvalidAS2ToNameEncounteredError</span><span class="sxs-lookup"><span data-stu-id="3fd96-112">InvalidAS2ToNameEncounteredError</span></span>                            |
|  <span data-ttu-id="3fd96-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3fd96-113">Message Text</span></span>   |             <span data-ttu-id="3fd96-114">Se encontró un nombre de AS2-To no válido durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="3fd96-114">Invalid AS2-To name encountered during processing.</span></span>  <span data-ttu-id="3fd96-115">Valor: {0}</span><span class="sxs-lookup"><span data-stu-id="3fd96-115">Value: {0}</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="3fd96-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="3fd96-116">Explanation</span></span>  
 <span data-ttu-id="3fd96-117">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque el valor del encabezado AS2-To no se ajustaba a las especificaciones de AS2 RFC 4130.</span><span class="sxs-lookup"><span data-stu-id="3fd96-117">This Error/Warning/Information event indicates that either the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the value of the AS2-To header did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3fd96-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3fd96-118">User Action</span></span>  
 <span data-ttu-id="3fd96-119">Para resolver este error, asegúrese de que el encabezado AS2-To del mensaje entrante o saliente se ajusta a las especificaciones de la sección 6.2 de AS2 RFC 4130.</span><span class="sxs-lookup"><span data-stu-id="3fd96-119">To resolve this error, make sure that the AS2-To header in the incoming or outgoing message conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>