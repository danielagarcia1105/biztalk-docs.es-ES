---
title: Problemas conocidos del adaptador MLLP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP adapters, known issues
- known issues, MLLP adapters
ms.assetid: 66af8fcc-981a-4a77-80b7-84824bfae608
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cbae1bf4bf04e2ecf4e643ad5107b9e0fd70f70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206060"
---
# <a name="mllp-adapter-known-issues"></a>Problemas conocidos del adaptador MLLP
Esta sección contiene información útil que puede ayudar a evitar errores del adaptador de protocolo de nivel inferior mínimo (MLLP).  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a>Adaptador MLLP bidireccional podría no detectar un problema con una confirmación  
 Cuando [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) recibe una confirmación (ACK) en un adaptador MLLP bidireccional, el adaptador realiza una validación ligera en la confirmación para determinar su validez. Si se encuentra sea válido, se extrae el campo MSA1 y dependiendo de su valor, el adaptador de reintentos, suspende o elimina el mensaje original a la que se responde la confirmación. Sin embargo, dado que la validación realizada por el adaptador no es una validación completa, es posible que el adaptador no detectan un problema con la confirmación. Por ejemplo, el adaptador puede determinar que la confirmación es válida y eliminar el mensaje original, mientras que la canalización podría determinar que la confirmación no tenía el formato correcto y suspender el mensaje de confirmación.  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a>Contadores de rendimiento de MLLP no cuentan confirmaciones  
 Una medida de rendimiento es el número de mensajes procesados por un adaptador MLLP, como se indica en los contadores de rendimiento de MLLP. Este contador mide el número de mensajes recibidos o transmitida. Sin embargo, el recuento no mide el número de confirmaciones recibidos o enviados.  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a>No se garantiza que los nombres de conexión de adaptador MLLP ser único  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]no garantiza la exclusividad del nombre de conexión especificado en las páginas de propiedades de un adaptador MLLP. Asegurarse de esa conexión descriptiva y relevante nombres se escriben en este campo obligatorio. Uso de nombres de conexión que representan las aplicaciones de línea de negocio puede ser útil al tratar de comprender el comportamiento de la conexión. Por ejemplo, los contadores PerfMon utilizar el nombre de la conexión.  
  
> [!NOTE]
>  BTAHL7 asegurar la exclusividad de las ubicaciones de recepción o nombres de puerto de envío.  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a>Adaptadores MLLP bidireccionales no envían confirmación ACK para todos los mensajes en un lote  
 Al configurar cada mensaje en un lote que se va a generar una confirmación de confirmación y el sistema envía el lote a un MLLP bidireccional del adaptador de recepción, el adaptador sólo enviará la confirmación de confirmación correspondiente al primer mensaje en el lote.  
  
> [!NOTE]
>  Se recomienda que utilice un adaptador MLLP unidireccional para el transporte de lotes.  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a>NAK generado por el adaptador MLLP bidireccional  
 Cuando un adaptador MLLP bidireccional suspende cualquier mensaje, el adaptador MLLP genera un NAK (confirmación negativa) y lo coloca en la base de datos de cuadro de mensajes. Esto puede ser un comportamiento inesperado. Puede que desee quitar el NAK desde la base de datos de cuadro de mensajes o asignar a otro mensaje.  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a>Adaptador MLLP bidireccional sólo es compatible con el formato del mensaje 2.X  
 El adaptador MLLP bidireccional admite actualmente solo el formato del mensaje 2.X.  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a>El adaptador MLLP bidireccional no admite confirmaciones estáticas  
 La de envío bidireccional adaptador no admite el procesamiento de confirmaciones estáticas.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)