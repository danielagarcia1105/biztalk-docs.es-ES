---
title: 'Paso 8: Configurar el puerto de 997 envío | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4780c491-9f1a-4f13-b346-6a2e1801ec09
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd203912dbf77c3e677f8f1180ba312c02829699
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022762"
---
# <a name="step-8-configure-the-997-send-port"></a>Paso 8: Configurar el puerto de 997 envío
![Paso 8 de 11](../core/media/tut-step8-of-11.gif "Tut_Step8_of_11")  
  
 En este paso, configurará un puerto de envío para enviar el mensaje 997 al socio comercial: Este puerto de envío usa la canalización de envío AS2EdiSend para transportar una confirmación 997 con codificación EDIINT/AS2 a la carpeta _997ToFabrikam.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-create-the-sendasync997-send-port"></a>Para crear el puerto de envío Send_Async_997  
  
1. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, bajo el nodo BizTalk Application 1, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático** .  
  
   > [!NOTE]
   >  Usará un puerto de envío unidireccional estático, ya que no se ha configurado ningún MDN para la entidad Fabrikam como un receptor de mensaje AS2.  
  
2. En el **propiedades de puerto de envío** diálogo cuadro, asigne el nombre del puerto de envío **Send_Async_997**. Seleccione **HTTP** para **tipo**y, a continuación, haga clic en **configurar**.  
  
3. En el **propiedades de transporte HTTP** cuadro de diálogo para **dirección URL de destino**, escriba `http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam`. Borrar **Habilitar codificación fragmentada** y, a continuación, haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  El **dirección URL de destino** configuración garantiza que el puerto de envío enviará el mensaje 997 al directorio virtual de Fabrikam. El archivo Default.aspx.cs asociado a este directorio virtual generará el 997 con una extensión .msg y lo enviará a la carpeta de destino.  
  
4. En el **propiedades de puerto de envío** cuadro de diálogo, seleccione **AS2EdiSend** para **canalización de envío**.  
  
5. Haga clic en **filtros** en el árbol de consola. Para **propiedad**, seleccione **BTS. MessageType**. Para **operador**, seleccione **==**. Para **valor**, escriba `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.  
  
   > [!NOTE]
   >  Este filtro garantiza que el puerto de envío sólo recogerá confirmaciones 997 del cuadro de mensajes.  
  
6. Haga clic en **Aceptar**.  
  
7. En el **puertos de envío** panel de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **Send_Async_997** puerto de envío y, a continuación, haga clic en **iniciar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar el puerto de envío (**Send_Payload_EdiXml**) para enviar la carga EDI a Contoso, como se describe en [paso 9: configurar el puerto de envío EDI carga](../core/step-9-configure-the-edi-payload-send-port.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server envía mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md)   
 [Configuración de un puerto de envío estático para mensajes a través de AS2](../core/configuring-a-static-send-port-for-messages-over-as2.md)