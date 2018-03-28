---
title: Desensamblador y ensamblador de las propiedades promocionan | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, promoted properties
- promoted properties, assembler
- promoted properties, disassembler
- assembler, promoted properties
ms.assetid: 342b0250-bdf7-45ce-8964-3aeda89989b1
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab1e0cab902ded34f10cf03bc6e8229d28123be2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="disassembler-and-assembler-promoted-properties"></a>Desensamblador y ensamblador de las propiedades promocionadas
Las propiedades de desensamblador y de ensamblador se dividen en dos categorías: propiedades de enrutamiento para el enrutamiento y filtrado; y las propiedades de tiempo de ejecución, para el procesamiento interno.  
  
Este tema proporciona una lista de propiedades que se agregan al y promocionan para todos los mensajes publicados por el Desensamblador SWIFT para la base de datos de cuadro de mensajes.  
  
## <a name="routing-properties"></a>Propiedades de enrutamiento

El Desensamblador SWIFT promociona las propiedades de enrutamiento. Puede utilizar estas propiedades para enrutamiento por contenidos (filtros de puertos de envío) y recibir el filtrado en las orquestaciones.  
  
|Nombre promocionada|Description|Tipo de datos|Intervalo de valores|Ejemplo de uso|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_BatchId**|Un identificador único global que se genera dinámicamente el Desensamblador SWIFT cuando se procesa un lote de entrada. El Desensamblador asigna este identificador de lote a todos los mensajes publicados en la base de datos de cuadro de mensajes que se origina en el mismo lote.<br /><br /> Establecido en **-1** para mensajes sencillos (que no se origina desde un lote entrante).|String|"-1" o *identificador único global (GUID)*|Correlacionar mensajes con el mismo **A4SWIFT_BatchId** valor agruparlos en el mismo lote en el que incluyeron originalmente.|  
|**A4SWIFT_BreValidationErrors**|Indica el número de errores de validación encontrados durante la validación de motor de reglas de negocios (BRE).|Numérico|>= 0|Filtro de mensajes que no se produjo un error de validación de BRE (**A4SWIFT_BREValidationErrors** es igual a cero).|  
|**A4SWIFT_Failed**|Indica si se produjeron errores durante el procesamiento de mensajes (análisis y validación). Establecido en **True** si **A4SWIFT_ParseErrors** + **A4SWIFT_XmlValidationErrors** + **A4SWIFT_BreValidationErrors**  > 0.|Boolean|True, False|Filtro de mensajes SWIFT solo es válidos (**A4SWIFT_Failed** es igual a **False**).|  
|**A4SWIFT_ParseErrors**|Indica el número de errores de análisis encontrados durante el análisis.|Numérico|>= 0|Filtro de mensajes sin errores de análisis (**A4SWIFT_ParseErrors** es igual a cero).|  
|**A4SWIFT_PosInBatch**|Indica la posición ordinal de un mensaje que se origina en un lote de entrada. Un lote que contiene *n* mensajes, **A4SWIFT_PosInBatch** toma un valor entre 1 y *n*, que corresponde a la posición ordinal del mensaje en el lote.<br /><br /> Establecido en **0** si el mensaje es un encabezado de lote.<br /><br /> Establecido en **n+1** si el mensaje es un finalizador de lote.<br /><br /> Establecido en **1** si el mensaje es todo el lote (deshabilitado de fragmentación de lote).<br /><br /> Establecido en **-1** para mensajes sencillos (que no se origina desde un lote entrante).|Numérico|>= -1|Ordenar los mensajes desde el mismo lote entrante en el orden original en el que se incluyeron.|  
|**A4SWIFT_XmlValidationErrors**|Indica el número de errores de validación encontrados durante la validación de XML.|Numérico|>= 0|Filtro de mensajes que no se produjo un error de validación XML (**A4SWIFT_XmlValidationErrors** es igual a cero).|  
  
> [!NOTE]
>  En general, deben evaluar todas las expresiones de filtro o enrutamiento **A4SWIFT_Failed** antes de evaluar las propiedades de enrutamientos. Solo **A4SWIFT_Failed** se garantiza que será promovido y está disponible. Las propiedades restantes no están disponibles para los mensajes únicos válidos (no lote mensajes) publicados en la base de datos de cuadro de mensajes. Las demás propiedades se promocionan sólo para *no se pudo* solo mensajes y lote (válido o no).  

