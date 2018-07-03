---
title: 'Paso 8 (local): Configurar la aplicación de BizTalk Server | Microsoft Docs'
ms.custom: ''
ms.date: 2015-12-08
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5109fb54-8453-444f-bc9c-070a65053397
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b3eafcc5e49bb6fa360f1db4b6e92d9393068a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996845"
---
# <a name="step-8-on-premises-configure-the-biztalk-server-application"></a>Paso 8 (local): Configurar la aplicación de BizTalk Server
En el paso anterior, creó una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este paso, compilará, implementará y configurará la aplicación.  

## <a name="build-and-deploy-the-application"></a>Compilar e implementar la aplicación  

1.  En Visual Studio, haga clic en el nombre de la solución en el Explorador de soluciones y haga clic en **compilar**.  

2.  El proceso de implementación necesita que el ensamblado esté firmado de forma segura.  Debe firmar los ensamblados asociando el proyecto con un archivo de clave de ensamblado de nombre seguro.  

    1.  En el Explorador de soluciones, haga clic en el **OrderProcessingDemo** del proyecto y, a continuación, haga clic en **propiedades**.  

    2.  Haga clic en el **firma** pestaña y seleccione el **firmar el ensamblado** casilla de verificación.  

    3.  En la lista desplegable en el **elegir un archivo de clave de nombre seguro** cuadro, seleccione  **\<nuevo... \>**.  

    4.  En el **crear clave de nombre seguro** diálogo cuadro, escriba un nombre para el archivo de clave, por ejemplo `OrderProcessingDemo.snk`. Desactive la casilla de verificación para proteger el archivo de clave con una contraseña y, a continuación, haga clic en **Aceptar**.  

3.  Haga clic en el **implementación** ficha, en el cuadro a la derecha del **nombre de la aplicación**, tipo `OrderProcessingDemo`.  

4.  En la lista desplegable en el cuadro a la derecha del **volver a implementar**, seleccione **True**.  

5.  En el Explorador de soluciones, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **implementar**.  En la ventana de salida se debe ver:  

    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  

    ```  

## <a name="configure-the-application"></a>Configurar la aplicación  

1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  

2. En el árbol de consola en el panel izquierdo, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **actualizar**.  

3. Expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **OrderProcessingDemo**y, a continuación, haga clic en **orquestaciones**. Verá que el **OrderProcessingDemo.OrderProcessing** se implementa la orquestación.  

4. En la orquestación, creó un puerto lógico (**ReceiveSO**) para recibir mensajes de la cola de Service Bus. En este paso, se crea un puerto de recepción físico para asignar al puerto lógico.  

   1. Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **Unidireccional puerto de recepción**.  

   2. En la pestaña **General** , haga lo siguiente:  


      |                Use                |     Para      |
      |----------------------------------------|---------------------|
      |                **Nombre**                | Tipo **ReceiveSO**. |
      | **Habilitar enrutamiento para mensajes con errores** |       (clear)       |


   3. Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **New**.  

   4. Desde el cuadro de diálogo Ubicación de recepción1 - Propiedades de ubicación de recepción, haga lo siguiente:  


      |       Use       |              Para              |
      |----------------------|--------------------------------------|
      |       **Nombre**       |      Tipo **ReceiveOrders_SO**.      |
      |       **Tipo**       |       Seleccione **SB-Messaging**.       |
      | **Controlador de recepción**  | Seleccionar **BizTalkServerApplication**. |
      | **Canalización de recepción** |        Seleccione **XMLReceive**.        |


   5. Haga clic en **configurar**.  

   6. Desde el cuadro de diálogo Propiedades de transporte SB-Messaging, en el **General** ficha, para **cola o la dirección URL de suscripción**, escriba **sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi** . En este caso, *mynamespace* es el espacio de nombres de Service Bus y *queueordersedi* es la cola de Service Bus que creó en [(Azure) del paso 3: crear una cola de Service Bus](../core/step-3-for-azure-create-a-service-bus-queue.md).  

   7. Desde el cuadro de diálogo Propiedades de transporte SB-Messaging, en el **autenticación** ficha, especifique los valores siguientes:  

      |Use|Para|  
      |--------------|----------------|  
      |**Uri de STS de Access Control Service**|Escriba `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`|  
      |**Nombre del emisor**|Especifique el nombre del emisor. Normalmente esto se establece en `owner`.|  
      |**Clave del emisor**|Especifique la clave del emisor.|  

      > [!NOTE]
      >  Puede obtener los valores para el emisor de la dirección URL de cola, dirección URL de ACS, nombre y la clave de la [Portal de administración de Windows Azure CTP](http://go.microsoft.com/fwlink/p/?LinkId=202886).  

   8. Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.  

5. En la orquestación, creó un puerto lógico (**SendToSQL**) para enviar mensajes a la **SalesOrder** tabla de base de datos. En este paso, se crea un puerto de envío físico para asignar al puerto lógico.  

   1. Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  

   2. En la ficha General, haga lo siguiente:  


      |     Use      |              Para              |
      |-------------------|--------------------------------------|
      |     **Nombre**      |         Tipo **SendToSQL**.          |
      |     **Tipo**      |         Seleccione **WCF-SQL**.          |
      | **Controlador de envío**  | Seleccione **BizTAlkServerApplication**. |
      | **Canalización de envío** |     Seleccione **PassThruTransmit**.     |


   3. Haga clic en **configurar**.  

   4. Propiedades de transporte WCF-SQL en el **General** ficha, realice lo siguiente:  


      |     Use      |                                                                                                                                                                                    Para                                                                                                                                                                                    |
      |-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      | **Dirección (URI)** | Tipo **mssql://computername/database_instance_name/databasename**. Por ejemplo, para conectarse a un **DemoDB** base de datos en el equipo local que se ejecutan en la instancia de base de datos predeterminada, escriba `mssql://.//DemoDB`<br /><br /> Para obtener más información, consulte [crear el URI de conexión de SQL Server](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md). |
      |    **Acción**     |                                                                                                                                                                     Tipo **TableOp/Insert/dbo/SalesOrder**.                                                                                                                                                                      |


   5. Propiedades de transporte WCF-SQL en el **credenciales** ficha, seleccione **no use Single Sign-On**y especifique las credenciales (distingue mayúsculas de minúsculas) para conectarse a SQL Server de base de datos que especificó en el cadena de conexión. Si quiere conectase usando la autenticación de Windows, deje las credenciales en blanco.  

   6. Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.  

