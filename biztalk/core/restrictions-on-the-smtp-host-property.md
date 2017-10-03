---
title: Restricciones de la propiedad de Host SMTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: 6dbdb6dc-0062-4444-a4c8-6e2a7900f533
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42173fa0ccb01b3ced42965af74e1fcc01d12aba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="restrictions-on-the-smtp-host-property"></a>Restricciones de la propiedad de Host de SMTP
La propiedad de host SMTP es una cadena que especifica el servidor SMTP que usará el adaptador de SMTP para enviar mensajes desde el servidor BizTalk.  
  
 Las siguientes reglas y restricciones se aplican a esta propiedad:  
  
-   Esta propiedad se debe configurar en el controlador de adaptador, en el extremo o en ambos.  
  
-   La propiedad del servidor SMTP no puede contener los siguientes caracteres: ' ~! @ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< > /, ?;  
  
-   La longitud del nombre del servidor SMTP no debe exceder 256 caracteres.  
  
 El adaptador de SMTP valida siempre el nombre del host SMTP en tiempo de diseño usando las reglas mencionadas anteriormente. Además, el adaptador de SMTP valida el nombre del host SMTP en tiempo de ejecución si se envía un mensaje a través de un puerto dinámico con el adaptador de SMTP.  
  
## <a name="see-also"></a>Vea también  
 [Restricciones al configurar el adaptador de SMTP](../core/restrictions-when-configuring-the-smtp-adapter.md)