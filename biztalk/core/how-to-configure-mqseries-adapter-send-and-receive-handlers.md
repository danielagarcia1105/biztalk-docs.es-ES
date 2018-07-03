---
title: Cómo configurar el envío del adaptador de MQSeries y controladores de recepción | Microsoft Docs
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
ms.openlocfilehash: 88c97b109146dadd1a5cc90710f00c9c8f6620f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988901"
---
# <a name="how-to-configure-mqseries-adapter-send-and-receive-handlers"></a>Cómo configurar el adaptador de MQSeries controladores de recepción y envío
Puede configurar algunas propiedades para los controladores de recepción y envío del adaptador de MQSeries mediante la consola de administración de BizTalk Server. El proceso se describe en [cómo configurar ubicaciones de recepción de MQSeries adaptadores y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) establece los valores para la mayoría de las propiedades del controlador de envío.  

## <a name="to-configure-the-send-and-receive-handlers"></a>Para configurar los controladores de envío y recepción  
 Siga estos pasos para configurar controladores de envío y recepción para el adaptador de MQSeries:  

1. Haga clic en **iniciar**, apunte a **programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, haga clic para expandir **configuración de plataforma**y, a continuación, haga clic en Expanda **adaptadores**.  

3. En la lista de adaptadores expandida, seleccione **MQSeries**. La lista de controladores de envío y recepción enlazados al adaptador de MQSeries aparece en el panel de la derecha.  

4. En el panel derecho, haga doble clic en un controlador de envío o recepción.  

5. En el **propiedades de controlador de adaptador** cuadro de diálogo, haga clic en **propiedades**.  

6. En el **propiedades de transporte MQSeries** diálogo cuadro, realice lo siguiente:  


   |           Use            |                                    Para                                    |
   |-------------------------------|----------------------------------------------------------------------------------|
   | **Número máximo de mensajes en lote** | Definir el número máximo de mensajes en un lote. Sólo se aplica al controlador de envío. |
   |          **Server**           |      Nombre del equipo que ejecuta MQSeries Server para Windows.       |


7. Haga clic en **Aceptar**.  

   > [!NOTE]
   >  Las propiedades de puerto de envío y ubicación de recepción invalidan los valores de los controladores de envío y recepción. Si las propiedades del puerto de envío y la ubicación de recepción no tienen valores, el adaptador utiliza los valores del controlador de envío y recepción respectivamente.  

8. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Cómo configurar MQSeries adaptador ubicaciones de recepción y puertos de envío](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)   
 [Configuración del adaptador de MQSeries](../core/configuring-the-mqseries-adapter.md)