6. En la orquestación, creó un puerto lógico (**SendToFile**) para enviar mensajes a una ubicación compartida. En este paso, se crea un puerto de envío físico para asignar al puerto lógico.  

   1. Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **OrderProcessingDemo** nodo, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  

   2. En la ficha General, haga lo siguiente:  


      |     Use      |              Para              |
      |-------------------|--------------------------------------|
      |     **Nombre**      |         Tipo **SendToFile**.         |
      |     **Tipo**      |           Seleccione **archivo**.           |
      | **Controlador de envío**  | Seleccione **BizTAlkServerApplication**. |
      | **Canalización de envío** |       Seleccione **XMLTransmit**.       |


   3. Haga clic en **configurar**.  

   4. Desde Propiedades de transporte de archivo, haga lo siguiente:  


      |      Use      |                        Para                        |
      |--------------------|----------------------------------------------------------|
      | **Carpeta de recepción** | Especifique la ubicación donde desea enviar el mensaje. |
      |   **Nombre de archivo**    |               Conservar **%MessageID%.xml**.                |


   5. Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.  

7. Ahora debe enlazar los puertos físico y lógico para configurar la aplicación.  

   1. Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **configurar**.  

   2. Desde Configurar aplicación, en el panel izquierdo, haga clic en **OrderProcessing**.  

   3. Use los valores en la siguiente tabla para configurar la aplicación.  


      |            Use             |             Para              |
      |---------------------------------|-------------------------------------|
      |          Para **Host**           | Seleccione **BizTalkServerApplication** |
      | Para el puerto lógico **ReceiveSO**  | Seleccionar puerto físico **ReceiveSO**  |
      | Para el puerto lógico **SendToSQL**  | Seleccionar puerto físico **SendToSQL**  |
      | Para el puerto lógico **SendToFile** | Seleccionar puerto físico **SendToFile** |


   4. Haga clic en **Aceptar** para guardar la configuración.  

## <a name="start-the-application"></a>Iniciar la aplicación  

1. Desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **OrderProcessingDemo**y, a continuación, haga clic en **iniciar**.  

2. En el cuadro de diálogo, haga clic en **iniciar**.  

## <a name="see-also"></a>Vea también  
 [Tutorial 4: Crear una aplicación híbrida con BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)