---
title: "Paso 3B: agregar un FILEACT ubicación de recepción para el escenario en tiempo real de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e086c86-1525-4cef-b7e5-a66e14bd8d4f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d97c2f58639814bda45a23c115fea0c3708c2579
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario"></a>Paso 3B: agregar un FILEACT ubicación de recepción para el escenario en tiempo real de FileAct
Antes de comenzar este paso, debe completar [paso 3A: agregar una ubicación de recepción de archivo para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md).  
  
### <a name="to-add-a-fileact-receive-location"></a>Para agregar ubicación de recepción de un FILEACT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**  
  
4.  En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, Tutorial_FA_HandleRequestOneWay_RealTime.  
  
5.  En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.  
  
6.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **FILEACT**, y a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte FILEACT** diálogo cuadro, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Contraseña**|Escriba la contraseña que usa para conectarse a SAG. Para obtener más información, consulte la Ayuda de SAG.|  
    |**Nombre de usuario.**|Escriba el nombre de usuario que utiliza para conectarse a SAG.|  
    |**Nombre de la aplicación**|Escriba la dirección del servidor \<nombre de la interfaz de aplicación > para el SAG cuadro enrutamiento conjunto.|  
    |**Modo de cifrado**|En la lista desplegable, seleccione **avanzadas**.|  
    |**Modo de FACrypto**|En la lista desplegable, seleccione **avanzadas**.|  
    |**LogMessages**|En la lista desplegable, seleccione **TRUE**. Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.|  
    |**MemberRef**|En la lista desplegable, seleccione **ResponsePayload**.|  
    |**Indicador de sin repudio**|En la lista desplegable, seleccione **FALSE**.|  
    |**Servicio de respuesta**|Escriba la correspondiente \<Respondedor > cadena, según su aprovisionamiento con SWIFT.|  
    |**ResponseCrypto**|En la lista desplegable, seleccione **FALSE**.|  
    |**Indicador de confirmación**|En la lista desplegable, seleccione **ResponsePayload**.|  
    |**FileCompression**|En la lista desplegable, seleccione **ninguno**.|  
    |**PhysicalFolderName**|Escriba el nombre de la carpeta en el servidor. Por ejemplo, C:\Fileact\ServerLocation.|  
    |**SubscribeFileEvents**|En la lista desplegable, seleccione **FALSE**.|  
    |**TransferAnswer**|En la lista desplegable, seleccione **aceptado**.|  
    |**AllFileEvents**|En la lista desplegable, seleccione **TRUE**.|  
    |**Extremo de eventos**|Escriba el extremo adecuado para el conjunto de enrutamiento SAG. Este valor debe coincidir con el punto de conexión de SnL que configuró en SAG.|  
    |**FullFileStatus**|En la lista desplegable, seleccione **TRUE**.|  
    |**Timeout**|Escriba un número adecuado de segundos antes de que se realizarán el tiempo de espera.|  
    |**Adquirir cola**|Deje el valor predeterminado de esta propiedad. Esta propiedad se utiliza para escenarios de almacenamiento y reenvío.|  
    |**ForceAcquire**|Deje el valor predeterminado de esta propiedad. Esta propiedad se utiliza para escenarios de almacenamiento y reenvío.|  
    |**Ordenar por**|Deje el valor predeterminado de esta propiedad. Esta propiedad se utiliza para escenarios de almacenamiento y reenvío.|  
    |**Sesión de inserción**|Deje el valor predeterminado de esta propiedad. Esta propiedad se utiliza para escenarios de almacenamiento y reenvío.|  
    |**Modo de recuperación**|Deje el valor predeterminado de esta propiedad. Esta propiedad se utiliza para escenarios de almacenamiento y reenvío.|  
    |**Extremo SNL**|Deje el valor predeterminado de esta propiedad. Esta propiedad se utiliza para escenarios de almacenamiento y reenvío.|  
  
8.  Haga clic en **Aceptar**.  
  
9. En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de recepción**|En la lista desplegable, seleccione **BizTalkServerIsolatedHost**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
10. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes de Sw:HandleRequest para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [Paso 3D: agregar un puerto de envío de FILEACT para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)   
 [Paso 3E: agregar un puerto de envío de archivo para capturar los mensajes de Sw:ExchangeFileResponse para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)