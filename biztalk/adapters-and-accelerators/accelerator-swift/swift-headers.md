---
title: Encabezados de SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, headers
- headers [SWIFT]
ms.assetid: b599cca2-8ae6-42db-b3a2-712ba12c1017
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e516fc906d2eac0610cb576266a034c54b42cae7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984445"
---
# <a name="swift-headers"></a>Encabezados de SWIFT
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona esquemas de encabezado y finalizador de SWIFT. A4SWIFT ya ha incorporado en los esquemas de intercambio para los distintos mensajes financieros (FIN). Si desea crear un tipo de mensaje de estilo de formato de FIN de SWIFT personalizado (por ejemplo, un mensaje N98), puede incorporar los esquemas de encabezado y finalizador en su propio formato.  
  
 El esquema de encabezado SWIFT (SWIFT Header.xsd) contiene los formatos para lo siguiente:  
  
- Encabezado básico  
  
- Encabezado de la aplicación (opción de entrada o salida)  
  
- Encabezado de usuario  
  
- Delimitador del principio del bloque de texto  
  
  El encabezado básico contiene información sobre el origen del mensaje. El encabezado de la aplicación contiene información sobre el tipo de mensaje y el destino del mensaje. La resolución del tipo de mensaje, el Desensamblador de SWIFT en una canalización de recepción se basa en el contenido del campo en el encabezado adecuado de la aplicación. El encabezado de usuario es opcional y contiene las instrucciones de procesamiento especial.  
  
> [!NOTE]
>  Algunos tipos de mensajes tienen formatos variable según el contenido del campo 119 en el encabezado de usuario. Estos son los "tipos de mensaje dual" en A4SWIFT. El Desensamblador de A4SWIFT utiliza el tipo de mensaje en el encabezado de la aplicación junto con el contenido del campo 119 para seleccionar el esquema apropiado para una instancia de mensaje.  
  
 El encabezado de usuario es opcional y aparece principalmente con fines de copia de FIN. El identificador del servicio en el bloque 1 debe ser "01". Si el encabezado está presente, debe estar presente al menos uno de los campos. Sin embargo, todos los campos son opcionales. Los campos en el encabezado de usuario siguen las mismas reglas que aparecen en el área de texto del mensaje.  
  
 En la tabla siguiente se enumera todos los tipos de campo de encabezados de SWIFT.  
  
|Tipo de campo|Descripción|  
|----------------|-----------------|  
|**Identificador de la aplicación (bloque de 1)**|Designa la aplicación que ha establecido la asociación que se usa para transmitir el mensaje. Utilice siempre **F** para los mensajes FIN.|  
|**Bloquear el identificador (todos)**|El primer carácter dentro de la llave de apertura. El identificador de bloque siempre va seguido de dos puntos.<br /><br /> **1** = encabezado básico<br /><br /> **2** = encabezado de la aplicación<br /><br /> **3** = encabezado de usuario<br /><br /> **4** = texto del mensaje<br /><br /> (Vea valores siguientes para el finalizador).|  
|**Supervisión de entrega (bloque de 2) (opcional)**|Si la prioridad es **U**, supervisión de entrega debe ser:<br /><br /> **1** = advertencia de no entrega<br /><br /> o bien<br /><br /> **3** = advertencia de no entrega y notificación de entrega.<br /><br /> Si la prioridad es **N**, supervisión de entrega debe ser:<br /><br /> **2** = notificación de entrega<br /><br /> o bien<br /><br /> No incluido|  
|**Dirección de destino (bloque de 2)**|La dirección lógica Terminal (LT) completa del destino del mensaje que se envían a la red SWIFT.|  
|**Delimitador de fin (bloquea todos)**|Utilice la llave de cierre (**}**) para el delimitador final.|  
|**Identificador de entrada/salida (bloque de 2)**|**Puedo** = los mensajes enviados a SWIFT.<br /><br /> **O** = los mensajes enviados desde SWIFT.|  
|**Entrada de hora y fecha (bloque de 2)**|La hora (HH) y los minutos (MM) seguido por el año (AA), month (MM) y día (DD) en el que el remitente envió el mensaje a SWIFT. La fecha y hora de entrada siempre es local para el remitente del mensaje.|  
|**Terminal lógico (LT) dirección (bloque de 1)**|La dirección lógica terminal del remitente para los mensajes enviados o el receptor de mensajes recibidos de la red SWIFT.|  
|**Referencia de mensajes de entrada (MIR) (bloque de 2)**|La fecha en que el remitente envió el mensaje a SWIFT escrita en el formato, year (YY), month (MM) y día (DD). El MIR siempre es local para el remitente del mensaje y va seguida de la dirección completa de LT del remitente del mensaje y el remitente de la sesión y secuencia a SWIFT.|  
|**Prioridad del mensaje (bloque de 2)**|Prioridad del mensaje. "S" para los mensajes del sistema (tipos 000: 099); "U" para urgente o "N" para los mensajes de usuario a otro (tipos de 100: 999).|  
|**Tipo de mensaje (bloque de 2)**|Tres dígitos FIN tipo de mensaje, 000 – 999.|  
|**Período de obsolescencia (bloque 2--opcional)**|Valor predeterminado de 3 unidades (15 minutos) para la prioridad y 20 unidades (100 minutos) de prioridad N. (Se usa siempre valores predeterminados. Válido únicamente si está presente la supervisión de entrega.|  
|**Fecha de salida (bloque de 2)**|La fecha de salida local para el receptor, escrita en el siguiente formato: AAMMDD.|  
|**Hora de salida (bloque de 2)**|La hora de salida local para el receptor, escrita en el siguiente formato: HHMM.|  
|**Número de secuencia (bloque de 1)**|Para todos los mensajes FIN con un identificador de servicio de **01** o **05**, este número es el siguiente número de secuencia esperado adecuado a la dirección de la transmisión.<br /><br /> Para los mensajes FIN con un identificador de servicio de **21** o **25**, es el número de secuencia del mensaje del servicio confirmado.|  
|**Identificador de servicio (bloque de 1)**|Un número de dos dígitos que identifica el tipo de mensaje correspondiente a la aplicación a FIN de servicio. Para todos los mensajes de tipos del 000 al 999 por FIN, utilice **01**. Para todos los mensajes de tipos 02 a 43, utilice su tipo de mensaje de servicio de dos dígitos.|  
|**Identificador de sesión (bloque de 1)**|Según corresponda, número de la sesión actual de la aplicación basada en el inicio de sesión.|  
|**Delimitador de inicio (todos los bloques)**|La llave de apertura: **{**.|  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)