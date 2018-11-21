---
title: Usar el adaptador de calendario de Outlook de Office 365 | Microsoft Docs
description: Enviar y recibir mensajes mediante el adaptador de calendario de Outlook de Office 365 en BizTalk Server. Utilice el adaptador para crear y recibir eventos de calendario mediante un puerto de recepción y el puerto de envío y un mensaje XML de ejemplo para crear el evento del calendario.
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
ms.openlocfilehash: 6787ece4af5ebdd17733dde33ae524f2c9b802e8
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752652"
---
# <a name="create-calendar-events-with-the-office-365-outlook-calendar-adapter---biztalk-server"></a>Crear eventos de calendario con el adaptador de calendario de Office 365 Outlook - servidor BizTalk Server

Utilice el adaptador de calendario de Outlook de Office 365 en BizTalk Server para crear y recibir eventos de calendario de su calendario de Outlook de Office 365.

## <a name="create-events-using-a-send-port"></a>Crear eventos mediante un puerto de envío

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y seleccione **puerto de envío unidireccional estático**.

    [Crear un puerto de envío](../core/how-to-create-a-send-port2.md) proporciona alguna orientación.

2. Escriba un **nombre**. En **transporte**, establezca el **tipo** a **calendario de Outlook de Office 365**y seleccione **configurar**.

