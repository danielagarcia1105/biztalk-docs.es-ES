---
title: "Creación de envío y puertos de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, receive ports
- adapters [JD Edwards OneWorld adapters], receive ports
- creating, receive ports [JD Edwards OneWorld adapters]
- send ports, creating [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], send ports
- adapters [JD Edwards OneWorld adapters], transport properties
- JD Edwards OneWorld adapters, send ports
- JD Edwards OneWorld adapters, transport properties
- receive ports, creating [JD Edwards OneWorld adapters]
- creating, send ports [JD Edwards OneWorld adapters]
ms.assetid: fb4ca8b1-40d9-4beb-a791-554086f8ca98
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da4b117ca2d032ef1dc10731128acca903a51790
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="creating-send-and-receive-ports"></a>Creación de envío y puertos de recepción
Use los procedimientos siguientes para crear puertos de envío y recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el adaptador de BizTalk para JD Edwards OneWorld.  
  
## <a name="creating-a-port"></a>Creación de un puerto  
  
#### <a name="to-create-a-send-port"></a>Procedimiento para crear un puerto de envío  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**y, a continuación, expanda el aplicación para la que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío** y haga clic en **New**y, a continuación, haga clic en **puerto de petición-respuesta estático**.  
  
4.  En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:  
  
    -   En el **nombre** , escriba un nombre de puerto de envío (por ejemplo, `SSOSendToJDE OneWorld`).  
  
    -   Desde el **tipo** lista desplegable, seleccione **JDEdwards**.  
  
    -   Desde el **controlador de envío** lista desplegable, seleccione la dirección del controlador de envío.  
  
    -   Para el **canalización de envío**, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.  
  
    -   Para el **canalización de recepción**, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="creating-a-receive-port"></a>Crear un puerto de recepción  
  
#### <a name="to-create-a-receive-port"></a>Para crear un puerto de recepción  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**y, a continuación, expanda el aplicación para la que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de recepción** y haga clic en **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
     En el **propiedades del puerto de recepción unidireccional** pantalla, en la **nombre** , escriba `ReceiveFromHttp`y, a continuación, haga clic en **Aceptar**.  
  
4.  Escriba la siguiente información en el **propiedades del puerto de recepción unidireccional** ventana:  
  
    -   En el **nombre** , escriba `ReceiveFromHTTP`.  
  
    -   Para el **tipo de transporte**, seleccione **HTTP**.  
  
5.  Haga clic en el botón de puntos suspensivos (…) de la dirección (URI).  
  
     ![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")  
  
    1.  Establezca el directorio virtual más la extensión ISAPI, /mySSODemo/BTSHTTPReceive.dll.  
  
    2.  Seleccione **devolver controlador de correlación en caso de éxito**.  
  
    3.  Seleccione **Use Single Sign-On**y, a continuación, haga clic en **Aceptar**.  
  
6.  En el **controlador de recepción** lista desplegable, seleccione **BizTalkServerIsolatedHost**.  
  
     ![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")  
  
7.  Para el **canalización de recepción**, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Agregar los artefactos a la administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [Agregar los artefactos a la administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [Seguridad en el adaptador](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)