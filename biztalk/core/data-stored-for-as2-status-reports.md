---
title: Datos almacenados para informes de estado de AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6aa4077-3768-436b-99b9-d203a86a7e69
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f14fc95dfba5e29089653ef02dddd1b0b366ff8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012519"
---
# <a name="data-stored-for-as2-status-reports"></a><span data-ttu-id="2ec41-102">Datos almacenados para informes de estado de AS2</span><span class="sxs-lookup"><span data-stu-id="2ec41-102">Data Stored for AS2 Status Reports</span></span>
<span data-ttu-id="2ec41-103">Existen dos niveles de informes están disponibles en informes de estado AS2: el primero tiene lugar si el **activar informes** propiedad está seleccionada para un acuerdo (desde el **propiedades generales** página de la **General**  pestaña en el **las propiedades del acuerdo** cuadro de diálogo) y el segundo si está seleccionada una propiedad de almacenamiento de base de datos sin repudio para un acuerdo.</span><span class="sxs-lookup"><span data-stu-id="2ec41-103">Two levels of reporting are available in AS2 status reporting: the first if the **Turn ON Reporting** property is selected for an agreement (from the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box), and the second if a non-repudiation database storage property is selected for an agreement.</span></span>  
  
## <a name="data-stored-if-as2-reporting-is-activated"></a><span data-ttu-id="2ec41-104">Datos que se almacenan si están activados los informes AS2</span><span class="sxs-lookup"><span data-stu-id="2ec41-104">Data Stored If AS2 Reporting Is Activated</span></span>  
 <span data-ttu-id="2ec41-105">Si el **activar informes** propiedad está seleccionada para un acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mantendrá un registro de todos los enviado o recibido mensajes AS2 y MDN.</span><span class="sxs-lookup"><span data-stu-id="2ec41-105">If the **Turn ON Reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will keep a record of all sent or received AS2 messages and MDNs.</span></span>  
  
 <span data-ttu-id="2ec41-106">En el caso de mensajes AS2 recibidos, BizTalk Server almacenará los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="2ec41-106">For a received AS2 message, BizTalk Server will store the following information:</span></span>  
  
- <span data-ttu-id="2ec41-107">Un registro del mensaje AS2.</span><span class="sxs-lookup"><span data-stu-id="2ec41-107">A record of the AS2 message.</span></span>  
  
  <span data-ttu-id="2ec41-108">En el caso de MDN enviados o recibidos (sincrónico o asíncrono), BizTalk Server almacenará los datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2ec41-108">For a received or sent MDN (synchronous or asynchronous), BizTalk Server will store the following information:</span></span>  
  
- <span data-ttu-id="2ec41-109">Un registro del MDN.</span><span class="sxs-lookup"><span data-stu-id="2ec41-109">A record of the MDN.</span></span>  
  
  <span data-ttu-id="2ec41-110">La interfaz de usuario de los informes de estado habilita la correlación del registro del mensaje AS2 con el registro del MDN correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2ec41-110">The status reporting UI enables correlation of the AS2 message record to the appropriate MDN record.</span></span>  
  
## <a name="data-stored-if-resend-as2-message-if-mdn-not-received-is-enabled"></a><span data-ttu-id="2ec41-111">Datos que se almacenan si está habilitado Reenviar mensaje de AS2 si no se recibe MDN</span><span class="sxs-lookup"><span data-stu-id="2ec41-111">Data Stored If Resend AS2 Message If MDN Not Received Is Enabled</span></span>  
 <span data-ttu-id="2ec41-112">Si el **reenviar mensaje AS2 si no se recibe MDN** propiedad está seleccionada para un acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] registrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="2ec41-112">If the **Resend AS2 message if MDN not received** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will record the following information:</span></span>  
  
-   <span data-ttu-id="2ec41-113">Fecha y hora de cada intento de reenvío</span><span class="sxs-lookup"><span data-stu-id="2ec41-113">Time of each resend attempt</span></span>  
  
-   <span data-ttu-id="2ec41-114">Estado de cada intento de reenvío</span><span class="sxs-lookup"><span data-stu-id="2ec41-114">Status of each resend attempt</span></span>  
  
-   <span data-ttu-id="2ec41-115">Índice de cada intento de reenvío</span><span class="sxs-lookup"><span data-stu-id="2ec41-115">Index of each resend attempt</span></span>  
  
