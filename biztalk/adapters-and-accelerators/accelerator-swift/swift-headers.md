---
title: Encabezados de SWIFT | Documentos de Microsoft
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
ms.openlocfilehash: 17003d43c5f8df74667f439ec83508820666fe9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214380"
---
# <a name="swift-headers"></a>Encabezados de SWIFT
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona SWIFT esquemas de encabezado y finalizador. A4SWIFT ya incorpora estos elementos en los esquemas de intercambio para los distintos mensajes financieros (FIN). Si desea crear un tipo de mensaje de estilo de formato de SWIFT FINÉS personalizado (por ejemplo, un mensaje de N98), puede incorporar los esquemas de encabezado y finalizador en su propio formato.  
  
 El esquema de encabezado SWIFT (SWIFT Header.xsd) contiene los formatos para lo siguiente:  
  
-   Encabezado básico  
  
-   Encabezado de la aplicación (opción de entrada o salida)  
  
-   Encabezado de usuario  
  
-   Delimitador de principio del bloque de texto  
  
 El encabezado básico contiene información sobre el origen del mensaje. El encabezado de la aplicación contiene información sobre el tipo de mensaje y el destino del mensaje. La resolución del tipo de mensaje el Desensamblador SWIFT en una canalización de recepción se basa en el contenido del campo en el encabezado adecuado de la aplicación. El encabezado de usuario es opcional y contiene las instrucciones de procesamiento especial.  
  
> [!NOTE]
>  Algunos tipos de mensajes tienen formatos variable en función de los contenidos del campo 119 en el encabezado de usuario. Se trata de "tipos de mensaje dual" en A4SWIFT. El Desensamblador de A4SWIFT utiliza el tipo de mensaje en el encabezado de la aplicación junto con los contenidos del campo 119 para seleccionar el esquema adecuado para una instancia de mensaje.  
  
 El encabezado de usuario es opcional y aparece principalmente con fines de copia de FIN. El identificador de servicio en el bloque 1 debe ser "01". Si el encabezado está presente, debe estar presente al menos uno de los campos. Sin embargo, todos los campos son opcionales. Los campos en el encabezado de usuario siguen las mismas reglas que en el área de texto de mensaje.  
  
 En la tabla siguiente se enumera todos los tipos de campo de encabezado SWIFT.  
  
|Tipo de campo|Description|  
|----------------|-----------------|  
|**Identificador de la aplicación (bloque 1)**|Designa la aplicación que ha establecido la asociación que se utiliza para transmitir el mensaje. Utilice siempre **F** para los mensajes FIN.|  
|**Bloquear el identificador (todos)**|El primer carácter de la llave de apertura. El identificador de bloque siempre va seguido de dos puntos.<br /><br /> **1** = encabezado básico<br /><br /> **2** = encabezado de la aplicación<br /><br /> **3** = encabezado de usuario<br /><br /> **4** = texto del mensaje<br /><br /> (Vea los valores inferiores a para el finalizador).|  
|**Supervisión de entrega (bloque de 2) (opcional)**|Si la prioridad es **U**, supervisión de entrega debe ser:<br /><br /> **1** = advertencia de no entrega<br /><br /> O bien<br /><br /> **3** = advertencia de no entrega y notificación de entrega.<br /><br /> Si la prioridad es **N**, supervisión de entrega debe ser:<br /><br /> **2** = notificación de entrega<br /><br /> O bien<br /><br /> No incluido|  
|**Dirección de destino (bloque 2)**|La dirección lógica Terminal (LP) completa del destino del mensaje que se envía a la red SWIFT.|  
|**Delimitador final (bloquea todos)**|Use la llave de cierre (**}**) para el delimitador final.|  
|**Identificador de entrada/salida (bloque 2)**|**¿** = Los mensajes enviados a SWIFT.<br /><br /> **O** = mensajes enviados desde SWIFT.|  
|**Hora de entrada y la fecha (bloque 2)**|La hora (HH) y los minutos (MM) seguido del año (AA), month (MM) y día (DD) en el que el remitente envió el mensaje para SWIFT. La fecha y hora de entrada siempre es local para el remitente del mensaje.|  
|**Terminal lógico (LP) dirección (bloque 1)**|La dirección lógica terminal del remitente para los mensajes enviados o el receptor de mensajes recibidos desde la red SWIFT.|  
|**Referencia de mensajes de entrada (MIR) (bloque 2)**|La fecha en que el remitente envió el mensaje para SWIFT escrito en el formato, year (AA), month (MM) y (DD/día). El MIR siempre es local para el remitente del mensaje y va seguida por la dirección completa de LT del remitente del mensaje y el remitente de la sesión y secuencia para SWIFT.|  
|**Prioridad del mensaje (bloque 2)**|Prioridad del mensaje; "S" para los mensajes del sistema (tipos 000: 099); "U" para urgente o "N" para los mensajes de usuario a otro (tipos 100: 999).|  
|**Tipo de mensaje (bloque 2)**|Tres dígitos FINÉS tipo de mensaje, 000-999.|  
|**Período de obsolescencia (bloque 2--opcional)**|Valor de 3 unidades (15 minutos) para la prioridad predeterminado se y 20 unidades (100 minutos) para prioridad N. (Valores predeterminados siempre utilizados. Válido únicamente si la supervisión de entrega está presente.|  
|**Fecha de salida (bloque 2)**|La fecha de salida, local al receptor, se escriben en el siguiente formato: AAMMDD.|  
|**Hora de salida (bloque 2)**|La hora de salida, local al receptor, se escriben en el siguiente formato: HHMM.|  
|**Número de secuencia (bloque 1)**|Para todos los mensajes FIN con un identificador de servicio de **01** o **05**, este número es el siguiente número de secuencia esperado correspondiente a la dirección de la transmisión.<br /><br /> Para los mensajes FIN con un identificador de servicio de **21** o **25**, es el número de secuencia del mensaje de servicio confirmado.|  
|**Identificador de servicio (bloque 1)**|Un número de dos dígitos que identifica el tipo de mensaje del servicio, adecuado para la aplicación de FIN. Para todos los mensajes de tipos del 000 al 999 por term, use **01**. Para todos los mensajes de tipos 02 a 43, utilice su tipo de mensaje de servicio de dos dígitos.|  
|**Identificador de la sesión (bloque 1)**|Si procede, número de la sesión actual de la aplicación según el inicio de sesión.|  
|**Delimitador de inicio (todos los bloques)**|La llave de apertura: **{**.|  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)