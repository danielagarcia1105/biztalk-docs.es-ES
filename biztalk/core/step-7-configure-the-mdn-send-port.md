---
title: 'Paso 7: Configurar el puerto de envío MDN | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 983033ac-9d32-47c8-9bb8-b4161bcdf183
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e65ac8f264e1d8784c97645383b055391397da1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987749"
---
# <a name="step-7-configure-the-mdn-send-port"></a>Paso 7: Configurar el puerto de envío MDN
![Paso 7 de 11](../core/media/tut-step7-of-11.gif "Tut_Step7_of_11")  
  
 En este paso, se establecerá un puerto de envío dinámico para enviar un MDN asincrónico para el \\carpeta _MDNToFabrikam. Este puerto de envío utiliza la canalización de envío AS2Send para generar la respuesta MDN saliente. Ya que se trata de un puerto de envío dinámico, utilizará la dirección en la línea Receipt-Delivery-Option en el encabezado del mensaje para enrutar el mensaje a la \\carpeta _MDNToFabrikam. Dicha dirección es la del directorio virtual de Fabrikam. El archivo Default.aspx.cs asociado a este directorio virtual generará el MDN con una extensión .msg y enviará el archivo a la carpeta de destino (también especificada en la línea Receipt-Delivery-Option).  
  
> [!NOTE]
>  También puede configurar el acuerdo para enviar el MDN a otra dirección, invalidando la configuración de mensaje con la nueva configuración de acuerdo. Para obtener más información, vea  
  
 En este ejemplo el MDN se envía usando un puerto de envío dinámico; sin embargo, también puede usar un puerto de envío estático para enviar el MDN a una dirección estática. Para obtener más información, consulte [configurar un puerto de envío estático para MDN asíncronos a través de AS2](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md) y [configurar un puerto de envío dinámico para MDN asíncronos a través de AS2](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-create-the-sendasyncmdn-send-port"></a>Para crear el puerto de envío Send_Async_MDN:  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, bajo el nodo BizTalk Application 1, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío de unidireccionaldinámico**.  
  
2. En el **propiedades de puerto de envío** cuadro de diálogo, el envío de nombre de puerto como **Send_Async_MDN**.  
  
3. Seleccione **AS2Send** para **canalización de envío**.  
  
   > [!NOTE]
   >  Se utiliza la canalización AS2Send debido a que no se requiere procesamiento de EDI para el MDN.  
  
4. Haga clic en **filtros** en el árbol de consola. En el panel filtros, seleccione **EdiIntAS.IsAS2AsynchronousMdn** para **propiedad**, **==** para **operador**y escriba **True** para **valor**.  
  
   > [!NOTE]
   >  Este filtro garantiza que el puerto de envío dinámico sólo recoge los MDN asíncronos del cuadro de mensajes.  
  
5. Haga clic en **Aceptar**.  
  
6. En el **puertos de envío** panel de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **Send_Async_MDN**y, a continuación, haga clic en **iniciar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar el puerto de envío (**Send_Async_997**) para enviar el 997 confirmación de nuevo a Fabrikam, tal como se describe en [paso 8: configurar el puerto de envío 997](../core/step-8-configure-the-997-send-port.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server envía mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md)   
 [Configurar un puerto de envío estático para MDN asíncronos a través de AS2](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)   
 [Configuración de un puerto de envío dinámico para mensajes a través de AS2](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)