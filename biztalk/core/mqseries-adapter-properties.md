---
title: Propiedades del adaptador de MQSeries | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fae8cc1ed67f077b6ae12945da10c58cf0f147da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263572"
---
# <a name="mqseries-adapter-properties"></a>Propiedades del adaptador de MQSeries
Para tener acceso a las propiedades de encabezado MQSeries desde una orquestación de BizTalk, se deberá agregar al proyecto una referencia al ensamblado MQSeries.dll. Este ensamblado está ubicado donde instaló el adaptador MQSeries, por ejemplo, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].  
  
 Tras hacer referencia el esquema de propiedades de MQSeries, propiedades de contexto adicionales están disponibles para varias herramientas de desarrollo de BizTalk Server (por ejemplo, el **asignación de mensajes** forma en el Diseñador de orquestaciones).  
  
> [!NOTE]
>  Cuando trabaje con propiedades de encabezado MQSeries, no olvide seguir las directrices descritas en la documentación de IBM WebSphere MQ.  
  
 El adaptador promociona automáticamente algunas propiedades de MQSeries. Las aplicaciones y componentes personalizados deben evitar degradar estas propiedades. Puede promocionar propiedades adicionales utilizando componentes de canalización personalizados. Las propiedades que se promocionan automáticamente son las siguientes:  
  
-   **BizTalk_CorrelationID**  
  
-   **MQMD_CorrelId**  
  
-   **MQMD_MsgId**  
  
-   **MQMD_ReplyToQ**  
  
-   **MQMD_ReplyToQMgr**  
  
-   **MQXQH_RemoteQMgrName**  
  
-   **MQXQH_RemoteQName**  
  
-   **MQXQH_MsgDesc_CorrelId**  
  
-   **MQXQH_MsgDesc_MsgId**  
  
-   **MQXQH_MsgDesc_ReplyToQ**  
  
-   **MQXQH_MsgDesc_ReplyToQMgr**  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Conversión de tipos de datos de propiedades](../core/data-type-conversion-of-properties.md)  
  
-   [Propiedades relacionadas con BizTalk Server](../core/properties-related-to-biztalk-server.md)  
  
-   [Propiedades de contexto de MQSeries](../core/mqseries-context-properties.md)  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de MQSeries](../core/configuring-the-mqseries-adapter.md)