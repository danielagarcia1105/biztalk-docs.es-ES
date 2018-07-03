---
title: No se ha reconocido el tipo de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4094bf-af00-4d5c-9661-7c8abcb1b722
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14a76219470f971d2c83e11dabfec7fa912dcb5f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992869"
---
# <a name="unrecognised-message-type"></a><span data-ttu-id="9838f-102">Tipo de mensaje no reconocido</span><span class="sxs-lookup"><span data-stu-id="9838f-102">Unrecognised message type</span></span>
## <a name="details"></a><span data-ttu-id="9838f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9838f-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9838f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9838f-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9838f-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9838f-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9838f-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9838f-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9838f-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9838f-107">Event Source</span></span>   | <span data-ttu-id="9838f-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9838f-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="9838f-109">Componente</span><span class="sxs-lookup"><span data-stu-id="9838f-109">Component</span></span>    |                                       <span data-ttu-id="9838f-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="9838f-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="9838f-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9838f-111">Symbolic Name</span></span>  |                                <span data-ttu-id="9838f-112">UnRecognizedMessageType</span><span class="sxs-lookup"><span data-stu-id="9838f-112">UnRecognizedMessageType</span></span>                                 |
|  <span data-ttu-id="9838f-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9838f-113">Message Text</span></span>   |                   <span data-ttu-id="9838f-114">Tipo de mensaje no reconocido.</span><span class="sxs-lookup"><span data-stu-id="9838f-114">Unrecognised message type.</span></span> <span data-ttu-id="9838f-115">No se puede continuar.</span><span class="sxs-lookup"><span data-stu-id="9838f-115">Cannot proceed further.</span></span>                   |

## <a name="explanation"></a><span data-ttu-id="9838f-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="9838f-116">Explanation</span></span>  
 <span data-ttu-id="9838f-117">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque no se ha implementado ningún esquema de documento para el tipo de documento de un conjunto de transacciones en dicho intercambio o bien BizTalk Server no puede determinar el tipo de documento a partir del código de identificador, la versión y el espacio de nombres del conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="9838f-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because no document schema has been deployed for the document type of a transaction set in that interchange, or BizTalk Server cannot determine the document type from the transaction set identifier code, version, and namespace.</span></span>  

## <a name="user-action"></a><span data-ttu-id="9838f-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9838f-118">User Action</span></span>  
 <span data-ttu-id="9838f-119">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="9838f-119">To resolve this error, do one of the following:</span></span>  

- <span data-ttu-id="9838f-120">Implemente un esquema de documento para el tipo de documento de un conjunto de transacciones en el intercambio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="9838f-120">Deploy a document schema for the document type of a transaction set in the interchange, and then resend the interchange.</span></span>  

- <span data-ttu-id="9838f-121">Compruebe que los siguientes valores definen un esquema válido: de X12, escriba el espacio de nombres de destino, la versión y el documento; para EDIFACT, el espacio de nombres de destino, número de versión de mensaje, el número de versión de mensaje y tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9838f-121">Verify that the following values define a valid schema: for X12, the target namespace, version/release, and document type; for EDIFACT, the target namespace, message version number, message release number, and message type.</span></span> <span data-ttu-id="9838f-122">Para obtener más información, consulte la sección "Detección de esquemas" del tema "Resolución de entidades, detección de esquemas y autorización para los mensajes EDI recibidos" de la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9838f-122">For more information, see the "Schema Discovery" section in the "Party Resolution, Schema Discovery, and Authorization for Received EDI Messages" topic in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>
