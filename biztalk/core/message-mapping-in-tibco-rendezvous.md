---
title: "Asignación de TIBCO Rendezvous de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, mapping
- message mapping
- message field elements
ms.assetid: 62793bec-f076-425c-b25e-c4be5bd93cc8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc5b3559067dbb998240a3fc814d890701e2591c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
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
 [Controladores de recepción de creación TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)