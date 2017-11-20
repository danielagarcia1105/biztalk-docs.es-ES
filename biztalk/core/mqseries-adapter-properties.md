---
title: Propiedades del adaptador de MQSeries | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQXQH_RemoteQName property [MQSeries adapters]
- MQMD_ReplyToQ property [MQSeries adapters]
- configuring [MQSeries adapters], properties
- MQXQH_MsgDesc_ReplyToQMgr property [MQSeries adapters]
- UserHttpHeaders property [MQSeries adapters]
- MQMD_CorrelId property [MQSeries adapters]
- MQXQH_MsgDesc_MsgId property [MQSeries adapters]
- MQXQH_MsgDesc_ReplyToQ property [MQSeries adapters]
- SubmissionHandle property [MQSeries adapters]
- BizTalk_CorrelationID property [MQSeries adapters]
- MQMD_ReplyToQMgr property [MQSeries adapters]
- EnableChunkedEncoding property [MQSeries adapters]
- MQSeries adapters, properties
- MQXQH_MsgDesc_CorrelId property [MQSeries adapters]
- MQXQH_RemoteQMgrName property [MQSeries adapters]
- MQMD_MsgId property [MQSeries adapters]
ms.assetid: c3cfbc8c-4c9b-431e-b0b6-4c065a69ce6b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fae8cc1ed67f077b6ae12945da10c58cf0f147da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-properties"></a><span data-ttu-id="f0ad3-102">Propiedades del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="f0ad3-102">MQSeries Adapter Properties</span></span>
<span data-ttu-id="f0ad3-103">Para tener acceso a las propiedades de encabezado MQSeries desde una orquestación de BizTalk, se deberá agregar al proyecto una referencia al ensamblado MQSeries.dll.</span><span class="sxs-lookup"><span data-stu-id="f0ad3-103">To access MQSeries header properties from a BizTalk orchestration, you must add a reference to the MQSeries.dll assembly to your project.</span></span> <span data-ttu-id="f0ad3-104">Este ensamblado está ubicado donde instaló el adaptador MQSeries, por ejemplo, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0ad3-104">This assembly is located where you installed the MQSeries adapter, for example, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="f0ad3-105">Tras hacer referencia el esquema de propiedades de MQSeries, propiedades de contexto adicionales están disponibles para varias herramientas de desarrollo de BizTalk Server (por ejemplo, el **asignación de mensajes** forma en el Diseñador de orquestaciones).</span><span class="sxs-lookup"><span data-stu-id="f0ad3-105">After you reference the MQSeries property schema, additional context properties are available to various BizTalk Server development tools (for example, the **Message Assignment** shape in Orchestration Designer).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0ad3-106">Cuando trabaje con propiedades de encabezado MQSeries, no olvide seguir las directrices descritas en la documentación de IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="f0ad3-106">Make sure that you follow the guidelines in the IBM WebSphere MQ documentation when you work with MQSeries header properties.</span></span>  
  
 <span data-ttu-id="f0ad3-107">El adaptador promociona automáticamente algunas propiedades de MQSeries.</span><span class="sxs-lookup"><span data-stu-id="f0ad3-107">The adapter automatically promotes some MQSeries properties.</span></span> <span data-ttu-id="f0ad3-108">Las aplicaciones y componentes personalizados deben evitar degradar estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="f0ad3-108">Your applications and custom components must avoid demoting these properties.</span></span> <span data-ttu-id="f0ad3-109">Puede promocionar propiedades adicionales utilizando componentes de canalización personalizados.</span><span class="sxs-lookup"><span data-stu-id="f0ad3-109">You can promote additional properties by using custom pipeline components.</span></span> <span data-ttu-id="f0ad3-110">Las propiedades que se promocionan automáticamente son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="f0ad3-110">The automatically promoted properties are as follows:</span></span>  
  
-   <span data-ttu-id="f0ad3-111">**BizTalk_CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="f0ad3-111">**BizTalk_CorrelationID**</span></span>  
  
-   <span data-ttu-id="f0ad3-112">**MQMD_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="f0ad3-112">**MQMD_CorrelId**</span></span>  
  
-   <span data-ttu-id="f0ad3-113">**MQMD_MsgId**</span><span class="sxs-lookup"><span data-stu-id="f0ad3-113">**MQMD_MsgId**</span></span>  
  
-   <span data-ttu-id="f0ad3-114">**MQMD_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="f0ad3-114">**MQMD_ReplyToQ**</span></span>  
  
-   <span data-ttu-id="f0ad3-115">**MQMD_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="f0ad3-115">**MQMD_ReplyToQMgr**</span></span>  
  
-   <span data-ttu-id="f0ad3-116">**MQXQH_RemoteQMgrName**</span><span class="sxs-lookup"><span data-stu-id="f0ad3-116">**MQXQH_RemoteQMgrName**</span></span>  
  
-   <span data-ttu-id="f0ad3-117">**MQXQH_RemoteQName**</span><span class="sxs-lookup"><span data-stu-id="f0ad3-117">**MQXQH_RemoteQName**</span></span>  
  
-   <span data-ttu-id="f0ad3-118">**MQXQH_MsgDesc_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="f0ad3-118">**MQXQH_MsgDesc_CorrelId**</span></span>  
  
-   <span data-ttu-id="f0ad3-119">**MQXQH_MsgDesc_MsgId**</span><span class="sxs-lookup"><span data-stu-id="f0ad3-119">**MQXQH_MsgDesc_MsgId**</span></span>  
  
-   <span data-ttu-id="f0ad3-120">**MQXQH_MsgDesc_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="f0ad3-120">**MQXQH_MsgDesc_ReplyToQ**</span></span>  
  
-   <span data-ttu-id="f0ad3-121">**MQXQH_MsgDesc_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="f0ad3-121">**MQXQH_MsgDesc_ReplyToQMgr**</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f0ad3-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f0ad3-122">In This Section</span></span>  
  
-   [<span data-ttu-id="f0ad3-123">Conversión de tipos de datos de propiedades</span><span class="sxs-lookup"><span data-stu-id="f0ad3-123">Data Type Conversion of Properties</span></span>](../core/data-type-conversion-of-properties.md)  
  
-   [<span data-ttu-id="f0ad3-124">Propiedades relacionadas con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f0ad3-124">Properties Related to BizTalk Server</span></span>](../core/properties-related-to-biztalk-server.md)  
  
-   [<span data-ttu-id="f0ad3-125">Propiedades de contexto de MQSeries</span><span class="sxs-lookup"><span data-stu-id="f0ad3-125">MQSeries Context Properties</span></span>](../core/mqseries-context-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="f0ad3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0ad3-126">See Also</span></span>  
 [<span data-ttu-id="f0ad3-127">Configurar el adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="f0ad3-127">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)