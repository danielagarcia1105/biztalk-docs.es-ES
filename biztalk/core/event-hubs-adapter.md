---
title: Usar el adaptador de centros de eventos | Documentos de Microsoft
description: Enviar y recibir mensajes mediante el adaptador de centros de eventos de Azure en BizTalk Server
ms.custom: ''
ms.date: 11/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: plarsen
manager: anneta
ms.openlocfilehash: cb9bbe26f07d87d7cccc084b6842b6d0974fdbb3
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848924"
---
# <a name="event-hub-adapter-in-biztalk"></a>Adaptador de concentrador de eventos de BizTalk

## <a name="overview"></a>Información general
**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, puede enviar y recibir mensajes entre BizTalk Server y los centros de eventos de Azure. 

Centros de eventos de Azure es una plataforma, de transmisión por secuencias de datos altamente escalables y puede recibir y procesar millones de eventos por segundo. [¿Qué es centros de eventos? ](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) proporcionan más detalles.

## <a name="prerequisites"></a>Requisitos previos

* Crear un [espacio de nombres de los centros de eventos de Azure y centro de eventos](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)
* Crear un [cuenta de almacenamiento de blobs de Azure con un contenedor](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)
* Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en el servidor BizTalk Server

Ahora se crea el centro de eventos y de que las cadenas de conexión que necesita para enviar y recibir eventos.

## <a name="send-messages-to-event-hubs"></a>Enviar mensajes a los centros de eventos

1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y seleccione **puerto de envío unidireccional estático**.

    [Crear un puerto de envío](../core/how-to-create-a-send-port2.md) proporciona alguna orientación.

2. Escriba un **nombre**. En **transporte**, establezca el **tipo** a **EventHub**y seleccione **configurar**. 

3. Configurar la **cuenta de Azure** propiedades: 

    |Use|Para|  
    |---|---|  
    | **inicio de sesión** | Inicie sesión en su cuenta de Azure |
    | **Suscripción** | Seleccione la suscripción que tenga el espacio de nombres EventHubs |
    | **Grupo de recursos** | Seleccione el grupo de recursos que tiene el espacio de nombres EventHubs |