## <a name="data-stored-if-non-repudiation-database-storage-is-enabled"></a><span data-ttu-id="2ec41-116">Datos que se almacenan si está habilitado el almacenamiento de la base de datos sin repudio</span><span class="sxs-lookup"><span data-stu-id="2ec41-116">Data Stored If Non-Repudiation Database Storage Is Enabled</span></span>  
 <span data-ttu-id="2ec41-117">El almacenamiento de la base de datos sin repudio se habilita seleccionando las propiedades del acuerdo siguientes:</span><span class="sxs-lookup"><span data-stu-id="2ec41-117">Non-repudiation database storage is enabled by the following agreement properties is selected:</span></span>  
  
- <span data-ttu-id="2ec41-118">NRR habilitado para mensajes AS2 codificados de salida</span><span class="sxs-lookup"><span data-stu-id="2ec41-118">NRR enabled for outbound encoded AS2 messages</span></span>  
  
- <span data-ttu-id="2ec41-119">NRR habilitado para mensajes AS2 descodificados de salida</span><span class="sxs-lookup"><span data-stu-id="2ec41-119">NRR enabled for outbound decoded AS2 messages</span></span>  
  
- <span data-ttu-id="2ec41-120">NRR habilitado para MDN de entrada</span><span class="sxs-lookup"><span data-stu-id="2ec41-120">NRR enabled for inbound MDN</span></span>  
  
- <span data-ttu-id="2ec41-121">NRR habilitado para mensajes de AS2 codificados de entrada</span><span class="sxs-lookup"><span data-stu-id="2ec41-121">NRR enabled for inbound encoded AS2 messages</span></span>  
  
- <span data-ttu-id="2ec41-122">NRR habilitado para mensajes de AS2 descodificados de entrada</span><span class="sxs-lookup"><span data-stu-id="2ec41-122">NRR enabled for inbound decoded AS2 messages</span></span>  
  
- <span data-ttu-id="2ec41-123">NRR habilitado para MDN de salida</span><span class="sxs-lookup"><span data-stu-id="2ec41-123">NRR enabled for outbound MDN</span></span>  
  
  <span data-ttu-id="2ec41-124">Si está seleccionada una o varias de las propiedades anteriores, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] almacenará los datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2ec41-124">If one or more of the above properties is selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store the following information:</span></span>  
  
- <span data-ttu-id="2ec41-125">El contenido de todos los mensajes AS2 y el de todos los MDN (con o sin encabezados AS2).</span><span class="sxs-lookup"><span data-stu-id="2ec41-125">The content of any AS2 message and the content of any MDN (with or without AS2 headers).</span></span>  
  
## <a name="data-stored-for-edi-over-as2"></a><span data-ttu-id="2ec41-126">Datos almacenados para mensajes EDI a través de transporte AS2</span><span class="sxs-lookup"><span data-stu-id="2ec41-126">Data Stored For EDI Over AS2</span></span>  
 <span data-ttu-id="2ec41-127">Si el **activar informes** está seleccionada la propiedad tanto para un acuerdo de EDI, así como un acuerdo de AS2 y, después, puede poner en correlación un registro de mensaje AS2 (que contiene la carga EDI) con un registro de mensaje EDI.</span><span class="sxs-lookup"><span data-stu-id="2ec41-127">If the **Turn ON Reporting** property is selected both for an EDI agreement as well as an AS2 agreement, then you can correlate an AS2 message record (containing EDI payload) with an EDI message record.</span></span>  
  
 <span data-ttu-id="2ec41-128">Si está habilitado el almacenamiento de conjuntos de transacciones, es posible mostrar los detalles de los conjuntos de transacciones y los detalles del contenido de los mensajes AS2 en la interfaz de usuario del informe de estado.</span><span class="sxs-lookup"><span data-stu-id="2ec41-128">If transaction set storage is enabled, you can display transaction set details and AS2 message content details in the status reporting UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ec41-129">Para obtener acceso a estos informes, debe utilizar las canalizaciones AS2EdiReceive o AS2EdiSend.</span><span class="sxs-lookup"><span data-stu-id="2ec41-129">You must use the AS2EdiReceive or AS2EdiSend pipeline to have access to these reports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec41-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ec41-130">See Also</span></span>  
 <span data-ttu-id="2ec41-131">[Datos almacenados para informes de estado de AS2 y EDI](../core/data-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="2ec41-131">[Data Stored for EDI and AS2 Status Reports](../core/data-stored-for-edi-and-as2-status-reports.md) </span></span>  
 <span data-ttu-id="2ec41-132">[Datos almacenados para informes de estado EDI](../core/data-stored-for-edi-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="2ec41-132">[Data Stored for EDI Status Reports](../core/data-stored-for-edi-status-reports.md) </span></span>  
 [<span data-ttu-id="2ec41-133">Datos almacenados para informes de estado de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="2ec41-133">Data Stored for Batching Status Reports</span></span>](../core/data-stored-for-batching-status-reports.md)