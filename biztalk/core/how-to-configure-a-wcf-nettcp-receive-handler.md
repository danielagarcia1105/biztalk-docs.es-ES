---
title: Cómo configurar controlador de recepción WCF-NetTcp | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, global variables
- receive handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], global variables
- configuring [WCF-NetTcp adapters], receive handlers
ms.assetid: a4a283d1-21de-4d6b-9cb5-f2f9f823903b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8d7e68e4df5a729aae7f84932b53d319fea0114
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009949"
---
# <a name="how-to-configure-a-wcf-nettcp-receive-handler"></a>Cómo configurar un controlador de recepción WCF-NetTcp
Utilice este procedimiento para configurar un controlador de recepción WCF-NetTcp.  

### <a name="to-change-global-variables-for-a-wcf-nettcp-receive-handler"></a>Para cambiar las variables globales del controlador de recepción WCF-NetTcp  

1. En la consola de administración de BizTalk, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.  

2. En la lista de adaptadores expandida, haga clic en **WCF-NetTcp**, en el panel derecho, el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.  

3. En el **propiedades de controlador de adaptador** cuadro de diálogo el **General** ficha la **nombre de Host** lista, seleccione el host con el que se asociará el controlador de recepción.  

4. En el **General** , haga clic **propiedades**, en el **controlador de recepción** ficha, realice lo siguiente.  


   |        Use         |                                                                                                                         Para                                                                                                                         |
   |-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Número máximo de conexiones** | Especificar el número máximo de conexiones que el agente de escucha puede tener esperando la aceptación de la aplicación. Cuando se supera este valor de cuota, se interrumpen las nuevas conexiones entrantes en lugar de esperar la aceptación.<br /><br /> El valor predeterminado es 10. |


5. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Configuración del adaptador de WCF-NetTcp](../core/configuring-the-wcf-nettcp-adapter.md)   
 [Publicación de servicios WCF](../core/publishing-wcf-services.md)