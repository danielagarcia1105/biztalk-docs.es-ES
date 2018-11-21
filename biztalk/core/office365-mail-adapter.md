---
title: Usar el adaptador de correo electrónico de Office 365 Outlook | Microsoft Docs
description: Enviar y recibir mensajes de correo electrónico mediante el adaptador de correo electrónico de Outlook de Office 365 en BizTalk Server. Para ello, cree un puerto de recepción y puerto de envío mediante el adaptador de correo electrónico y usar mensajes de ejemplo para probar los puertos.
ms.custom: ''
ms.date: 06/25/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: ribarua
manager: dougeby
ms.openlocfilehash: 58183ce30236ccca39b9c8345959c4785de46ae9
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752639"
---
# <a name="send-and-receive-email-with-office-365-outlook-email-adapter---biztalk-server"></a>Enviar y recibir correo electrónico con el adaptador de correo electrónico de Office 365 Outlook - servidor BizTalk Server

El adaptador de correo electrónico de Outlook de Office 365 le permite enviar y recibir mensajes de correo desde su correo electrónico de Outlook de Office 365 desde BizTalk.

## <a name="send-mail-using-a-send-port"></a>Enviar correo mediante un puerto de envío

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y seleccione **puerto de envío unidireccional estático**.

    [Crear un puerto de envío](../core/how-to-create-a-send-port2.md) proporciona alguna orientación.

2. Escriba un **nombre**. En **transporte**, establezca el **tipo** a **correo electrónico de Outlook de Office 365**y seleccione **configurar**.

3. Seleccione **iniciar sesión...** e inicie sesión en su cuenta de Office 365. La cuenta está rellena automáticamente con su dirección de correo electrónico.

4. Permitir la aprobación de BizTalk Server para obtener permiso para tener acceso:

    ![Permisos de correo electrónico de Office 365](../core/media/office365-mail-permissions.png)

5. Configure sus propiedades predeterminadas de correo electrónico de Office 365 Outlook:

    |Use|Para|  
    |---|---|  
    | **Para** | Especifique su valor predeterminado para las direcciones de correo electrónico separadas por ';' (máximo de 256 caracteres)|
    | **CC** | Especifique las direcciones de correo electrónico predeterminada CC separadas por ';' (máximo de 256 caracteres)|
    | **Asunto** | Mencione al asunto de correo electrónico predeterminado. (máximo de 256 caracteres) |
    | **Importancia** | Seleccione el valor de importancia. Lista desplegable contiene valores **baja**, **Normal** y **alta** con **Normal** el valor predeterminado. |

    Cuando termine, las propiedades de aspecto similares al siguiente:

    ![Propiedades de punto de conexión](../core/media/office365-mail-send-properties.png)

6. Seleccione **Aceptar** para guardar los cambios.

### <a name="important-details"></a>Detalles importantes

1. Sólo puede enviar mensajes de texto sin formato mediante el adaptador de envío.
2. Las propiedades predeterminadas también se actualiza con las propiedades promocionadas:

|Property|Propiedad promocionada|
|---|---|
| **Para** | OfficeMail.To |
| **CC** | OfficeMail.CC |
| **Asunto** | OfficeMail.Subject |
| **Importancia** | OfficeMail.Importance |

### <a name="test-your-send-port"></a>Probar el puerto de envío

Puede usar un simple archivo de puerto de recepción y ubicación para enviar mensajes a su correo electrónico de Outlook de Office 365.

