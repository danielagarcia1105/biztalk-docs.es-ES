---
title: Arquitectura de la solución EDI | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55709a89-7706-4c64-ada3-16951951c943
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6c4ce03c9188a03b47cc2fbe3f67a8be163acdc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009981"
---
# <a name="edi-solution-architecture"></a><span data-ttu-id="8ff4d-102">Arquitectura de solución EDI</span><span class="sxs-lookup"><span data-stu-id="8ff4d-102">EDI Solution Architecture</span></span>
<span data-ttu-id="8ff4d-103">El intercambio electrónico de datos (EDI) es uno de los medios más notables a través del cual las entidades de negocio intercambian datos de forma electrónica.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-103">Electronic Data Interchange (EDI) is one of the most prevalent means by which business entities exchange data electronically.</span></span> <span data-ttu-id="8ff4d-104">El uso de EDI conlleva la sintaxis y los estándares del mensaje (incluidos ANSI X12 y UN/EDIFACT), el protocolo de mensajería y los transportes.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-104">EDI usage entails message syntax and standards (including ANSI X12 and UN/EDIFACT), messaging protocol, and transports.</span></span> <span data-ttu-id="8ff4d-105">A continuación se presentan las características de mensajería EDI:</span><span class="sxs-lookup"><span data-stu-id="8ff4d-105">The following are characteristics of EDI messaging:</span></span>  
  
- <span data-ttu-id="8ff4d-106">Los protocolos de mensajería EDI comprueban que los datos siempre llegan de la forma esperada y los datos dañados o erróneos se detectan y se generan informes de ellos de manera automática.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-106">EDI messaging protocols ensure that data always arrives as expected, and corrupted or incorrect data is automatically detected and reported.</span></span>  
  
- <span data-ttu-id="8ff4d-107">Los mecanismos EDI suelen especificar los esquemas de agregación de datos (procesamiento por lotes).</span><span class="sxs-lookup"><span data-stu-id="8ff4d-107">EDI mechanisms usually specify data aggregation schemes (batching).</span></span>  
  
- <span data-ttu-id="8ff4d-108">Los usuarios a menudo personalizan las definiciones del documento EDI mediante la implementación de un subconjunto o implementación específica de una instrucción EDI.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-108">Users often customize EDI document definitions by implementing subset or specific implementation of an EDI guideline.</span></span>  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8ff4d-109"> procesa los mensajes EDI mediante canalizaciones de recepción y de envío específicas para EDI que pueden analizar y serializar mensajes EDI.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-109"> processes EDI messages using receive and send pipelines specific to EDI that can parse and serialize EDI messages.</span></span> <span data-ttu-id="8ff4d-110">En esta sección se describe la arquitectura de soluciones EDI en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], incluidos los detalles del procesamiento de recepción y de envío, de la validación de mensajes y generación de informes de estado.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-110">This section describes the architecture of EDI solutions on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], including specifics of receive-side and send-side processing, message validation, and status reporting.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ff4d-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8ff4d-111">In This Section</span></span>  
  
-   [<span data-ttu-id="8ff4d-112">Mensajería EDI</span><span class="sxs-lookup"><span data-stu-id="8ff4d-112">EDI Messaging</span></span>](../core/edi-messaging.md)  
  
-   [<span data-ttu-id="8ff4d-113">Rol de los acuerdos en el procesamiento de EDI</span><span class="sxs-lookup"><span data-stu-id="8ff4d-113">The Role of Agreements in EDI Processing</span></span>](../core/the-role-of-agreements-in-edi-processing.md)  
  
-   [<span data-ttu-id="8ff4d-114">Cómo recibe BizTalk Server los mensajes EDI</span><span class="sxs-lookup"><span data-stu-id="8ff4d-114">How BizTalk Server Receives EDI Messages</span></span>](../core/how-biztalk-server-receives-edi-messages.md)  
  
-   [<span data-ttu-id="8ff4d-115">Cómo envía BizTalk Server los mensajes EDI</span><span class="sxs-lookup"><span data-stu-id="8ff4d-115">How BizTalk Server Sends EDI Messages</span></span>](../core/how-biztalk-server-sends-edi-messages.md)  
  
-   [<span data-ttu-id="8ff4d-116">Validación de mensajes EDI</span><span class="sxs-lookup"><span data-stu-id="8ff4d-116">EDI Message Validation</span></span>](../core/edi-message-validation.md)  
  
-   [<span data-ttu-id="8ff4d-117">Uso de las extensiones de herramientas XML</span><span class="sxs-lookup"><span data-stu-id="8ff4d-117">Using the XML Tool Extensions</span></span>](../core/using-the-xml-tool-extensions.md)