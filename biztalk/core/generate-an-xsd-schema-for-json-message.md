---
title: Generar un esquema XSD para mensajes JSON | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5453b76c-b282-442f-9eb1-6c2628b38ad5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88caf75d312179cd45bb1b3b421d6c2c7f25c2a8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="generate-an-xsd-schema-for-json-message"></a>Generar un esquema XSD para mensajes JSON
> [!NOTE]
>  Este tutorial solo se aplica a BizTalk Server.  
  
 En esta solución, una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje JSON. Para que la aplicación pueda procesar el mensaje, debe convertirlo en esquema XSD. Para ello, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona un asistente para esquemas JSON que crea un esquema XSD a partir de un mensaje JSON.  
  
1.  En Visual Studio, cree un nuevo proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2.  En el Explorador de soluciones, haga clic en el nombre del proyecto > **agregar** > **nuevo elemento** > **Asistente para esquemas JSON**. Proporcione un nombre para el esquema (`PO.xsd`) y, a continuación, haga clic en **agregar**.  
  
3.  En el Asistente para esquemas de JSON, en la página de bienvenida, haga clic en **siguiente**.  
  
4.  En la página Información del esquema JSON, proporcione la ubicación del archivo de pedido de compra JSON que se envía a la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Proporcione un nombre de nodo raíz, un espacio de nombres de destino y, a continuación, haga clic en **finalizar**.  
  
     ![Esquema XSD generado para JSON](../core/media/btsjson-wizard.png "BTSJSON_Wizard")  
  
5.  Con esto se agrega un esquema con el nombre especificado al proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El archivo de esquema generado (**PO.xsd**) también se proporciona con el ejemplo.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes JSON con BizTalk Server](../core/processing-json-messages-using-biztalk-server.md)