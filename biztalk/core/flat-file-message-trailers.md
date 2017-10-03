---
title: Finalizadores de mensaje de archivo sin formato | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfe115a5-4fdc-4779-94f3-437b5a06fbd4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cbeaef3f23de3cb89d873413964cd331ec23f43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-message-trailers"></a>Finalizadores de los mensajes de archivo sin formato
Como con encabezados de mensaje de instancia de archivo sin formato, el análisis del finalizador de mensaje de instancia de archivo sin formato opcional el Desensamblador de archivos sin formato se controla mediante el esquema de archivo sin formato que se ha configurado en el **esquema de finalizador** tiempo de diseño propiedad del desensamblador de archivos sin formato o **XMLNORM. TrailerSpecName** propiedad de contexto de mensaje. Si no ha especificado un esquema con uno de estos dos métodos, el desensamblador de archivos sin formato considerará que el mensaje de instancia de archivo sin formato no contiene un finalizador.  
  
 A diferencia de los encabezados de los mensajes de instancia de archivo sin formato, los finalizadores de los mensajes de instancia de archivo sin formato no se pueden guardar ni restaurar como una única unidad ni pueden usar la promoción de propiedades para copiar elementos individuales de datos al contexto del mensaje asociado con el cuerpo del mensaje de instancia de archivo sin formato. Sin embargo, puede agregarse un finalizador a un mensaje de instancia de archivo sin formato especificando el esquema apropiado en el **esquema de finalizador** propiedad en tiempo de diseño del ensamblador de archivo sin formato o **XMLNORM. TrailerSpecName** propiedad de contexto de mensaje. Los datos que constituyen la parte variable del finalizador se pueden especificar mediante la degradación de propiedades desde el contexto del mensaje del cuerpo del mensaje de instancia de archivo sin formato o mediante la especificación de valores predeterminados o fijos en el esquema correspondiente.  
  
## <a name="see-also"></a>Vea también  
 [Encabezados de mensaje de archivo sin formato](../core/flat-file-message-headers.md)   
 [Cuerpos de mensaje de archivo sin formato](../core/flat-file-message-bodies.md)   
 [Estructura de un mensaje de archivo sin formato](../core/structure-of-a-flat-file-message.md)   
 [Cómo crear esquemas para mensajes de archivo sin formato](../core/how-to-create-schemas-for-flat-file-messages.md)