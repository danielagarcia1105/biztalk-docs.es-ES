---
title: Encabezados de mensaje de archivo sin formato | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1981daaf-149a-426d-9a2f-5fcf64bce185
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 271e9fe74d0a55f4b3ff5271861d24474fffaf37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-message-headers"></a>Encabezados de los mensajes de archivo sin formato
El análisis del encabezado del mensaje de instancia de archivo sin formato opcional el Desensamblador de archivos sin formato se controla mediante el esquema de archivo sin formato que se ha configurado en el **esquema de encabezado** propiedad en tiempo de diseño del desensamblador de archivos sin formato o el **XMLNORM. HeaderSpecName** propiedad de contexto de mensaje. Si no ha especificado un esquema con uno de estos dos métodos, el desensamblador de archivos sin formato considera que el mensaje de instancia de archivo sin formato no contiene ningún encabezado.  

## <a name="outbound-messages"></a>Mensajes salientes  
 Para los mensajes de instancia de archivo sin formato, puede configurar el ensamblador de archivo sin formato para generar un encabezado especificando el esquema apropiado en su **Header Specification Name** propiedad en tiempo de diseño o **XMLNORM. HeaderSpecName** propiedad de contexto de mensaje. Para obtener más información acerca de cómo establecer propiedades de contexto de mensaje, consulte **propiedades de contexto de mensaje** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  

## <a name="inbound-messages"></a>Mensajes de entrada  
 Los datos encontrados en los encabezados de los mensajes de instancia de archivo sin formato de entrada se pueden conservar y utilizar de dos maneras. En primer lugar, los encabezados de los mensajes de instancia de archivo sin formato se pueden guardar por completo dentro del contexto de mensaje del cuerpo para restaurarlos más tarde como encabezados de los mensajes de instancia de archivo sin formato de salida correspondientes. Puede usar el **conservar encabezado** propiedad de la canalización de recepción para especificar que debe conservarse el encabezado. En caso de que especifique un encabezado en el ensamblador de archivos sin formato, el encabezado conservado se usará en el mensaje de salida.  
  
 En segundo lugar, los elementos individuales de datos de un encabezado de mensaje de instancia de archivo sin formato se pueden copiar al contexto del mensaje asociado con el cuerpo del mensaje de archivo sin formato si se especifica la promoción de propiedades para uno o más campos en el esquema correspondiente. Para obtener más información acerca de la promoción de propiedades, vea [promocionar propiedades](../core/promoting-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Cuerpos de mensaje de archivo sin formato](../core/flat-file-message-bodies.md)   
 [Finalizadores de mensaje de archivo sin formato](../core/flat-file-message-trailers.md)   
 [Estructura de un mensaje de archivo sin formato](../core/structure-of-a-flat-file-message.md)   
 [Cómo crear esquemas para mensajes de archivo sin formato](../core/how-to-create-schemas-for-flat-file-messages.md)