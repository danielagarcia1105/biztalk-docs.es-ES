---
title: Cómo configurar controlador de recepción de WCF-NetTcp | Documentos de Microsoft
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
ms.openlocfilehash: 69598bc1ce0bda41269fa91a0618fb040e741b28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247524"
---
# <a name="how-to-configure-a-wcf-nettcp-receive-handler"></a>Cómo configurar un controlador de recepción WCF-NetTcp
Utilice este procedimiento para configurar un controlador de recepción WCF-NetTcp.  
  
### <a name="to-change-global-variables-for-a-wcf-nettcp-receive-handler"></a>Para cambiar las variables globales del controlador de recepción WCF-NetTcp  
  
1.  En la consola de administración de BizTalk, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **Adaptadores**.  
  
2.  En la lista de adaptadores expandida, haga clic en **WCF-NetTcp**, en el panel derecho, haga el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host al que se asociará el controlador de recepción.  
  
4.  En el **General** , haga clic en **propiedades**, en la **controlador de recepción** ficha, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Número máximo de conexiones**|Especificar el número máximo de conexiones que el agente de escucha puede tener esperando la aceptación de la aplicación. Cuando se supera este valor de cuota, se interrumpen las nuevas conexiones entrantes en lugar de esperar la aceptación.<br /><br /> El valor predeterminado es 10.|  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de WCF-NetTcp](../core/configuring-the-wcf-nettcp-adapter.md)   
 [Publicar servicios WCF](../core/publishing-wcf-services.md)