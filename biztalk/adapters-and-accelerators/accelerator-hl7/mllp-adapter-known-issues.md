---
title: Problemas conocidos del adaptador MLLP | Microsoft Docs
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
ms.openlocfilehash: cb90c62baebb8fc73b939c0a3ea20eb85e9b0e28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970837"
---
# <a name="mllp-adapter-known-issues"></a>Problemas conocidos del adaptador MLLP
Esta sección contiene información útil que puede ayudarle a evitar errores del adaptador de protocolo de nivel inferior mínimo (MLLP).  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a>Adaptador MLLP bidireccional podría no detectar un problema con una confirmación  
 Cuando el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) recibe una confirmación (ACK) en un adaptador de MLLP bidireccional, el adaptador realiza una validación ligera en la confirmación para determinar su validez. Si se encuentra sea válido, se extrae el campo MSA1 y vuelve a intentar según su valor, el adaptador, suspende o elimina el mensaje original a la que se responde la confirmación. Sin embargo, puesto que la validación realizada por el adaptador no es una validación completa, es posible que el adaptador no detecta un problema con la confirmación. Por ejemplo, el adaptador podría determinar que la confirmación es válida y eliminar el mensaje original, mientras que la canalización podría determinar que la confirmación no tenía el formato correcto y suspender el mensaje de confirmación.  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a>Contadores de rendimiento de MLLP no cuentan confirmaciones  
 Una medida de rendimiento es el número de mensajes procesados por un adaptador MLLP, como se indica en los contadores de rendimiento de MLLP. Este recuento mide el número de mensajes recibidos o transmitir. Sin embargo, el recuento no mide el número de confirmaciones recibidos o enviados.  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a>Nombres de conexión del adaptador MLLP se garantiza que no sean únicos  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] no garantiza la exclusividad del nombre de conexión especificado en las páginas de propiedades de un adaptador MLLP. Asegúrese de esa conexión descriptiva y relevante se especifican los nombres en este campo obligatorio. Uso de nombres de conexión que representan las aplicaciones de línea de negocio puede ser útil al tratar de comprender el comportamiento de la conexión. Por ejemplo, contadores PerfMon use el nombre de la conexión.  
  
> [!NOTE]
>  BTAHL7 garantiza la unicidad de las ubicaciones de recepción o nombres de puerto de envío.  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a>Adaptadores MLLP bidireccionales no envían confirmaciones de confirmación para todos los mensajes en un lote  
 Al configurar cada mensaje en un lote para generar una confirmación de confirmación y el sistema envía el lote al adaptador de recepción de un MLLP bidireccional, el adaptador sólo enviará la confirmación de confirmación correspondiente al primer mensaje en el lote.  
  
> [!NOTE]
>  Se recomienda que use un adaptador de MLLP unidireccional para el transporte de lotes.  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a>NAK generado por el adaptador MLLP bidireccional  
 Cuando un adaptador de MLLP bidireccional suspende cualquier mensaje, el adaptador MLLP genera un NAK (confirmación negativa) y lo coloca en la base de datos de cuadro de mensajes. Esto puede ser un comportamiento inesperado. Es posible que desee quitar el NAK de la base de datos o asignarla a otro mensaje.  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a>Adaptador MLLP bidireccional solo admite el formato del mensaje 2.X  
 El adaptador MLLP bidireccional actualmente admite solo el formato del mensaje 2.X.  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a>El adaptador MLLP bidireccional no admite confirmaciones estáticas  
 El de envío bidireccional adaptador no admite el procesamiento de confirmaciones estáticas.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)