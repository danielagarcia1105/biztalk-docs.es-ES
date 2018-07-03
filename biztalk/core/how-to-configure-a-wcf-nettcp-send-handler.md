---
title: Cómo configurar un controlador de envío WCF-NetTcp | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], send handlers
- WCF-NetTcp adapters, global variables
- configuring [WCF-NetTcp adapters], global variables
ms.assetid: c60fe03d-7e11-4e08-9a24-8ff443eee9c1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5855c7405437d7958f53d679ad2eafc670608c7a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014109"
---
# <a name="how-to-configure-a-wcf-nettcp-send-handler"></a>Cómo configurar un controlador de envío WCF-NetTcp
Para configurar el controlador de envío WCF-NetTcp, siga este procedimiento:  

### <a name="to-change-global-variables-for-a-wcf-nettcp-send-handler"></a>Para cambiar las variables globales de un controlador de envío WCF-NetTcp  

1. En la consola de administración de BizTalk, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.  

2. En la lista de adaptadores expandida, haga clic en **WCF-NetTcp**, en el panel derecho, el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.  

3. En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de envío.  

4. En el **General** , haga clic **propiedades**. En el **controlador de envío** ficha, realice lo siguiente.  


   |        Use         |                                                                                                                                                                                                                                                                          Para                                                                                                                                                                                                                                                                          |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Número máximo de conexiones** | Especificar el número máximo de conexiones salientes para cada extremo almacenado en la caché del grupo de conexiones. Esto limita el número de conexiones que se almacena en la caché para cada extremo remoto único. Es conveniente establecer un valor que sea mayor que el número máximo de conexiones que espera que se almacene en la caché de cualquier extremo remoto único. Si el número de conexiones salientes activas supera el valor máximo, puede parecer que el servicio no responde a los puertos de envío WCF-NetTcp que se ejecutan en este controlador de envío.<br /><br /> El valor predeterminado es 10. |


5. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Consumir servicios WCF](../core/consuming-wcf-services.md)   
 [Configuración del adaptador de WCF-NetTcp](../core/configuring-the-wcf-nettcp-adapter.md)