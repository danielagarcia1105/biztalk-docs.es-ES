---
title: Cómo configurar un controlador de envío WCF-NetNamedPipe | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, global adapters
- configuring [WCF-NetNamedPipe adapters], global adapters
- send handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], send handlers
ms.assetid: 1f281649-d09f-44eb-8af5-1f83233fab60
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fc9ef8086ae0cda04da3ecdc7eacbfcb6d01f14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970229"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-send-handler"></a>Cómo configurar un controlador de envío WCF-NetNamedPipe
Utilice el siguiente procedimiento para configurar un controlador de envío WCF-NetNamedPipe.  

### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-send-handler"></a>Para cambiar las variables globales del controlador de envío WCF-NetNamedPipe  

1. En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.  

2. En la lista de adaptadores expandida, haga clic en **WCF-NetNamedPipe**, en el panel derecho, el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.  

3. En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de envío.  

4. En el **General** , haga clic **propiedades**. En el **controlador de envío** ficha, realice lo siguiente:  


   |        Use         |                                                                                                                                                                                                                                                                             Para                                                                                                                                                                                                                                                                             |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Número máximo de conexiones** | Especificar el número máximo de conexiones salientes para cada extremo almacenado en la caché del grupo de conexiones. Esto limita el número de conexiones que se almacena en la caché para cada extremo remoto único. Es conveniente establecer un valor que sea mayor que el número máximo de conexiones que espera que se almacene en la caché de cualquier extremo remoto único. Si el número de conexiones salientes activas supera el valor máximo, puede parecer que el servicio no responde a los puertos de envío WCF-NetNamedPipe que se ejecutan en este controlador de envío.<br /><br /> El valor predeterminado es 10. |


5. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Consumir servicios WCF](../core/consuming-wcf-services.md)   
 [Configuración del adaptador de WCF-NetNamedPipe](../core/configuring-the-wcf-netnamedpipe-adapter.md)