---
title: Cómo configurar el envío del adaptador de MQSeries y controladores de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, MQSeries adapters
- configuring [MQSeries adapters], receive handlers
- MQSeries adapters, send handlers
- MQSeries adapters, receive handlers
- send handlers, MQSeries adapters
- configuring [MQSeries adapters], send handlers
ms.assetid: e1cfc415-50d2-440b-9301-ad69da28ad3e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a1e933f62adaf4e17fae5334e65f50610fb6f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248236"
---
# <a name="how-to-configure-mqseries-adapter-send-and-receive-handlers"></a>Controladores de recepción y envío de cómo configurar el adaptador de MQSeries
Puede configurar algunas propiedades para los controladores de recepción y envío del adaptador de MQSeries mediante la consola de administración de BizTalk Server. El proceso se describe en [cómo configurar ubicaciones de recepción de MQSeries adaptador y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) establece los valores para la mayoría de las propiedades del controlador de envío.  
  
## <a name="to-configure-the-send-and-receive-handlers"></a>Para configurar los controladores de envío y recepción  
 Siga estos pasos para configurar controladores de envío y recepción para el adaptador de MQSeries:  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, haga clic para expandir **configuración de plataforma**y, a continuación, haga clic en Expanda **adaptadores**.  
  
3.  En la lista de adaptadores expandida, seleccione **MQSeries**. La lista de controladores de envío y recepción enlazados al adaptador de MQSeries aparece en el panel de la derecha.  
  
4.  En el panel derecho, haga doble clic en un controlador de envío o recepción.  
  
5.  En el **propiedades de controlador de adaptador** cuadro de diálogo, haga clic en **propiedades**.  
  
6.  En el **propiedades de transporte MQSeries** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Número máximo de mensajes en lote**|Definir el número máximo de mensajes en un lote. Sólo se aplica al controlador de envío.|  
    |**Server**|Nombre del equipo que ejecuta MQSeries Server para Windows.|  
  
7.  Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Las propiedades de puerto de envío y ubicación de recepción invalidan los valores de los controladores de envío y recepción. Si las propiedades del puerto de envío y la ubicación de recepción no tienen valores, el adaptador utiliza los valores del controlador de envío y recepción respectivamente.  
  
8.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar MQSeries adaptador ubicaciones de recepción y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)   
 [Configurar el adaptador de MQSeries](../core/configuring-the-mqseries-adapter.md)