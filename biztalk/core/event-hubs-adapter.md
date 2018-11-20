---
title: Usar el adaptador de Event Hubs | Microsoft Docs
description: Enviar y recibir mensajes mediante el adaptador de Azure Event Hubs en BizTalk Server
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
ms.openlocfilehash: a1e30b1ab1aacc1c5134d1dd5b44744bd670b308
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630337"
---
# <a name="event-hub-adapter-in-biztalk"></a>Adaptador del centro de eventos de BizTalk

## <a name="overview"></a>Información general
**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, puede enviar y recibir mensajes entre BizTalk Server y Azure Event Hubs. 

Azure Event Hubs es una plataforma, de streaming de datos altamente escalables y puede recibir y procesar millones de eventos por segundo. [¿Qué es Event Hubs? ](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) proporciona más detalles.

## <a name="prerequisites"></a>Requisitos previos

* Crear un [centro de eventos y el espacio de nombres de Azure event hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)
* Crear un [cuenta de almacenamiento de blobs de Azure con un contenedor](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)
* Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en el servidor BizTalk Server

Ya se ha creado el centro de eventos y tiene las cadenas de conexión que necesita para enviar y recibir eventos.

## <a name="send-messages-to-event-hubs"></a>Enviar mensajes a Event Hubs

1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y seleccione **puerto de envío unidireccional estático**.

    [Crear un puerto de envío](../core/how-to-create-a-send-port2.md) proporciona alguna orientación.

2. Escriba un **nombre**. En **transporte**, establezca el **tipo** a **EventHub**y seleccione **configurar**. 

3. Configurar la **cuenta de Azure** propiedades: 

    |Use|Para|  
    |---|---|  
    | **Inicio de sesión** | Inicie sesión en su cuenta de Azure |
    | **Suscripción** | Seleccione la suscripción que tiene el espacio de nombres de Event hubs |
    | **Grupo de recursos** | Seleccione el grupo de recursos que tiene el espacio de nombres de Event hubs |

