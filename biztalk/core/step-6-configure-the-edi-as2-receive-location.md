---
title: "Paso 6: Configurar EDI-AS2 ubicación de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 167f8ba2-d38b-4088-863b-2bd90c2a12a2
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bbf1fce88301960a28c19fa20c9996282ce4619
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-configure-the-edi-as2-receive-location"></a>Paso 6: Configurar EDI-AS2 ubicación de recepción
![Paso 6 de 11](../core/media/tut-step6-of-11.gif "Tut_Step6_of_11")  
  
 En este paso, configure un puerto de recepción unidireccional que reciba el mensaje EDI de la entidad de Fabrikam. Esta ubicación de recepción utiliza la canalización de recepción AS2EdiReceive para procesar el mensaje EDI/AS2 entrante. El mensaje se enviará a la ubicación de recepción mediante la aplicación sender.exe a través del directorio virtual de Contoso con la extensión ISAPI BTSHTTPReceive.dll.  
  
 En este tutorial, establecerá un puerto de envío dinámico para enviar la respuesta MDN de forma asíncrona. En este escenario, sólo es necesario un puerto de recepción unidireccional. Sin embargo, puede también cambiar Sender.exe para enviar un mensaje AS2 que especifica un MDN sincrónico. Tendrá que crear un puerto de recepción de solicitud-respuesta bidireccional para devolver el MDN. Para obtener más información, vea la sección "para probar la solución" de [tutorial (AS2): recibir EDI a través de AS2 con un MDN sincrónico](../core/walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-create-the-biztalk-http-receive-location"></a>Para crear la ubicación de recepción HTTP de BizTalk  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, bajo el nodo BizTalk Application 1, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
2.  Nombre del puerto de recepción como **Receive_AS2**.  
  
3.  Haga clic en **ubicaciones de recepción** en el árbol de consola y, a continuación, haga clic en **nuevo**.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, el nombre de la ubicación de recepción **Receive_AS2**, seleccione **HTTP** para **tipo**y, a continuación, Haga clic en **configurar**.  
  
5.  En el **propiedades de transporte HTTP** diálogo cuadro, escriba **/Contoso/BTSHTTPReceive.dll** para **directorio Virtual más extensión ISAPI**. Desactive **devolver controlador de correlación en caso de éxito** y seleccione **suspender solicitudes con errores**. Haga clic en **Aceptar**.  
  
6.  Seleccione **AS2EdiReceive** para el **canalización de recepción**. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
    > [!NOTE]
    >  La canalización de recepción AS2EdiReceive realiza descodificación AS2 y desensamblado EDI.  
  
7.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **ubicaciones de recepción** bajo el nodo BizTalk Application 1, haga clic en **Receive_AS2**y, a continuación, haga clic en **habilitar** .  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar el puerto de envío (**Send_Asynch_MDN**) puerto de envío para enviar el MDN asincrónico a Fabrikam, tal y como se describe en [paso 7: configurar el puerto de envío MDN](../core/step-7-configure-the-mdn-send-port.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md)   
 [Configurar un puerto de recepción de mensajes a través de AS2](../core/configuring-a-receive-port-for-messages-over-as2.md)