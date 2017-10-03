---
title: "Cómo configurar controlador de recepción de WCF-NetNamedPipe | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [WCF-NetNamedPipe adapters], global variables
- receive handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], receive handlers
- WCF-NetNamedPipe adapters, global variables
ms.assetid: f7ab2228-1049-40f0-87f7-6330a8f40cfe
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9339cca7f8065d3412686cfcc84d84028ef39faf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-netnamedpipe-receive-handler"></a>Cómo configurar un controlador de recepción WCF-NetNamedPipe
Utilice este procedimiento para configurar un controlador de recepción WCF-NetNamedPipe.  
  
### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-receive-handler"></a>Para cambiar las variables globales del controlador de recepción WCF-NetNamedPipe  
  
1.  En la consola de administración de BizTalk, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.  
  
2.  En la lista de adaptadores expandida, haga clic en **WCF-NetNamedPipe**, en el panel derecho, haga el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host al que se asociará el controlador de recepción.  
  
4.  En el **General** , haga clic en **propiedades**. En el **controlador de recepción** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Número máximo de conexiones**|Especificar el número máximo de conexiones que el agente de escucha puede tener esperando la aceptación de la aplicación. Cuando se supera este valor de cuota, se interrumpen las nuevas conexiones entrantes en lugar de esperar la aceptación.<br /><br /> El valor predeterminado es 10.|  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Publicar servicios WCF](../core/publishing-wcf-services.md)   
 [Configurar el adaptador de WCF-NetNamedPipe](../core/configuring-the-wcf-netnamedpipe-adapter.md)