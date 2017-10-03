---
title: "Paso 8 (de forma local): Configurar la aplicación de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-12-08
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5109fb54-8453-444f-bc9c-070a65053397
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47332edbf974b7e45d3ab65644f28d9d2bd6a623
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-on-premises-configure-the-biztalk-server-application"></a>Paso 8 (de forma local): Configurar la aplicación de BizTalk Server
En el paso anterior, creó una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este paso, compilará, implementará y configurará la aplicación.  
  
## <a name="build-and-deploy-the-application"></a>Compilar e implementar la aplicación  
  
1.  En Visual Studio, haga clic en el nombre de la solución en el Explorador de soluciones y haga clic en **generar**.  
  
2.  El proceso de implementación necesita que el ensamblado esté firmado de forma segura.  Debe firmar los ensamblados asociando el proyecto con un archivo de clave de ensamblado de nombre seguro.  
  
    1.  En el Explorador de soluciones, haga clic en el **OrderProcessingDemo** del proyecto y, a continuación, haga clic en **propiedades**.  
  
    2.  Haga clic en el **firma** pestaña y seleccione la **firmar el ensamblado** casilla de verificación.  
  
    3.  En la lista desplegable de la **elegir un archivo de clave de nombre seguro** cuadro, seleccione  **\<nuevo... >**.  
  
    4.  En el **crear clave de nombre seguro** diálogo cuadro, escriba un nombre para el archivo de clave, por ejemplo `OrderProcessingDemo.snk`. Desactive la casilla para proteger el archivo de clave con una contraseña y, a continuación, haga clic en **Aceptar**.  
  
3.  Haga clic en el **implementación** ficha, en el cuadro a la derecha del **nombre de la aplicación**, tipo `OrderProcessingDemo`.  
  
4.  En la lista desplegable en el cuadro a la derecha del **volver a implementar**, seleccione **True**.  
  
5.  En el Explorador de soluciones, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **implementar**.  En la ventana de salida se debe ver:  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
## <a name="configure-the-application"></a>Configurar la aplicación  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione  **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  
  
2.  En el árbol de consola en el panel izquierdo, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **actualizar**.  
  
3.  Expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **OrderProcessingDemo**y, a continuación, haga clic en **orquestaciones**. Verá que la **OrderProcessingDemo.OrderProcessing** se implementa la orquestación.  
  