4. Configurar la **extremo** propiedades: 

    |Use|Para|  
    |---|---|  
    | **Espacio de nombres** | Seleccione el espacio de nombres de Event Hubs, que es algo parecido a sb: / /*youreventhubnamespace*.servicebus.windows.net/ |
    | **Nombre** | Seleccione el nombre del centro de eventos (que se creó en el espacio de nombres de Event Hubs) |
    | **Clave de partición predeterminado** | Opcional. [Guía de programación de Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide) proporciona más detalles sobre esta clave. |
    | **Autenticación** | **Firma de acceso de Namespace** es el valor predeterminado y usa automáticamente el RootManageSharedAccessKey que se crea cuando se crea un espacio de nombres de Event Hubs.<br/><br/>**Firma de acceso de la entidad** es la directiva SAS puede crear en el Event Hub-nivel (no los Event Hubs espacio de nombres-). <br/><br/>[Información general de las características de Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) se explica más información. |

    Cuando termine, las propiedades de aspecto similares al siguiente: 

    ![Propiedades de punto de conexión](../core/media/event-hub-endpoint-properties.png)


5. Opcional. Configurar la **mensaje** propiedades. El **Namespace para propiedades de mensaje definidas por el usuario** valor representa un esquema de mensaje de BizTalk asignado a propiedades de mensajes de Event Hubs.

6. Seleccione **Aceptar** para guardar los cambios. 


### <a name="test-your-send-port"></a>Probar el puerto de envío

Puede usar un simple archivo de puerto de recepción y ubicación para enviar mensajes al centro de eventos de Azure. 

1. Crear un puerto de recepción mediante el adaptador de archivo. Dentro de la ubicación de recepción, establezca la **carpeta recepción** a **C:\Temp\In\\**y establece la máscara de archivo en  **\*.xml**.
2. En el centro de eventos propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == FileReceivePort`.
3. Pegue lo siguiente en un editor de texto y guarde el archivo como **EventHubMessage.xml**. Este es el mensaje de ejemplo. 

    ```xml
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

4. Iniciar el archivo de ubicación de recepción y el puerto de envío del centro de eventos.
5. Copia **EventHubMessage.xml** mensaje de ejemplo en la carpeta de recepción (C:\Temp\In\). El puerto de envío envía el archivo XML al centro de eventos.

## <a name="receive-messages-from-event-hubs"></a>Recibir mensajes desde Event Hubs

1. En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**, seleccione **New**y seleccione **unidireccional puerto de recepción**. 

    [Crear un puerto de recepción](../core/how-to-create-a-receive-port.md) proporciona alguna orientación.

2. Escriba un nombre y seleccione **ubicaciones de recepción**. 

3. Seleccione **New**, y **nombre** la ubicación de recepción. En **transporte**, seleccione **EventHub** desde el **tipo** lista desplegable y, a continuación, seleccione **configurar**. 

4. Configurar la **cuenta de Azure** propiedades: 

    |Use|Para|  
    |---|---|  
    | **Inicio de sesión** | Inicie sesión en su cuenta de Azure |
    | **Suscripción** | Seleccione la suscripción que tiene el espacio de nombres de Event hubs |
    | **Grupo de recursos** | Seleccione el grupo de recursos que tiene el espacio de nombres de Event hubs |

4. Configurar la **extremo** propiedades: 

    |Use|Para|  
    |---|---|  
    | **Espacio de nombres** | Seleccione el espacio de nombres de Event Hubs, que es algo parecido a sb: / /*youreventhubnamespace*.servicebus.windows.net/ |
    | **Nombre** | Seleccione el nombre del centro de eventos (que se creó en el espacio de nombres de Event Hubs) |
    | **Grupo de consumidores** | Seleccione el grupo de consumidores dentro de su centro de eventos. Se crea automáticamente un grupo de forma predeterminada. <br/><br/>[Información general de las características de Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) proporciona más detalles. |
    | **Autenticación** | **Firma de acceso de Namespace** es el valor predeterminado y usa automáticamente el RootManageSharedAccessKey que se crea cuando se crea un espacio de nombres de Event Hubs.<br/><br/>**Firma de acceso de la entidad** es la directiva SAS puede crear en el Event Hub-nivel (no los Event Hubs espacio de nombres-). <br/><br/>[Información general de las características de Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) se explica más información. |

    Cuando termine, las propiedades de aspecto similares al siguiente: 

    ![Propiedades de punto de conexión](../core/media/event-hub-endpoint-receive-properties.png)

5. Configurar la **Checkpoint** propiedades. Este adaptador usa una cuenta de almacenamiento de blobs de Azure para leer con un punto de control de eventos confiable y reanudar a partir de un reinicio. 

    **Autenticación de almacenamiento**   
    Seleccione un método de autenticación. Normalmente, se recomienda para usar una firma de acceso compartido. Los siguientes vínculos son buenos recursos para ayudarle a decidir cuál es la adecuada para su escenario:<br/><br/>[Acerca de las cuentas de almacenamiento de Azure](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)<br/>[Uso de firmas de acceso compartido (SAS)](https://docs.microsoft.com/azure/storage/common/storage-dotnet-shared-access-signature-part-1)

    Cuando termine, las propiedades de aspecto similares al siguiente: 

    ![Propiedades de punto de control](../core/media/event-hub-receive-checkpoint.png)

6. Configurar la **mensaje** propiedades: 

    |Use|Para|  
    |---|---|  
    | **Namespace para el usuario define las propiedades de mensaje** | `http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User` es el esquema predeterminado, pero puede escribir otro esquema. Este valor representa un esquema de mensaje de BizTalk asignado a propiedades de mensajes de Event Hubs. |
    | **Promocionar propiedades definidas por el usuario** | Opcional. Si lo prefiere puede promocionar estas propiedades. <br/><br/>**NOTA**<br/>Las propiedades que deben promocionarse deben tener un esquema porperty implementado *antes* recibir eventos.|

7. Seleccione **Aceptar** para guardar los cambios. 

### <a name="test-your-receive-settings"></a>Prueba la configuración de recepción

Puede usar un puerto de envío de archivos simple para recibir mensajes desde el centro de eventos de Azure. 

1. Crear un puerto de envío mediante el adaptador de archivo. Dentro de las propiedades de puerto de envío, establezca el **carpeta de destino** a **C:\Temp\Out\\**y establezca el y **nombre de archivo** a **%MessageID%.xml** .
2. En el archivo de propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == EHReceivePort`.
3. El centro de eventos de inicio ubicación de recepción y el puerto de envío de archivo.
4. Buscar mensajes en la carpeta de destino (c:\temp\out).

## <a name="do-more"></a>Hacer más cosas
Event Hubs se considera la "puerta principal" para muchos otros servicios de Azure, incluido Azure Data Lake, HD Insight y mucho más. Se ha diseñado para procesar un lote de mensajes y procesarlos rápida. Más información acerca de Event Hubs y sus características: 

[Información general de las características de Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)  
[¿Qué es Event Hubs?](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
