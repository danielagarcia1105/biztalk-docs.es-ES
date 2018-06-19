---
title: 'Se produjo un error en el procesamiento de X12 mensajes en el puerto de envío: no existen acuerdos de pares de calificador de identificador de destinatario y remitente | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72ae7926-f5c1-42f4-8c29-11f34c138dd4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 637cd174b2c9723f4391417392700e3a4f079b79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240860"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a><span data-ttu-id="f49b1-102">Se produjo un error en el procesamiento de X12 mensajes en el puerto de envío: no existen acuerdos de pares de calificador de identificador de destinatario y remitente</span><span class="sxs-lookup"><span data-stu-id="f49b1-102">A failure occurred in processing X12 message on send port: No agreement for receiver and sender identifier-qualifier pairs</span></span>
## <a name="details"></a><span data-ttu-id="f49b1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f49b1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f49b1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f49b1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f49b1-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f49b1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f49b1-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f49b1-106">Event ID</span></span>|-|  
|<span data-ttu-id="f49b1-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f49b1-107">Event Source</span></span>|<span data-ttu-id="f49b1-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f49b1-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="f49b1-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f49b1-109">Component</span></span>|<span data-ttu-id="f49b1-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="f49b1-110">EDI Engine</span></span>|  
|<span data-ttu-id="f49b1-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f49b1-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="f49b1-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f49b1-112">Message Text</span></span>|<span data-ttu-id="f49b1-113">Error al procesar el mensaje X12 en el puerto de envío {0}.</span><span class="sxs-lookup"><span data-stu-id="f49b1-113">A failure occurred in processing X12 message on send port {0}.</span></span> <span data-ttu-id="f49b1-114">No existen acuerdos de pares de calificador o identificador de destinatario y remitente de {1}, {2}, {3}, \{4\.</span><span class="sxs-lookup"><span data-stu-id="f49b1-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f49b1-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="f49b1-115">Explanation</span></span>  
 <span data-ttu-id="f49b1-116">Este evento de error, advertencia o información indica que BizTalk Server no pudo resolver la entidad para el intercambio EDIFACT porque no pudo hacer coincidir las propiedades del calificador e identificador del servidor promocionado y las propiedades del calificador e identificador del receptor promocionado con los valores correspondientes para una entidad.</span><span class="sxs-lookup"><span data-stu-id="f49b1-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f49b1-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f49b1-117">User Action</span></span>  
 <span data-ttu-id="f49b1-118">Para resolver este error, asegúrese de que el calificador e identificador del remitente (ISA5 e ISA6) y el calificador e identificador del receptor (ISA7 e ISA8) definidos en la página Definición de segmento ISA del cuadro de diálogo Propiedades de EDI coinciden con las propiedades promocionadas correspondientes en el contexto del intercambio.</span><span class="sxs-lookup"><span data-stu-id="f49b1-118">To resolve this error, ensure that the sender qualifier and identifier (ISA5 and ISA6) and receiver qualifier and identifier (ISA7 and ISA8) defined in the party's ISA Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>