---
title: "Adaptador dinámico MLLP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e22fabb-0edf-4931-b8b2-74a5daccee4a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7d1d7046135de1dc1837d1fb8961ef440b5009
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-mllp-adapter"></a>Adaptador MLLP dinámica
A partir de [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)], se pueden configurar las propiedades del adaptador MLLP en tiempo de ejecución mediante un puerto de envío unidireccional o bidireccional (solicitud-respuesta).  
  
## <a name="dynamic-properties"></a>Propiedades dinámicas  
 Las propiedades siguientes están en el **GlobalPropertySchemas** espacio de nombres:  
  
|Propiedad|Description|  
|--------------|-----------------|  
|Mensaje (MLLP.acceptableACKCodes) = "Todos los códigos de confirmación;"|Los valores son:<br /><br /> -Todos los códigos de confirmación<br />-AA y entidad de certificación<br />-AA, CA, AE y CE<br />-AA, CA, AR y CR<br /><br /> Esto es similar a la **aceptable códigos de confirmación** propiedad en un puerto de envío estático MLLP.|  
|Mensaje (MLLP. CarriageReturn) = "0D";|Carácter de retorno de carro de ASCII|  
|Mensaje (MLLP.endBlockDelimiter) = "c 1";|Carácter ASCII final del bloque|  
|Mensaje (MLLP.startBlockDelimiter) = "0b";|Carácter del bloque de inicio de ASCII|  
|Mensaje (MLLP.timeout) = "60000";|Período después qué socket envío inactiva en el tiempo de espera de BTAHL7 server will (0 no es tiempo de espera)|  
|SendPortName(Microsoft.XLANGs.BaseTypes.Address) = "127.0.0.1:11000";|Dirección y el puerto para enrutar el mensaje|  
|SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) = "MLLP";|Tipo de adaptador (MLLP)|  
  
## <a name="additional"></a>Notas  
  
-   Al crear un mensaje de varias partes en una orquestación para HL7, cree las partes del mensaje en este siguiente orden:  
  
    1.  Segmento de MSH  
  
    2.  BodySegments  
  
    3.  ZSegments  
  
     Si especifica las partes del mensaje en un orden diferente, se produce el siguiente error:  
  
     WrongBodyPartException  
  
-   Las propiedades de ruta del adaptador pueden especificarse en la orquestación para admitir el enrutamiento dinámico.  
  
## <a name="see-also"></a>Vea también  
 [Parámetros de configuración para el envío y adaptadores de recepción](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [Cómo procesa el adaptador de recepción de MLLP](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [Cómo procesa el adaptador MLLP envío](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [Procesamiento de mensajes con codificación MLLP](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)