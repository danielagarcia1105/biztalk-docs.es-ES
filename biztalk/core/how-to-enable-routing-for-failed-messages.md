---
title: Cómo habilitar enrutamiento para mensajes erróneos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d33beed4-1ae2-4282-95ac-5d68aab7fb5d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c00e49afa528bc0008d73272dca561d461660367
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008493"
---
# <a name="how-to-enable-routing-for-failed-messages"></a>Cómo habilitar el enrutamiento para mensajes con errores
El enrutamiento de mensajes con errores es una propiedad de los puertos de envío y recepción y se habilita mediante la opción “Habilitar enrutamiento para mensajes con errores” de la página de propiedades del puerto.  
  
> [!NOTE]
>  La configuración en un puerto de recepción se aplica a todas las ubicaciones de recepción asociadas con dicho puerto.  
  
> [!NOTE]
>  La configuración en un puerto de envío se aplica a los transportes tanto principales como de reserva.  
  
### <a name="to-configure-failed-message-routing-for-a-receive-port-this-applies-to-both-one-way-and-request-response-receive-ports"></a>Para configurar el enrutamiento de mensajes con errores en un puerto de recepción (se aplica a los puertos de recepción tanto unidireccionales como de solicitud-respuesta)  
  
1. Abra la consola de administración de BizTalk Server.  
  
2. Expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación a la que pertenece el puerto de envío.  
  
3. Haga clic en el **puertos de recepción** carpeta.  
  
4. En el panel de la derecha, haga doble clic en el nombre del puerto de recepción que desea configurar.  
  
5. En la página de propiedades del puerto de recepción, en el panel izquierdo, seleccione el **General** categoría.  
  
6. En el panel derecho, seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación y, a continuación, haga clic en **aplicar**.  
  
### <a name="to-configure-failed-message-routing-for-a-send-port-this-applies-only-to-static-one-way-and-static-solicit-response-send-ports"></a>Para configurar el enrutamiento de mensajes con errores en un puerto de envío (se aplica solo a los puertos de envío unidireccionales estáticos y de petición-respuesta estáticos)  
  
1. Abra la consola de administración de BizTalk Server.  
  
2. Expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación a la que pertenece el puerto de envío.  
  
3. Haga clic en el **puertos de envío** carpeta.  
  
4. En el panel de la derecha, haga doble clic en el nombre del puerto de envío que desea configurar.  
  
5. En la página de propiedades del puerto de envío, en el panel izquierdo, seleccione el **opciones avanzadas de transporte** categoría.  
  
6. En el panel derecho, en el **opciones de transporte** cuadro de grupo, seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación y, a continuación, haga clic en **aplicar**.  
  
## <a name="see-also"></a>Vea también  
 [Tratamiento de errores](../core/error-handling.md)