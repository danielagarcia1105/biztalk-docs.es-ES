---
title: Cuerpos de mensaje de archivo sin formato | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 097e49a1-75d2-44a4-9372-d78de7b7597c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de8748d9a36c817f7db8fed96a59c8d2bd7dda2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-message-bodies"></a>Cuerpos de los mensajes de archivo sin formato
El cuerpo del mensaje de una instancia de archivo sin formato es necesario y es lo que procesa el desensamblador de archivos sin formato en uno o más mensajes de instancia XML. Para saber qué datos debe contar el cuerpo del mensaje de una instancia de archivo sin formato de entrada, debe configurar el desensamblador de archivos sin formato con el esquema de archivo sin formato correspondiente al cuerpo. Puede especificar el esquema mediante la **esquema de documento** propiedad en tiempo de diseño del desensamblador de archivos sin formato o **XMLNORM. DocumentSpecName** propiedad de contexto de mensaje. Como los mensajes de instancia de archivo sin formato deben tener la parte del cuerpo, tendrá que configurar el esquema apropiado con uno de estos dos métodos.  
  
 Para los mensajes de instancia de archivo sin formato de salida, el ensamblador de archivos sin formato puede determinar de forma dinámica el esquema de archivo sin formato apropiado para el cuerpo del mensaje de instancia. El ensamblador de archivos sin formato determina el esquema apropiado a partir del tipo de mensaje, que es una combinación del espacio de nombres de destino y el nombre del elemento de raíz, los cuales deben estar presentes en la versión XML del mensaje de salida. Como alternativa, puede configurar explícitamente el esquema de archivo sin formato que se utilizará al configurar la **esquema de documento** propiedad en tiempo de diseño del ensamblador de archivo sin formato o **XMLNORM. DocumentSpecName** propiedad de contexto de mensaje.  
  
 Los datos encontrados en los cuerpos de los mensajes de instancia de archivo sin formato de entrada se pueden copiar en el contexto de mensaje correspondiente si especifica la promoción de propiedades en el esquema de archivo sin formato que utiliza el desensamblador de archivos sin formato para procesar el mensaje de instancia de entrada. Igualmente, los datos del contexto de mensaje se pueden copiar de nuevo en los mensajes de instancia de archivo sin formato de salida si especifica la degradación de propiedades en el esquema de archivo sin formato que utiliza el ensamblador de archivos sin formato para procesar el mensaje de salida.  
  
## <a name="see-also"></a>Vea también  
 [Encabezados de mensaje de archivo sin formato](../core/flat-file-message-headers.md)   
 [Finalizadores de mensaje de archivo sin formato](../core/flat-file-message-trailers.md)   
 [Estructura de un mensaje de archivo sin formato](../core/structure-of-a-flat-file-message.md)   
 [Cómo crear esquemas para mensajes de archivo sin formato](../core/how-to-create-schemas-for-flat-file-messages.md)