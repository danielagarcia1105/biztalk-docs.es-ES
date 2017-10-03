---
title: "Restricciones de la propiedad de dirección URL de destino | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [HTTP adapters], restrictions
- HTTP adapters, restrictions
ms.assetid: 982a5122-e43d-4730-a8b9-ceb1ff88638c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0788b693027fb803b121b1b732cb3ee126897e7b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="restrictions-on-the-destination-url-property"></a>Restricciones de la propiedad de dirección URL de destino
La dirección URL de destino es una cadena que especifica la dirección del servidor HTTP donde desea enviar mensajes con el protocolo HTTP.  
  
 Las reglas y restricciones siguientes se aplican a la propiedad Dirección URL de destino:  
  
-   Siempre debe especificar la propiedad Dirección URL de destino con el formato siguiente:  
  
     http [s] ://\<host > [:\<puerto >] [/\<ruta de acceso > [/\<archivo > [?\< cadena de consulta >]]]  
  
-   La cadena entera puede estar o no codificada con un URI.  
  
-   Toda la cadena, excepto la cadena de consulta, no puede contener ninguno de los siguientes caracteres: \< >: \ &#124; " ? *.  
  
-   La propiedad no distingue mayúsculas de minúsculas.  
  
-   La longitud de la cadena no debe exceder 256 caracteres.  
  
## <a name="see-also"></a>Vea también  
 [Configurar un puerto de envío HTTP](../core/configuring-an-http-send-port.md)