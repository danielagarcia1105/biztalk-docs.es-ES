---
title: Restricciones de uso de Macros en encabezados SMTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- macros, SMTP headers [SMTP adapters]
- SMTP adapters, macros
- SMTP adapters, restrictions
- configuring [SMTP adapters], SMTP headers
- SMTP adapters, SMTP headers
- configuring [SMTP adapters], macros
- SMTP headers
ms.assetid: ceab0917-cb3c-423b-a15f-63747ab1d8da
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5162de289f9c9e7798e5a24aa75fa9305763b401
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977981"
---
# <a name="restrictions-on-using-macros-in-smtp-headers"></a>Restricciones de uso de Macros en encabezados SMTP
Puede utilizar un conjunto predefinido de macros para formar dinámicamente las propiedades **Asunto**, **Para**, **De**y **CC** de un encabezado de mensaje SMTP. Antes de enviar un mensaje, el controlador de envío de SMTP sustituye todas las macros de los encabezados por el valor correspondiente. Puede utilizar varias macros para formar un encabezado.  
  
 El controlador de envío de SMTP no sustituirá las macros de los encabezados **Para**, **De**ni **CC** cuando se dé algunas de las situaciones siguientes:  
  
- La propiedad de sistema correspondiente no está definida.  
  
- La macro no se ha escrito correctamente.  
  
- El valor de la macro contiene símbolos que no son válidos para los encabezados SMTP.  
  
  Si se cumple alguna de estas condiciones, el envío de SMTP controlador dejará las macros como están, por ejemplo, <strong>% SourceParty %@somedomain.com</strong>  o **Message from % SourceParty %**.  
  
  En la tabla siguiente se enumeran las macros que puede utilizar para crear los encabezados **Para**, **CC**y **Asunto** .  
  
|Macro|Descripción|Para uso con “Para”|Para uso con “CC”|Para uso con “Asunto”|  
|-----------|-----------------|---------------------|---------------------|--------------------------|  
|%MessageID%|Identificador único global (GUID) del mensaje en BizTalk Server. El valor procede de la propiedad de contexto de mensaje **BTS.DestinationParty**.|no|no|Sí|  
|%datetime_bts2000%|Hora y fecha UTC con formato AAAMMDDhhmmss, donde sss representa los segundos y milisegundos (por ejemplo, 199707121035234 significa 1997/07/12, 10:35:23 y 400 milisegundos).|no|no|Sí|  
|%datetime%|Hora y fecha UTC con formato AAAA-MM-DDThhmmss (por ejemplo, 1997-07-12T103508).|no|no|Sí|  
|%datetime.tz%|Hora y fecha local, y diferencia de zona horaria respecto de GMT, con formato AAAA-MM-DDThhmmssDZH (por ejemplo, 1997-07-12T103508+ 800).|no|no|Sí|  
|%time%|Hora UTC con formato hhmmss.|no|no|Sí|  
|%time.tz%|Hora local, y diferencia de zona horaria en relación con GMT, con formato hhmmssDZH (por ejemplo, 124525+530).|no|no|Sí|  
|%SourceParty%|Nombre de la entidad de origen de la que procede el mensaje recibido por el adaptador de archivo.|no|no|Sí|  
|%SourcePartyQualifier%|Calificador de la entidad de origen de la que procede el mensaje recibido por el adaptador de archivo.|no|no|Sí|  
|%DestinationParty%|Nombre de la entidad de destino. El valor procede de la propiedad de contexto del mensaje **BTS.DestinationParty**.|Sí|Sí|Sí|  
|%DestinationPartyQualifier%|Calificador de la entidad de destino. El valor procede de la propiedad de contexto del mensaje **BTS.DestinationPartyQualifier**.|no|no|Sí|  
  
## <a name="see-also"></a>Vea también  
 [Restricciones al configurar el adaptador de SMTP](../core/restrictions-when-configuring-the-smtp-adapter.md)