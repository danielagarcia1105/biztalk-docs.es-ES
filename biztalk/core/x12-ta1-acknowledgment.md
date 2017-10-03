---
title: "X12 confirmación TA1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68568a1a-3669-46f4-8edc-8d057b012544
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8547175461732e41248e1e94bf961f95e655890f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="x12-ta1-acknowledgment"></a>Confirmación TA1 de X12
La confirmación técnica TA1 de X12 informa del estado del procesamiento de un encabezado de intercambio y finalizador mediante el receptor de direcciones. Si los segmentos ISA y IEA del mensaje codificado con X12 son válidos, se envía una confirmación TA1 positiva, siempre que el estado del otro contenido también sea válido. En caso contrario, la confirmación TA1 se envía con un código de error.  
  
 La confirmación TA1 se ajusta a la X12_ de X12\<número de versión > _TA1.xsd esquema. La confirmación TA1 se envía dentro de un sobre ISA/IEA. Los intercambios ISA e IEA no son distintos a otros intercambios.  
  
 Los segmentos del intercambio de una confirmación TA1 se muestran en la siguiente tabla.  
  
|Campo en TA1|Nombre del campo|Asignado a un intercambio entrante|Valor|  
|------------------|-------------------|------------------------------------|-----------|  
|TA101|Número de control de intercambio.|ISA13 - Número de control de intercambio|-|  
|TA102|Fecha de intercambio|Fecha del intercambio ISA09|-|  
|TA103|Hora de intercambio|ISA10 – Hora de intercambio|-|  
|TA104|Código de confirmación de intercambio*|N/D|Comportamiento del motor: A, E o R<br /><br /> A = Aceptar<br /><br /> E = Intercambio aceptado con errores<br /><br /> R = Intercambio rechazado/suspendido|  
|TA105|Código de nota de intercambio|N/D|Código de error de resultado de procesamiento. **Nota:** tabla vea en [X12 códigos de Error de confirmación de TA1](../core/x12-ta1-acknowledgment-error-codes.md).|  
  
 \*Comportamiento del motor se basa en la validación de elementos de datos; excepto la información de autenticación y seguridad, que se basará fuera comparaciones de cadenas de información de configuración.