---
title: "Paso 3B: agregar un FILEACT ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f30bb7d-1efb-4350-8809-be35f5634ea0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c717d23886860363ca9c94d1eec79195f873fff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3b-add-a-fileact-receive-location-for-the-fileact-store-and-forward-scenario"></a>Paso 3B: agregar un FILEACT ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct
Antes de comenzar este paso, debe completar [paso 3A: agregar una ubicación de recepción de archivo para el escenario de al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md).  
  
### <a name="to-add-an-fileact-receive-location"></a>Para agregar ubicación de recepción de un FILEACT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**  
  
4.  En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, Tutorial_FA_HandleRequestOneWay_SnF.  
  
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
    |**FileCompression**|En la lista desplegable, seleccione ninguno.|  
    |**PhysicalFolderName**|Escriba el nombre de la carpeta en el servidor. Por ejemplo, C:\Fileact\ServerLocation.|  
    |**SubscribeFileEvents**|En la lista desplegable, seleccione **FALSE**.|  
    |**TransferAnswer**|En la lista desplegable, seleccione **aceptado**.|  
    |**AllFileEvents**|En la lista desplegable, seleccione **TRUE**.|  
    |**Extremo de eventos**|Escriba el extremo SAG adecuado.|  
    |**FullFileStatus**|En la lista desplegable, seleccione **TRUE**.|  
    |**Timeout**|Escriba un número adecuado de segundos antes de que se realizarán el tiempo de espera.|  
    |**Adquirir cola**|Escriba el nombre de cola, en función de su aprovisionamiento con SWIFT.|  
    |**ForceAcquire**|En la lista desplegable, seleccione **TRUE**.|  
    |**Ordenar por**|En la lista desplegable, seleccione **FileAct**.|  
    |**Sesión de inserción**|En la lista desplegable, seleccione **TRUE**.|  
    |**Modo de recuperación**|En la lista desplegable, seleccione **FALSE**.|  
    |**Extremo SNL**|Escriba el extremo adecuado para el conjunto de enrutamiento SAG. Este valor debe coincidir con el punto de conexión de SnL que configuró en SAG.|  
  
8.  Haga clic en **Aceptar**.  
  
9. En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de recepción**|En la lista desplegable, seleccione **BizTalkServerIsolatedHost**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
10. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [Paso 3A: agregar un archivo de ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)   
 [Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes Sw:HandleFileRequest y Sw:HandleSnFRequest para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
 [Paso 3D: agregar un puerto de envío de FILEACT para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)