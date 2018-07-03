---
title: Generar un esquema XSD para mensajes JSON | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5453b76c-b282-442f-9eb1-6c2628b38ad5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b95af2f3a44454aa59138cd6f77b7f7195cbb02b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971141"
---
# <a name="generate-an-xsd-schema-for-json-message"></a>Generar un esquema XSD para mensajes JSON
> [!NOTE]
>  Este tutorial solo se aplica a BizTalk Server.  
  
 En esta solución, una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje JSON. Para que la aplicación pueda procesar el mensaje, debe convertirlo en esquema XSD. Para ello, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona un asistente para esquemas JSON que crea un esquema XSD a partir de un mensaje JSON.  
  
1. En Visual Studio, cree un nuevo proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2. En el Explorador de soluciones, haga clic en el nombre del proyecto > **agregar** > **nuevo elemento** > **Asistente para esquemas JSON**. Proporcione un nombre para el esquema (`PO.xsd`) y, a continuación, haga clic en **agregar**.  
  
3. En el Asistente para esquema de JSON, en la página de bienvenida, haga clic en **siguiente**.  
  
4. En la página Información del esquema JSON, proporcione la ubicación del archivo de pedido de compra JSON que se envía a la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Proporcione un nombre de nodo raíz, un espacio de nombres de destino y, a continuación, haga clic en **finalizar**.  
  
    ![Esquema XSD generado para JSON](../core/media/btsjson-wizard.png "BTSJSON_Wizard")  
  
5. Con esto se agrega un esquema con el nombre especificado al proyecto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El archivo de esquema generado (**PO.xsd**) también se proporciona con el ejemplo.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes JSON con BizTalk Server](../core/processing-json-messages-using-biztalk-server.md)