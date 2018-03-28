---
title: Restricciones de la propiedad de dirección URL de destino | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [HTTP adapters], restrictions
- HTTP adapters, restrictions
ms.assetid: 982a5122-e43d-4730-a8b9-ceb1ff88638c
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f7966fccca324a1453f0ea84e79cd7d9d3d55ad
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="restrictions-on-the-destination-url-property"></a>Restricciones de la propiedad de dirección URL de destino
La dirección URL de destino es una cadena que especifica la dirección del servidor HTTP donde desea enviar mensajes con el protocolo HTTP.  
  
 Las reglas y restricciones siguientes se aplican a la propiedad Dirección URL de destino:  
  
-   Siempre debe especificar la propiedad Dirección URL de destino con el formato siguiente:  
  
     http[s]://\<host\>[:\<port\>][/\<path\>[/\<file\>[?\<query-string\>]]]  
  
-   La cadena entera puede estar o no codificada con un URI.  
  
-   ¿Toda la cadena, excepto la cadena de consulta, no puede contener ninguno de los siguientes caracteres: \< \> : \ &#124; "? *.  
  
-   La propiedad no distingue mayúsculas de minúsculas.  
  
-   La longitud de la cadena no debe exceder 256 caracteres.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de un puerto de envío HTTP](../core/configuring-an-http-send-port.md)