---
title: "Implementar y probar la aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2c86d5f-1849-4b7d-8061-23f156245f5b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d93284823c2ce5d0c00a1601a5b9ae0aac4643c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="deploy-and-test-the-application"></a>Implementar y probar la aplicación
> [!NOTE]
>  Este tutorial solo se aplica a BizTalk Server.  
  
 En este tema, vamos a compilar, implementar, configurar y probar la aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="build-and-deploy-the-application"></a>Compilar e implementar la aplicación  
  
1.  En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk y, a continuación, haga clic en **propiedades**.  
  
2.  En la página Propiedades, haga clic en la ficha Firma, active la casilla Firmar el ensamblado y, en la lista desplegable, elija la opción para crear un archivo de clave de nombre seguro. Siga las instrucciones que aparecen para crear el archivo.  
  
3.  Guarde los cambios del proyecto. En el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **generar solución**.  
  
4.  Después de proyecto se compila correctamente, en el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **implementar solución**.  
  
## <a name="configure-the-application"></a>Configurar la aplicación  
 Para configurar la aplicación, en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], cree los puertos de envío y recepción, y enlácelos con la orquestación y los puertos de envío y recepción lógicos creados como parte de la orquestación.  
  
1.  Cree un puerto de recepción por el que la aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reciba un pedido de compra JSON.  
  
    1.  En [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **BizTalk Application 1**, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
    2.  Proporcione un nombre para el puerto de recepción y, a continuación, en el panel izquierdo, haga clic en **ubicaciones de recepción**. En el **ubicaciones de recepción** , haga clic en **nuevo**.  
  
    3.  Especifique un nombre para la ubicación de recepción, seleccione el tipo de puerto como **archivo**y, a continuación, haga clic en **configurar**.  
  
    4.  Proporcione la ubicación de carpeta de donde la ubicación de recepción tomará el pedido de compra JSON entrante. Especifique `*.json` como la máscara de archivo y, a continuación, haga clic en **Aceptar**.  
  
    5.  Desde el **canalización de recepción** lista desplegable, seleccione **JSONToXml**. Creó esta canalización de recepción personalizada en la aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Haga clic en los puntos suspensivos **(...)**  botón junto a la canalización y, a continuación, en **fase 1 – componente descodificar**, proporcione los valores siguientes:  
  
        -   RootNode-`ROOT`  
  
        -   RootNodeNamespace:`http://BTSJSON`.  
  
         Estos valores representan el espacio de nombres de destino y el nombre del nodo raíz del esquema del pedido de compra XML que se generó a partir del pedido de compra JSON con el asistente para esquemas JSON.  
  
    6.  Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo abiertos.  
  
2.  Cree un puerto de envío para enviar mensajes de factura JSON.  
  
    1.  En [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **BizTalk Application 1**, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **enviar Puerto unidireccional**.  
  
    2.  Especifique un nombre para el puerto de envío, seleccione el tipo de puerto como **archivo**y, a continuación, haga clic en **configurar**.  
  
    3.  Proporcione la ubicación de carpeta donde el puerto de envío copia la factura JSON saliente. Especifique `%MessageID%.json` como el nombre de archivo y, a continuación, haga clic en **Aceptar**.  
  
    4.  Desde el **canalización de envío** lista desplegable, seleccione **XmlToJSON**y, a continuación, haga clic en **Aceptar**.  
  
    5.  Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo abiertos.  
  
3.  Finalmente, enlace los puertos lógicos que creó como parte de la orquestación a los puertos físicos que ha creado ahora para configurar la aplicación.  
  
    1.  Haga clic en **BizTalk Application 1**y, a continuación, haga clic en **configurar**.  
  
    2.  En el panel izquierdo, haga clic en **ProcessPO**. En el panel derecho, asocie un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hospedar, asigne los puertos lógicos a los puertos físicos y, a continuación, haga clic en **Aceptar**.  
  
    3.  Haga clic en **BizTalk Application 1**y, a continuación, haga clic en **iniciar**.  
  
## <a name="test-the-application"></a>Probar la aplicación  
  
1.  Navegue al ejemplo que ha descargado y desde el **TestMessage** carpeta, copie **JsonPurchaseOrder.json**y péguelo en la carpeta asociada con la ubicación de recepción. Espere hasta que desaparezca el archivo.  
  
2.  Navegue a la carpeta que ha asociado al puerto de envío que había creado. Tenga en cuenta que un   ***\<GUID\>*.json** archivo está disponible en la carpeta. Abra el archivo y verifique que es el mensaje de factura.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes JSON con BizTalk Server](../core/processing-json-messages-using-biztalk-server.md)