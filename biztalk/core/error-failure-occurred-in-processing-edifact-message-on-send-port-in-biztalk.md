---
title: 'Error al procesar el mensaje Edifact en el puerto de envío: no existen acuerdos de pares de calificador de identificador de receptor y remitente | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cffc4705-164f-4779-8f04-c6a2a7f1bbda
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c27bc81b24a9d2850bc895f28020df286da17cba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021874"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a><span data-ttu-id="4ce4f-102">Error al procesar el mensaje Edifact en el puerto de envío: no existen acuerdos de pares de calificador de identificador de receptor</span><span class="sxs-lookup"><span data-stu-id="4ce4f-102">A failure occurred in processing Edifact message on send port: No agreement for receiver and sender identifier-qualifier pairs</span></span>
## <a name="details"></a><span data-ttu-id="4ce4f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4ce4f-103">Details</span></span>  
  
|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4ce4f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="4ce4f-104">Product Name</span></span>   |                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                         |
| <span data-ttu-id="4ce4f-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="4ce4f-105">Product Version</span></span> |                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                     |
|    <span data-ttu-id="4ce4f-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="4ce4f-106">Event ID</span></span>     |                                                                                 -                                                                                 |
|  <span data-ttu-id="4ce4f-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="4ce4f-107">Event Source</span></span>   |                                      <span data-ttu-id="4ce4f-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ce4f-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                       |
|    <span data-ttu-id="4ce4f-109">Componente</span><span class="sxs-lookup"><span data-stu-id="4ce4f-109">Component</span></span>    |                                                                            <span data-ttu-id="4ce4f-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="4ce4f-110">EDI Engine</span></span>                                                                             |
|  <span data-ttu-id="4ce4f-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4ce4f-111">Symbolic Name</span></span>  |                                                                                 -                                                                                 |
|  <span data-ttu-id="4ce4f-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4ce4f-112">Message Text</span></span>   | <span data-ttu-id="4ce4f-113">Error al procesar el mensaje Edifact en el puerto de envío {0}.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="4ce4f-114">No existen acuerdos de pares de calificador/identificador de receptor y remitente para {1}, {2}, {3} y {4}.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4ce4f-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="4ce4f-115">Explanation</span></span>  
 <span data-ttu-id="4ce4f-116">Este evento de error,  indica que BizTalk Server no pudo resolver la entidad para el intercambio EDIFACT porque no pudo hacer coincidir las propiedades del calificador e identificador del servidor promocionado y las propiedades del calificador e identificador del receptor promocionado con los valores correspondientes para una entidad.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because it was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4ce4f-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4ce4f-117">User Action</span></span>  
 <span data-ttu-id="4ce4f-118">Para resolver este error, asegúrese de que el calificador e identificador del remitente (UNB2.1 y UNB2.2) y el calificador e identificador del receptor (UNB3.1 y UNB3.2) definidos en la página Definición de segmento UNB del cuadro de diálogo Propiedades de EDI coinciden con las propiedades promocionadas correspondientes en el contexto del intercambio.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-118">To resolve this error, ensure that the sender qualifier and identifier (UNB2.1 and UNB2.2) and receiver qualifier and identifier (UNB3.1 and UNB3.2) defined in the party's UNB Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>