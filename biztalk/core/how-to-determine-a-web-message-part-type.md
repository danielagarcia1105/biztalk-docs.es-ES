---
title: "Cómo determinar un tipo de parte de mensaje Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web messages, message types
- Web services, Web messages
- Web messages, parts
ms.assetid: bdd1f604-ec35-41e3-b5a8-1e0ad0193eff
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dd01d549ffbc6c299124b63df73b82f874cb4d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-determine-a-web-message-part-type"></a>Cómo determinar un tipo de parte de mensaje web
Se puede determinar si un tipo de parte de un mensaje Web es un tipo .NET primitivo o un tipo de esquema mediante la ventana Propiedades de un tipo de mensaje Web concreto.  
  
### <a name="to-determine-a-web-message-part-type"></a>Para determinar un tipo de parte de mensaje Web  
  
1.  Con una orquestación abierta, en el **vista** menú, haga clic en **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.  
  
2.  Expanda el **tipos de mensaje de varias partes** nodo y, a continuación, expanda un tipo de mensaje Web.  
  
3.  Seleccione una parte de un mensaje.  
  
     Una firma de parte de mensaje Web que comienza por  **\<* espacio de nombres predeterminado del proyecto*>.\< *Nombre de referencia web*>. Referencia. \< *raíz del esquema*> ** es un tipo de esquema. El  **\<* raíz del esquema*> ** parte del tipo es el elemento raíz del esquema de referencia Web que construye la parte del mensaje Web. En caso contrario, la firma de la parte de mensaje es un tipo .NET primitivo como **System.String** o **System.Int32**.  
  
## <a name="see-also"></a>Vea también  
 [Construcción de mensajes Web](../core/constructing-web-messages.md)