## <a name="runtime-properties"></a>Propiedades de tiempo de ejecución

El Desensamblador SWIFT promociona las propiedades en tiempo de ejecución y los utiliza para los procesos internos en tiempo de ejecución. Sólo están promocionadas y están disponibles para el enrutamiento en determinadas condiciones, dependiendo del contexto. En general, no utilice estas propiedades para enrutamiento o el filtrado. No se garantiza promocionadas y estará disponible. En algunos escenarios, puede inspeccionar estas propiedades después de recuperar o filtrar la información con las propiedades de enrutamiento. En la tabla siguiente se enumera las propiedades en tiempo de ejecución.  
  
|Nombre promocionada|Description|Tipo de datos|Intervalo de valores|Ejemplo de uso|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_IsMessageHeaderValued**|Indica si los datos existen en la parte del encabezado del mensaje de varias partes. Establecido en **True** si la parte del encabezado contiene datos (encabezado de mensaje sobre para un mensaje procedente de un lote). Establecido en **False** si el elemento de encabezado está vacío.|Boolean|True, False|Decida si desea inspeccionar la parte del encabezado de un mensaje recuperado (por ejemplo, en una orquestación de reparación de mensajes).|  
|**A4SWIFT_IsMessageTrailerValued**|Indica si los datos existen en la parte del finalizador del mensaje de varias partes. Establecido en **True** si la parte del finalizador contiene datos (finalizador de sobres de mensaje para un mensaje procedente de un lote). Establecido en **False** si la parte del finalizador está vacía.|Boolean|True, False|Decida si desea inspeccionar la parte del finalizador de un mensaje recuperado (por ejemplo, en una orquestación de reparación de mensajes).|  
|**A4SWIFT_MessageType**|Tipo de mensaje de número de tres dígitos en el encabezado SWIFT indicar SWIFT (**MT*xxx ***).|String|*Tres dígitos numéricos*|Identificar dinámicamente el tipo de mensaje SWIFT de un mensaje.|  
|**A4SWIFT_MessageType2**|Tipo de mensaje de número de tres dígitos en el encabezado SWIFT indicar SWIFT (**MT*xxx ***). Usar sólo si **A4SWIFT_MessageType** no se encuentra en el encabezado de SWIFT.|String|*Tres dígitos numéricos*|Identificar dinámicamente el tipo de mensaje SWIFT de un mensaje.|  
|**A4SWIFT_NumberOfParts**|Indica el número de partes del mensaje de varias partes.<br /><br /> Establecido en **1** si sólo la parte del cuerpo existe (que contiene un mensaje SWIFT individual válido que no se origina en un lote, o el encabezado de lote o el finalizador de lote de un elemento envelope lote).<br /><br /> Establecido en **2** si las partes de cuerpo y error existen (parte del cuerpo que contiene el mensaje de error o el lote, parte del error que contiene la colección de errores de XML).<br /><br /> Establecido en **3** si el cuerpo, el encabezado y el finalizador partes existen (parte del cuerpo que contiene el mensaje SWIFT individual válido que se origina desde un lote, el encabezado de sobre de mensaje que contiene de encabezado parte, si no usa y finalizador de mensaje que contiene la parte finalizador de sobres, si usa: **A4SWIFT_IsMessageHeaderValued** y **A4SWIFT_IsMessageTrailerValued** indicar si los datos existen en los elementos de encabezado y finalizador).|Numérico|1, 2, 3|Filtro de mensajes con un número determinado de elementos (por ejemplo, filtrar por **A4SWIFT_NumberOfParts** forma de recepción es igual a dos para una orquestación de reparación de mensajes).|  
|**A4SWIFT_SecondaryMessageType**|Un valor de cadena en el encabezado SWIFT indicar SWIFT subtipo del mensaje (**MT*xxx_XYZ ***).|String|*Cualquier cadena*|Identificar dinámicamente el subtipo de mensaje SWIFT de un mensaje.|  
  
 
## <a name="see-also"></a>Vea también  
[Propiedades promocionadas A4SWIFT_*](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   