4.  En la orquestación, creó un puerto lógico (**ReceiveSO**) para recibir mensajes desde la cola de Bus de servicio. En este paso, se crea un puerto de recepción físico para asignar al puerto lógico.  
  
    1.  Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de recepción**, seleccione **nuevo**y, a continuación, haga clic en **Unidireccional puerto de recepción**.  
  
    2.  En la pestaña **General** , haga lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Nombre**|Tipo de **ReceiveSO**.|  
        |**Habilitar enrutamiento para mensajes con errores**|(clear)|  
  
    3.  Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **nuevo**.  
  
    4.  Desde el cuadro de diálogo Ubicación de recepción1 - Propiedades de ubicación de recepción, haga lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Nombre**|Tipo de **ReceiveOrders_SO**.|  
        |**Tipo**|Seleccione **SB-Messaging**.|  
        |**Controlador de recepción**|Seleccionar **BizTalkServerApplication**.|  
        |**La canalización de recepción**|Seleccione **XMLReceive**.|  
  
    5.  Haga clic en **configurar**.  
  
    6.  Cuadro de diálogo Propiedades de transporte SB-Messaging en el **General** ficha, para **cola o la dirección URL de suscripción**, escriba **sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi** . En este caso, *mynamespace* es el espacio de nombres de Bus de servicio y *queueordersedi* es la cola de Bus de servicio que creó en [(para Azure) del paso 3: crear una cola de Bus de servicio](../core/step-3-for-azure-create-a-service-bus-queue.md).  
  
    7.  Cuadro de diálogo Propiedades de transporte SB-Messaging en el **autenticación** ficha, especifique los valores siguientes:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Uri de STS del servicio de Control de acceso**|Escriba `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`|  
        |**Nombre del emisor**|Especifique el nombre del emisor. Normalmente se establece en `owner`.|  
        |**Clave del emisor**|Especifique la clave del emisor.|  
  
        > [!NOTE]
        >  Puede obtener los valores para el emisor de la dirección URL de cola, dirección URL de ACS, nombre y la clave de la [Portal de administración de Windows Azure CTP](http://go.microsoft.com/fwlink/p/?LinkId=202886).  
  
    8.  Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.  
  
5.  En la orquestación, creó un puerto lógico (**SendToSQL**) para enviar mensajes a la **SalesOrder** tabla de base de datos. En este paso, se crea un puerto de envío físico para asignar al puerto lógico.  
  
    1.  Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de envío**, seleccione **nuevo**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  
  
    2.  En la ficha General, haga lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Nombre**|Tipo de **SendToSQL**.|  
        |**Tipo**|Seleccione **WCF-SQL**.|  
        |**Controlador de envío**|Seleccione **BizTAlkServerApplication**.|  
        |**Canalización de envío**|Seleccione **PassThruTransmit**.|  
  
    3.  Haga clic en **configurar**.  
  
    4.  Propiedades de transporte WCF-SQL en el **General** ficha, realice lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Dirección (URI)**|Tipo de **mssql://computername/database_instance_name/databasename**. Por ejemplo, para conectarse a un **DemoDB** en el equipo local que se ejecuta en la instancia de base de datos predeterminada de base de datos, escriba`mssql://.//DemoDB`<br /><br /> Para obtener más información, consulte [crear el URI de conexión de SQL Server](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).|  
        |**Acción**|Tipo de **TableOp/Insert/dbo/SalesOrder**.|  
  
    5.  Propiedades de transporte WCF-SQL en el **credenciales** ficha, seleccione **no use Single Sign-On**y especifique las credenciales (distingue mayúsculas de minúsculas) para conectarse a SQL Server de base de datos que especificó en el cadena de conexión. Si quiere conectase usando la autenticación de Windows, deje las credenciales en blanco.  
  
    6.  Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.  
  
6.  En la orquestación, creó un puerto lógico (**SendToFile**) para enviar mensajes a una ubicación compartida. En este paso, se crea un puerto de envío físico para asignar al puerto lógico.  
  
    1.  Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de envío**, seleccione **nuevo**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  
  
    2.  En la ficha General, haga lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Nombre**|Tipo de **SendToFile**.|  
        |**Tipo**|Seleccione **archivo**.|  
        |**Controlador de envío**|Seleccione **BizTAlkServerApplication**.|  
        |**Canalización de envío**|Seleccione **XMLTransmit**.|  
  
    3.  Haga clic en **configurar**.  
  
    4.  Desde Propiedades de transporte de archivo, haga lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Carpeta de recepción**|Especifique la ubicación donde desea enviar el mensaje.|  
        |**Nombre de archivo**|Conservar **%MessageID%.xml**.|  
  
    5.  Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.  
  
7.  Ahora debe enlazar los puertos físico y lógico para configurar la aplicación.  
  
    1.  Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **configurar**.  
  
    2.  Desde Configurar aplicación, en el panel izquierdo, haga clic en **OrderProcessing**.  
  
    3.  Use los valores en la siguiente tabla para configurar la aplicación.  
  
        |Use|Para|  
        |--------------|----------------|  
        |Para **Host**|Seleccione **BizTalkServerApplication**|  
        |Para el puerto lógico **ReceiveSO**|Seleccionar puerto físico **ReceiveSO**|  
        |Para el puerto lógico **SendToSQL**|Seleccionar puerto físico **SendToSQL**|  
        |Para el puerto lógico **SendToFile**|Seleccionar puerto físico **SendToFile**|  
  
    4.  Haga clic en **Aceptar** para guardar la configuración.  
  
## <a name="start-the-application"></a>Iniciar la aplicación  
  
1.  Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **iniciar**.  
  
2.  En el cuadro de diálogo, haga clic en **iniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)