4. Configurar la **extremo** propiedades: 

    |Use|Para|  
    |---|---|  
    | **Espacio de nombres** | Seleccione el espacio de nombres de los centros de eventos, que es algo parecido a sb: / /*youreventhubnamespace*.servicebus.windows.net/ |
    | **Nombre** | Seleccione el nombre de su centro de eventos (que se creó en el espacio de nombres de los centros de eventos) |
    | **Clave de partición predeterminada** | Opcional. [Guía de programación de centros de eventos](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide) contiene más detalles sobre esta clave. |
    | **Autenticación** | **Firma de acceso de Namespace** es el valor predeterminado y utiliza automáticamente el RootManageSharedAccessKey que se crea cuando se crea un espacio de nombres de los centros de eventos.<br/><br/>**Firma de acceso de la entidad** es la directiva SAS puede crear en el concentrador de eventos-nivel (no lo centros de eventos espacio de nombres de nivel). <br/><br/>[Información general de características de los centros de eventos](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) más detallada. |

    Cuando termine, las propiedades de aspecto similares al siguiente: 

    ![Propiedades de punto de conexión](../core/media/event-hub-endpoint-properties.png)


5. Opcional. Configurar la **mensaje** propiedades. El **Namespace para propiedades de mensaje definidas por el usuario** valor representa un esquema de mensaje de BizTalk asignado a propiedades de mensaje de los centros de eventos.

6. Seleccione **Aceptar** para guardar los cambios. 


### <a name="test-your-send-port"></a>Probar el puerto de envío

Puede usar un simple archivo de puerto de recepción y ubicación para enviar mensajes a su centro de eventos de Azure. 

1. Crear un puerto de recepción mediante el adaptador de archivo. Dentro de la ubicación de recepción, establezca la **carpeta recepción** a **C:\Temp\In\** y establece la máscara de archivo en  **\*.xml**.
2. En el centro de eventos de propiedades de puerto de envío, establezca la **filtros** a `BTS.ReceivePortName == FileReceivePort`.
3. Pegue lo siguiente en un editor de texto y guarde el archivo como **EventHubMessage.xml**. Este es el mensaje de ejemplo. 

    ```xml
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

4. Iniciar el archivo de ubicación de recepción y el puerto de envío de concentrador de eventos.
5. Copia **EventHubMessage.xml** mensaje de ejemplo en la carpeta de recepción (C:\Temp\In\). El puerto de envío envía el archivo XML para el concentrador de eventos.

## <a name="receive-messages-from-event-hubs"></a>Recibir mensajes desde los centros de eventos

1. En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**, seleccione **New**y seleccione **unidireccional puerto de recepción**. 

    [Crear un puerto de recepción](../core/how-to-create-a-receive-port.md) proporciona alguna orientación.

2. Escriba un nombre y seleccione **ubicaciones de recepción**. 

3. Seleccione **New**, y **nombre** la ubicación de recepción. En **transporte**, seleccione **EventHub** desde el **tipo** lista desplegable y, a continuación, seleccione **configurar**. 

4. Configurar la **cuenta de Azure** propiedades: 

    |Use|Para|  
    |---|---|  
    | **inicio de sesión** | Inicie sesión en su cuenta de Azure |
    | **Suscripción** | Seleccione la suscripción que tenga el espacio de nombres EventHubs |
    | **Grupo de recursos** | Seleccione el grupo de recursos que tiene el espacio de nombres EventHubs |

4. Configurar la **extremo** propiedades: 

    |Use|Para|  
    |---|---|  
    | **Espacio de nombres** | Seleccione el espacio de nombres de los centros de eventos, que es algo parecido a sb: / /*youreventhubnamespace*.servicebus.windows.net/ |
    | **Nombre** | Seleccione el nombre de su centro de eventos (que se creó en el espacio de nombres de los centros de eventos) |
    | **Grupo de consumidores** | Seleccione el grupo de consumidores en el centro de eventos. Un grupo predeterminado se crea automáticamente. <br/><br/>[Información general de características de los centros de eventos](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) proporcionan más detalles. |
    | **Autenticación** | **Firma de acceso de Namespace** es el valor predeterminado y utiliza automáticamente el RootManageSharedAccessKey que se crea cuando se crea un espacio de nombres de los centros de eventos.<br/><br/>**Firma de acceso de la entidad** es la directiva SAS puede crear en el concentrador de eventos-nivel (no lo centros de eventos espacio de nombres de nivel). <br/><br/>[Información general de características de los centros de eventos](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) más detallada. |

    Cuando termine, las propiedades de aspecto similares al siguiente: 

    ![Propiedades de punto de conexión](../core/media/event-hub-endpoint-receive-properties.png)

5. Configurar la **punto de comprobación** propiedades. Este adaptador usa una cuenta de almacenamiento de blobs de Azure para confiable con un punto de control de eventos de lectura y continuar desde un reinicio. 

    **Autenticación de almacenamiento**   
    Seleccione un método de autenticación. Por lo general, se recomienda para usar una firma de acceso compartido. Los siguientes vínculos son buenos recursos para ayudarle a decidir cuál es el adecuado para su escenario:<br/><br/>[Acerca de las cuentas de almacenamiento de Azure](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)<br/>[Uso de firmas de acceso compartido (SAS)](https://docs.microsoft.com/azure/storage/common/storage-dotnet-shared-access-signature-part-1)

    Cuando termine, las propiedades de aspecto similares al siguiente: 

    ![Propiedades de punto de comprobación](../core/media/event-hub-receive-checkpoint.png)

6. Configurar la **mensaje** propiedades: 

    |Use|Para|  
    |---|---|  
    | **Propiedades de mensaje definidas por el Namespace para el usuario** | http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User es el esquema predeterminado, pero puede escribir otro esquema. Este valor representa un esquema de mensaje de BizTalk asignado a propiedades de mensaje de los centros de eventos. |
    | **Promocionar propiedades definidas por el usuario** | Opcional. Si lo prefiere puede promocionar estas propiedades. <br/><br/>**NOTA**<br/>Las propiedades que deben promocionarse deben tener un esquema de porperty implementarlo *antes de* recibir eventos.|

7. Seleccione **Aceptar** para guardar los cambios. 

### <a name="test-your-receive-settings"></a>Prueba la configuración de recepción

Puede utilizar un puerto de envío de archivo simple para recibir mensajes desde el centro de eventos de Azure. 

1. Crear un puerto de envío mediante el adaptador de archivo. En las propiedades de puerto de envío, establecer el **carpeta de destino** a **C:\Temp\Out\** y establezca el y **nombre de archivo** a **%MessageID%.xml** .
2. En el archivo de propiedades de puerto de envío, establezca la **filtros** a `BTS.ReceivePortName == EHReceivePort`.
3. El concentrador de eventos de inicio ubicación de recepción y el puerto de envío de archivos.
4. Buscar mensajes en la carpeta de destino (c:\temp\out).

## <a name="do-more"></a>Llevar a cabo más
Los concentradores de eventos se considera la "puerta principal" a una gran cantidad de otros servicios de Azure, incluido Data Lake de Azure, Hdinsight y mucho más. Se ha diseñado para procesar un lote de mensajes y procesarlos rápida. Más información acerca de los centros de eventos y sus características: 

[Información general de características de los centros de eventos](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)  
[¿Qué es centros de eventos?](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)