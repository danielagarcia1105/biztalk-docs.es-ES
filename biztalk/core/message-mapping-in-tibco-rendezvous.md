---
title: Asignación de TIBCO Rendezvous de mensajes | Documentos de Microsoft
description: Campos de mensajes y asignación de mensaje a XML en el adaptador de BizTalk para TIBCO Rendezvous
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62793bec-f076-425c-b25e-c4be5bd93cc8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb80ea4f908aa50dc32755c333aa3ccf2ea4db91
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014955"
---
# <a name="message-mapping-in-tibco-rendezvous"></a>Asignación de mensajes en TIBCO Rendezvous
Los mensajes de TIBCO Rendezvous constan de información de encabezado y un conjunto de campos del mensaje. La información de encabezado se asigna directamente a propiedades de contexto del mensaje.  
  
## <a name="message-field-elements"></a>Elementos del campo de mensaje  
 Un campo de mensaje se compone de los siguientes elementos:  
  
|Elemento|Description|  
|-------------|-----------------|  
|**Nombre**|Cadena de caracteres. No tiene que ser única en un mensaje.|  
|**Identificador**|Entero corto. Único en un mensaje. Implícitamente limita el número de campos de mensajes y 65535. El ámbito del identificador es el mensaje (o submensaje). Se puede usar el mismo identificador en dos submensajes, que son a su vez parte de un mensaje de contenido.|  
|**Valor**|Los datos del campo de mensaje.|  
|**Count**|Número de elementos (en caso de una matriz)|  
|**Tipo**|Tipo del campo de mensaje.|  
  
### <a name="mapping-process"></a>Proceso de asignación  
 Los mensajes estructurados de TIBCO Rendezvous se asignan a elementos de XML de la manera siguiente:  
  
-   **Nombre** se utiliza como el nombre del elemento. El nombre de campo de TIBCO Rendezvous puede contener caracteres que no son válidos para su uso en nombres de elementos de XML. El adaptador genera asignaciones de caracteres válidos entre mensajes estructurados de XML y TIBCO Rendezvous.  
  
-   **Identificador** se coloca en un atributo 'id'.  
  
-   **Valor** contiene una representación de cadena que es el cuerpo del elemento.  
  
-   **Recuento de** se omite.  
  
-   **Tipo** información se coloca en un atributo xsi: Type para el elemento generado.  
  
     Para obtener más información, consulte [Data Type Mapping para los controladores de recepción de TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).  
  
## <a name="see-also"></a>Vea también  
 [Conceptos de TIBCO Rendezvous](../core/tibco-rendezvous-concepts.md)   
 [Creación de controladores de recepción de TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)