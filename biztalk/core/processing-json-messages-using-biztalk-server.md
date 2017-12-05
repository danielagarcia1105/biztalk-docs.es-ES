---
title: Procesamiento de mensajes JSON con BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6db1421-9478-477c-8645-09eefba06246
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c2e4adac7c7d1503a49f68208e45e09f86b67ac
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="processing-json-messages-using-biztalk-server"></a>Procesamiento de mensajes JSON con BizTalk Server
> [!NOTE]
>  Este tutorial solo se aplica a BizTalk Server.  
  
 En este tutorial se muestra cómo procesar mensajes JSON con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El tutorial usa componentes de canalización personalizados, ahora están disponibles con BizTalk Server. Estos componentes de canalización convierten el mensaje JSON en XML mientras se recibe el mensaje en la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y convierten el mensaje de XML a JSON mientras se envía.  
  
## <a name="what-does-this-tutorial-do"></a>¿Qué hace este tutorial?  
 Para mostrar el procesamiento de JSON, creamos un servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que hace lo siguiente, en el orden especificado:  
  
1.  Recibe un pedido de compra JSON y, en la canalización de recepción, usa un componente descodificador de JSON para transformar el mensaje JSON en un mensaje XML.  
  
2.  Transforma el pedido de compra XML en una factura XML usando una asignación.  
  
3.  En la canalización de envío, usa un codificador JSON para transformar la factura XML en una factura JSON y la envía.  
  
 ![Procesamiento de mensajes JSON en BizTalk Server](../core/media/btsjson-flow.png "BTSJSON_Flow")  
  
## <a name="how-to-use-this-tutorial"></a>Cómo usar este tutorial  
 Este tutorial se basa en una muestra (**BTSJSON**) que puede descargarse desde el [MSDN Code Gallery](http://go.microsoft.com/fwlink/?LinkId=403197). Puede usar el ejemplo y seguir este tutorial para comprender cómo se ha compilado el ejemplo. O bien, puede usar este tutorial para crear su propia solución desde cero. El tutorial está pensado para la segunda opción, de forma que pueda comprender cómo se compiló esta solución. También, en la medida de lo posible, el tutorial es coherente con el ejemplo y usa los mismos nombres para los artefactos (por ejemplo, esquemas, transformaciones) que se usan en el ejemplo.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Generar un esquema XSD para mensajes JSON](../core/generate-an-xsd-schema-for-json-message.md)  
  
-   [Crear canalizaciones personalizadas para procesar mensajes JSON](../core/create-custom-pipelines-to-process-json-messages.md)  
  
-   [Crear una orquestación de BizTalk Server](../core/create-a-biztalk-server-orchestration.md)  
  
-   [Implementar y probar la aplicación](../core/deploy-and-test-the-application.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales de BizTalk Server](../core/biztalk-server-tutorials.md)