1. Crear un puerto de recepción mediante el adaptador de archivo. Dentro de la ubicación de recepción, establezca la **carpeta recepción** a **C:\\Temp\\en\\** y establece la máscara de archivo en **\*.xml**.
2. En el adaptador de correo electrónico de Outlook de Office 365 propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == <Receive Port Name>`.
3. Pegue lo siguiente en un editor de texto y guarde el archivo como **Office365Mail.xml**. Este es el mensaje de ejemplo.

    ```xml
    <ns0:Root xmlns:ns0="http://BizTalk_Server_Project1.Schema1"> 
        <Record> 
            <Name>BizTalk User</Name> 
            <ID>001</ID> 
        </Record> 
    </ns0:Root> 
    ```

4. Iniciar el archivo de ubicación de recepción y el puerto de envío del adaptador de correo electrónico de Outlook de Office 365.
5. Copia **Office365Mail.xml** mensaje de ejemplo en la carpeta de recepción (C:\\Temp\\en\\). El puerto de envío envía el archivo XML como cuerpo del correo electrónico a su correo electrónico de Office 365 Outlook.

## <a name="receive-email-using-a-receive-port"></a>Recibir correo electrónico mediante un puerto de recepción

1. En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**, seleccione **New**y seleccione **unidireccional puerto de recepción**.

    [Crear un puerto de recepción](../core/how-to-create-a-receive-port.md) proporciona alguna orientación.

2. Escriba un nombre y seleccione **ubicaciones de recepción**.

3. Seleccione **New**, y **nombre** la ubicación de recepción. En **transporte**, seleccione **correo electrónico de Outlook de Office 365** desde el **tipo** lista desplegable y, a continuación, seleccione **configurar**.

4. Seleccione **[iniciar sesión...** e inicie sesión en su cuenta de Office 365. La cuenta está rellena automáticamente con su dirección de correo electrónico.

5. Permitir la aprobación de BizTalk Server para obtener permiso para tener acceso:

    ![Permisos de correo electrónico de Office 365](../core/media/office365-mail-permissions.png)

6. Configurar la **extremo** propiedades:

    |Use|Para|  
    |---|---|  
    | **Carpeta** | Seleccione la carpeta para recibir correo electrónico. La carpeta predeterminada es la Bandeja de entrada. Tenga en cuenta que las carpetas no son de naturaleza recursiva. Por ejemplo, correo electrónico de las subcarpetas no pudo recuperar. |
    | **Iniciar desde** | Especifique cómo se recibe correo electrónico de Office 365. Este valor indica receivedTimeStamp de un correo electrónico en Office 365 Outlook. Correo electrónico más reciente que se reciben los valores introducidos.  |
    | **Solo los mensajes no leídos** | Active esta opción para leer solo correo electrónico no leído. Manténgala desactivada para leer todo el correo electrónico. |
    | **Acción posterior** | Seleccione una acción posterior a realizarse una vez que se lee un correo electrónico. **Ninguno** es el valor predeterminado y no hace nada después de correo electrónico es recibido por BizTalk. **Marcar como leído** implica, que después de que BizTalk recibe un correo electrónico, el correo electrónico del buzón se marcará como leído. **Eliminar** implica, que después de que BizTalk recibe un correo electrónico, se elimina el correo electrónico del buzón. Acciones de publicación se realizan en forma de mejor esfuerzo.|

    Cuando termine, las propiedades de aspecto similares al siguiente:

    ![Propiedades de punto de conexión](../core/media/office365-mail-receive-properties.png)

7. Seleccione **Aceptar** para guardar los cambios.

### <a name="test-your-receive-settings"></a>Prueba la configuración de recepción

Puede usar un puerto de envío de archivos simple para recibir mensajes desde su correo electrónico de Outlook de Office 365.

1. Crear un puerto de envío mediante el adaptador de archivo. Dentro de las propiedades de puerto de envío, establezca el **carpeta de destino** a **C:\\Temp\\Out\\** y establezca el y **nombre de archivo** a **%MessageID%.xml**.
2. En el archivo de propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == <Receive Port Name>`.
3. Iniciar el correo electrónico de Outlook de Office 365 ubicación de recepción y el puerto de envío de archivo.
4. Buscar mensajes en la carpeta de destino (c:\temp\out).

### <a name="promoted-properties-from-receive-pipeline"></a>Propiedades promocionadas de canalización de recepción

Las siguientes propiedades de la canalización de recepción se promueven de forma predeterminada:

|Nombre de propiedad| Propiedad promocionada|
|---|---|
| **Importancia** | OfficeMail.ReceivedMailImportance |
| **Asunto** | OfficeMail.ReceivedMailSubject |
| **SenderName** | OfficeMail.SenderName |
| **SenderAddress** | OfficeMail.SenderAddress |
| **Tieneadjuntos**| OfficeMail.HasAttachments |

> [!NOTE]
> Solo el contenido del cuerpo del correo electrónico se pasa al mensaje.

## <a name="next-steps"></a>Pasos siguientes
Ver todos los [adaptadores de Office 365](office365-adapters.md), o instalar [característica Pack 3](https://aka.ms/bts2016fp3).