3. Seleccione **[iniciar sesión...** e inicie sesión en su cuenta de Office 365. La cuenta está rellena automáticamente con su dirección de correo electrónico.

4. Permitir la aprobación de BizTalk Server para obtener permiso para tener acceso:

    ![Permisos del calendario de Office 365](../core/media/office365-calendar-permissions.png)

5. Configure las propiedades de forma predeterminada de calendario de Outlook de Office 365:

    |Use|Para|  
    |---|---|  
    | **Calendario** | Seleccione el calendario en la que se crearán los eventos. |
    | **Asunto** | Establecer al asunto predeterminado para los eventos creados. (máximo de 256 caracteres) |
    | **Asistentes obligatorios** | Escriba las direcciones de correo electrónico de los asistentes predeterminados necesarios separadas por ';'. (máximo de 256 caracteres) |
    | **Asistentes opcionales** | Especificar el valor predeterminado asistentes opcionales de correo electrónico direcciones separadas por ';'. (máximo de 256 caracteres) |

6. Seleccione un calendario: 

    ![Calendarios de Office 365](../core/media/office365-calendars.png)

    Cuando termine, las propiedades de aspecto similares al siguiente:

    ![Propiedades de punto de conexión](../core/media/office365-calendar-send-properties.png)

7. Seleccione **Aceptar** para guardar los cambios.

### <a name="test-your-send-port"></a>Probar el puerto de envío

Puede usar un simple archivo de puerto de recepción y ubicación para crear un evento en su calendario de Outlook de Office 365.

1. Crear un puerto de recepción mediante el adaptador de archivo. Dentro de la ubicación de recepción, establezca la **carpeta recepción** a **C:\\Temp\\en\\** y establece la máscara de archivo en **\*.xml**.
2. En el adaptador de calendario de Outlook de Office 365 propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == <Receive Port Name>`.
3. Pegue lo siguiente en un editor de texto y guarde el archivo como **Office365Calendar.xml**. Este es el mensaje de ejemplo.

    ```xml
    <Event xmlns="http://schemas.microsoft.com/BizTalk/Office365OutlookCalendar/Send"> 
        <subject>Test event 1</subject> 
        <body> 
        <contentType>html</contentType> 
        <content>&lt;html&gt; 
        &lt;head&gt; 
        &lt;meta http-equiv="Content-Type" content="text/html; charset=utf-8"&gt; 
        &lt;meta content="text/html; charset=us-ascii"&gt; 
        &lt;/head&gt; 
        &lt;body&gt; 
        Test body for event Test event 1 
        &lt;/body&gt; 
        &lt;/html&gt; 
        </content> 
        </body> 
    </Event> 
    ```
    **El esquema XML se proporciona como parte del SDK de dentro de < instalación de BizTalk Folder\SDK\Schemas >**

4. Iniciar el archivo de ubicación de recepción y el puerto de envío del adaptador de calendario de Outlook de Office 365.
5. Copia **Office365Calendar.xml** mensaje de ejemplo en la carpeta de recepción (C:\Temp\In\). El puerto de envío crea un evento en su calendario de Outlook de Office 365 basado en el documento xml.

## <a name="receive-events-using-a-receive-port"></a>Recepción de eventos mediante un puerto de recepción

1. En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**, seleccione **New**y seleccione **unidireccional puerto de recepción**.

    [Crear un puerto de recepción](../core/how-to-create-a-receive-port.md) proporciona alguna orientación.

2. Escriba un nombre y seleccione **ubicaciones de recepción**.

3. Seleccione **New**, y **nombre** la ubicación de recepción. En **transporte**, seleccione **calendario de Outlook de Office 365** desde el **tipo** lista desplegable y, a continuación, seleccione **configurar**.

4. Seleccione **iniciar sesión...** e inicie sesión en su cuenta de Office 365. La cuenta está rellena automáticamente con su dirección de correo electrónico.

5. Permitir la aprobación de BizTalk Server para obtener permiso para tener acceso:

    ![Permisos del calendario de Office 365](../core/media/office365-calendar-permissions.png)

6. Configurar la **extremo** propiedades:

    |Use|Para|  
    |---|---|  
    | **Calendario** | Seleccione el calendario desde el que se recuperarán los eventos.  |
    | **A partir de** | Seleccione el intervalo de tiempo dentro del cual un evento de calendario debe comenzar con el fin de ser recibido por BizTalk (valor predeterminado es 15 minutos).  |

7. Seleccionar un calendario:

    ![Calendarios de Office 365](../core/media/office365-calendars.png)

    Cuando termine, las propiedades de aspecto similares al siguiente:

    ![Propiedades de punto de conexión](../core/media/office365-calendar-receive-properties.png)

8. Seleccione **Aceptar** para guardar los cambios.

### <a name="test-your-receive-settings"></a>Prueba la configuración de recepción

Puede usar un puerto de envío de archivos simple para recibir mensajes desde su calendario de Outlook de Office 365.

1. Crear un puerto de envío mediante el adaptador de archivo. Dentro de las propiedades de puerto de envío, establezca el **carpeta de destino** a **C:\\Temp\\Out\\** y establezca el y **nombre de archivo** a **%MessageID%.xml**.
2. En el archivo de propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == <Receive Port Name>`.
3. Inicio del calendario de Outlook de Office 365 ubicación de recepción y el puerto de envío de archivo.
4. Buscar mensajes en la carpeta de destino (c:\temp\out). 
**El esquema XML se incluye en el SDK en `\Program Files (x86)\Microsoft BizTalk Server <your version>\SDK\Schemas`.**

### <a name="example-of-a-received-calendar-event-xml"></a>Ejemplo de un archivo xml de eventos de calendario recibidos

```xml
<ns0:Event xmlns:ns0="http://schemas.microsoft.com/BizTalk/Office365OutlookCalendar/Receive"> 
<reminderMinutesBeforeStart>20160</reminderMinutesBeforeStart> 
<importance>normal</importance> 
<subject>Let's meet</subject> 
<id>AQMkADAwATNiZmYAZC0xMQBlOC0yODQ1LTA</id> 
<body> 
<contentType>html</contentType> 
<content>&lt;html&gt; 
&lt;head&gt; 
&lt;meta http-equiv="Content-Type" content="text/html; charset=utf-8"&gt; 
&lt;meta content="text/html; charset=us-ascii"&gt; 
&lt;meta name="ProgId" content="Word.Document"&gt; 
&lt;meta name="Generator" content="Microsoft Word 15"&gt; 
&lt;meta name="Originator" content="Microsoft Word 15"&gt; 
&lt;link rel="File-List" href="cid:filelist.xml@01D40724.27036CE0"&gt;&lt;style&gt; 
&lt;!-- 
@font-face 
  {font-family:"Cambria Math"} 
@font-face 
  {font-family:Calibri} 
p.MsoNormal, li.MsoNormal, div.MsoNormal 
  {margin:0in; 
  margin-bottom:.0001pt; 
  font-size:11.0pt; 
  font-family:"Calibri",sans-serif} 
a:link, span.MsoHyperlink 
  {color:#0563C1; 
  text-decoration:underline} 
a:visited, span.MsoHyperlinkFollowed 
  {color:#954F72; 
  text-decoration:underline} 
span.EmailStyle17 
  {font-family:"Calibri",sans-serif; 
  color:windowtext} 
.MsoChpDefault 
  {font-family:"Calibri",sans-serif} 
@page WordSection1 
  {margin:1.0in 1.0in 1.0in 1.0in} 
div.WordSection1 
  {} 
--&gt; 
&lt;/style&gt; 
&lt;/head&gt; 
&lt;body lang="EN-US" link="#0563C1" vlink="#954F72" style=""&gt; 
&lt;div class="WordSection1"&gt; 
&lt;p class="MsoNormal"&gt;Let’s sync up.&lt;/p&gt; 
&lt;/div&gt; 
&lt;/body&gt; 
&lt;/html&gt; 
</content> 
</body> 
<bodyPreview>Let’s sync up.</bodyPreview> 
<attendees> 
<type>required</type> 
<status> 
<response>none</response> 
<time>0001-01-01T00:00:00Z</time> 
</status> 
<emailAddress> 
<name>someone@contoso.com</name> 
<address>someone@contoso.com</address> 
</emailAddress> 
</attendees> 
<start> 
<dateTime>2018-06-25T17:00:00</dateTime> 
<timeZone>UTC</timeZone> 
</start> 
<end> 
<dateTime>2018-06-25T17:30:00</dateTime> 
<timeZone>UTC</timeZone> 
</end> 
<location> 
<displayName>Your office</displayName> 
<locationType>default</locationType> 
<uniqueId>Your office</uniqueId> 
<uniqueIdType>private</uniqueIdType> 
</location> 
<responseRequested>true</responseRequested> 
<seriesMasterId /> 
<isCancelled>false</isCancelled> 
<isOrganizer>true</isOrganizer> 
<createdDateTime>2018-06-18T23:48:35.0164728Z</createdDateTime> 
<lastModifiedDateTime>2018-06-18T23:48:22.178Z</lastModifiedDateTime> 
<hasAttachments>false</hasAttachments> 
<responseStatus> 
<response>none</response> 
<time>0001-01-01T00:00:00Z</time> 
</responseStatus> 
<changeKey>SFa3sLJfdiDEIpfwAAIAU=</changeKey> 
<originalStartTimeZone>Pacific Standard Time</originalStartTimeZone> 
<originalEndTimeZone>Pacific Standard Time</originalEndTimeZone> 
<isReminderOn>false</isReminderOn> 
<sensitivity>normal</sensitivity> 
<isAllDay>false</isAllDay> 
<showAs>busy</showAs> 
<type>singleInstance</type> 
<onlineMeetingUrl /> 
<recurrence /> 
<locations> 
<displayName>Your office</displayName> 
<locationType>default</locationType> 
<uniqueId>Your office</uniqueId> 
<uniqueIdType>private</uniqueIdType> 
</locations> 
<organizer> 
<emailAddress> 
<name>someone@contoso.com</name> 
<address>/O=FIRST ORGANIZATION/OU=EXCHANGE ADMINISTRATIVE GROUP(FYDIBOH3SPDLT)/CN=RECIPIENTS/CN=0003B11E8245</address> 
</emailAddress> 
</organizer> 
</ns0:Event> 
```

## <a name="next-steps"></a>Pasos siguientes
Ver todos los [adaptadores de Office 365](office365-adapters.md), o instalar [característica Pack 3](https://aka.ms/bts2016fp3).