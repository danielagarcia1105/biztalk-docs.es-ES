---
title: Cómo configurar controlador de recepción WCF-NetNamedPipe | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [WCF-NetNamedPipe adapters], global variables
- receive handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], receive handlers
- WCF-NetNamedPipe adapters, global variables
ms.assetid: f7ab2228-1049-40f0-87f7-6330a8f40cfe
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2601bcd6e68f8752699474c4d02295d353064083
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022906"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-receive-handler"></a>Cómo configurar un controlador de recepción WCF-NetNamedPipe
Utilice este procedimiento para configurar un controlador de recepción WCF-NetNamedPipe.  

### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-receive-handler"></a>Para cambiar las variables globales del controlador de recepción WCF-NetNamedPipe  

1. En la consola de administración de BizTalk, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.  

2. En la lista de adaptadores expandida, haga clic en **WCF-NetNamedPipe**, en el panel derecho, el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.  

3. En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de recepción.  

4. En el **General** , haga clic **propiedades**. En el **controlador de recepción** ficha, realice lo siguiente:  


   |        Use         |                                                                                                                         Para                                                                                                                         |
   |-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Número máximo de conexiones** | Especificar el número máximo de conexiones que el agente de escucha puede tener esperando la aceptación de la aplicación. Cuando se supera este valor de cuota, se interrumpen las nuevas conexiones entrantes en lugar de esperar la aceptación.<br /><br /> El valor predeterminado es 10. |


5. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Publicación de servicios WCF](../core/publishing-wcf-services.md)   
 [Configuración del adaptador de WCF-NetNamedPipe](../core/configuring-the-wcf-netnamedpipe-adapter.md)