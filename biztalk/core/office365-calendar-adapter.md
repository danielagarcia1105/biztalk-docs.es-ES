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
ms.openlocfilehash: ab724870e9c75a60119e86f7f62d6823f1db9873
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946222"
---
# <a name="create-calendar-events-with-the-office-365-outlook-calendar-adapter---biztalk-server"></a><span data-ttu-id="811f8-104">Crear eventos de calendario con el adaptador de calendario de Office 365 Outlook - servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="811f8-104">Create calendar events with the Office 365 Outlook Calendar adapter - BizTalk Server</span></span>

<span data-ttu-id="811f8-105">Utilice el adaptador de calendario de Outlook de Office 365 en BizTalk Server para crear y recibir eventos de calendario de su calendario de Outlook de Office 365.</span><span class="sxs-lookup"><span data-stu-id="811f8-105">Use the Office 365 Outlook Calendar adapter in BizTalk Server to create and receive calendar events from your Office 365 Outlook Calendar.</span></span>

## <a name="create-events-using-a-send-port"></a><span data-ttu-id="811f8-106">Crear eventos mediante un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="811f8-106">Create events using a send port</span></span>

1. <span data-ttu-id="811f8-107">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y seleccione **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="811f8-107">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="811f8-108">[Crear un puerto de envío](../core/how-to-create-a-send-port2.md) proporciona alguna orientación.</span><span class="sxs-lookup"><span data-stu-id="811f8-108">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="811f8-109">Escriba un **nombre**.</span><span class="sxs-lookup"><span data-stu-id="811f8-109">Enter a **Name**.</span></span> <span data-ttu-id="811f8-110">En **transporte**, establezca el **tipo** a **calendario de Outlook de Office 365**y seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="811f8-110">In **Transport**, set the **Type** to **Office 365 Outlook Calendar**, and select **Configure**.</span></span>

3. <span data-ttu-id="811f8-111">Seleccione **[iniciar sesión...** e inicie sesión en su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="811f8-111">Select **[Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="811f8-112">La cuenta está rellena automáticamente con su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="811f8-112">The account is auto-populated with your email address.</span></span>

4. <span data-ttu-id="811f8-113">Permitir la aprobación de BizTalk Server para obtener permiso para tener acceso:</span><span class="sxs-lookup"><span data-stu-id="811f8-113">Allow BizTalk Server approval for permission to access:</span></span>

    ![Permisos del calendario de Office 365](../core/media/office365-calendar-permissions.png)

5. <span data-ttu-id="811f8-115">Configure las propiedades de forma predeterminada de calendario de Outlook de Office 365:</span><span class="sxs-lookup"><span data-stu-id="811f8-115">Configure your Office365 Outlook Calendar default properties:</span></span>

    |<span data-ttu-id="811f8-116">Use</span><span class="sxs-lookup"><span data-stu-id="811f8-116">Use this</span></span>|<span data-ttu-id="811f8-117">Para</span><span class="sxs-lookup"><span data-stu-id="811f8-117">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="811f8-118">**Calendario**</span><span class="sxs-lookup"><span data-stu-id="811f8-118">**Calendar**</span></span> | <span data-ttu-id="811f8-119">Seleccione el calendario en la que se crearán los eventos.</span><span class="sxs-lookup"><span data-stu-id="811f8-119">Select the calendar in which events will be created.</span></span> |
    | <span data-ttu-id="811f8-120">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="811f8-120">**Subject**</span></span> | <span data-ttu-id="811f8-121">Establecer al asunto predeterminado para los eventos creados.</span><span class="sxs-lookup"><span data-stu-id="811f8-121">Set the default subject for events created.</span></span> <span data-ttu-id="811f8-122">(máximo de 256 caracteres)</span><span class="sxs-lookup"><span data-stu-id="811f8-122">(256 character max)</span></span> |
    | <span data-ttu-id="811f8-123">**Asistentes obligatorios**</span><span class="sxs-lookup"><span data-stu-id="811f8-123">**Required Attendees**</span></span> | <span data-ttu-id="811f8-124">Escriba las direcciones de correo electrónico de los asistentes predeterminados necesarios separadas por ';'.</span><span class="sxs-lookup"><span data-stu-id="811f8-124">Enter your default required attendees email addresses separated by ';'.</span></span> <span data-ttu-id="811f8-125">(máximo de 256 caracteres)</span><span class="sxs-lookup"><span data-stu-id="811f8-125">(256 character max)</span></span> |
    | <span data-ttu-id="811f8-126">**Asistentes opcionales**</span><span class="sxs-lookup"><span data-stu-id="811f8-126">**Optional Attendees**</span></span> | <span data-ttu-id="811f8-127">Especificar el valor predeterminado asistentes opcionales de correo electrónico direcciones separadas por ';'.</span><span class="sxs-lookup"><span data-stu-id="811f8-127">Enter your default optional attendees email addresses separated by ';'.</span></span> <span data-ttu-id="811f8-128">(máximo de 256 caracteres)</span><span class="sxs-lookup"><span data-stu-id="811f8-128">(256 character max)</span></span> |

6. <span data-ttu-id="811f8-129">Seleccione un calendario:</span><span class="sxs-lookup"><span data-stu-id="811f8-129">Select a calendar:</span></span> 

    ![Calendarios de Office 365](../core/media/office365-calendars.png)

    <span data-ttu-id="811f8-131">Cuando termine, las propiedades de aspecto similares al siguiente:</span><span class="sxs-lookup"><span data-stu-id="811f8-131">When finished, your properties look similar to the following:</span></span>

    ![Propiedades de punto de conexión](../core/media/office365-calendar-send-properties.png)

7. <span data-ttu-id="811f8-133">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="811f8-133">Select **Ok** to save your changes.</span></span>

### <a name="test-your-send-port"></a><span data-ttu-id="811f8-134">Probar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="811f8-134">Test your send port</span></span>

<span data-ttu-id="811f8-135">Puede usar un simple archivo de puerto de recepción y ubicación para crear un evento en su calendario de Outlook de Office 365.</span><span class="sxs-lookup"><span data-stu-id="811f8-135">You can use a simple File receive port and location to create an event on your Office 365 Outlook Calendar.</span></span>

1. <span data-ttu-id="811f8-136">Crear un puerto de recepción mediante el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="811f8-136">Create a receive port using the File adapter.</span></span> <span data-ttu-id="811f8-137">Dentro de la ubicación de recepción, establezca la **carpeta recepción** a \**C:\Temp\In\** y establece la máscara de archivo en  **\*.xml**.</span><span class="sxs-lookup"><span data-stu-id="811f8-137">Within your receive location,  set the **Receive folder** to \**C:\Temp\In\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="811f8-138">En el adaptador de calendario de Outlook de Office 365 propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == <Receive Port Name>`.</span><span class="sxs-lookup"><span data-stu-id="811f8-138">In your Office 365 Outlook Calendar adapter send port properties, set the **Filters** to `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="811f8-139">Pegue lo siguiente en un editor de texto y guarde el archivo como **Office365Calendar.xml**.</span><span class="sxs-lookup"><span data-stu-id="811f8-139">Paste the following into a text editor, and save the file as **Office365Calendar.xml**.</span></span> <span data-ttu-id="811f8-140">Este es el mensaje de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="811f8-140">This is your sample message.</span></span>

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
    <span data-ttu-id="811f8-141">**El esquema XML se proporciona como parte del SDK de dentro de < instalación de BizTalk Folder\SDK\Schemas >**</span><span class="sxs-lookup"><span data-stu-id="811f8-141">**The XML schema is provided as part of the SDK inside < BizTalk Installation Folder\SDK\Schemas >**</span></span>

4. <span data-ttu-id="811f8-142">Iniciar el archivo de ubicación de recepción y el puerto de envío del adaptador de calendario de Outlook de Office 365.</span><span class="sxs-lookup"><span data-stu-id="811f8-142">Start the File receive location and the Office 365 Outlook Calendar adapter send port.</span></span>
5. <span data-ttu-id="811f8-143">Copia **Office365Calendar.xml** mensaje de ejemplo en la carpeta de recepción (C:\Temp\In\).</span><span class="sxs-lookup"><span data-stu-id="811f8-143">Copy **Office365Calendar.xml** sample message into the receive folder (C:\Temp\In\).</span></span> <span data-ttu-id="811f8-144">El puerto de envío crea un evento en su calendario de Outlook de Office 365 basado en el documento xml.</span><span class="sxs-lookup"><span data-stu-id="811f8-144">The send port creates an event in your Office 365 Outlook calendar based on the xml.</span></span>

## <a name="receive-events-using-a-receive-port"></a><span data-ttu-id="811f8-145">Recepción de eventos mediante un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="811f8-145">Receive events using a receive port</span></span>

1. <span data-ttu-id="811f8-146">En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**, seleccione **New**y seleccione **unidireccional puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="811f8-146">In the BizTalk Server Administration console, right-click **Receive Ports**, select **New**, and select **One-Way receive port**.</span></span>

    <span data-ttu-id="811f8-147">[Crear un puerto de recepción](../core/how-to-create-a-receive-port.md) proporciona alguna orientación.</span><span class="sxs-lookup"><span data-stu-id="811f8-147">[Create a receive port](../core/how-to-create-a-receive-port.md) provides some guidance.</span></span>

2. <span data-ttu-id="811f8-148">Escriba un nombre y seleccione **ubicaciones de recepción**.</span><span class="sxs-lookup"><span data-stu-id="811f8-148">Enter a name, and select **Receive Locations**.</span></span>

3. <span data-ttu-id="811f8-149">Seleccione **New**, y **nombre** la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="811f8-149">Select **New**, and **Name** the receive location.</span></span> <span data-ttu-id="811f8-150">En **transporte**, seleccione **calendario de Outlook de Office 365** desde el **tipo** lista desplegable y, a continuación, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="811f8-150">In **Transport**, select **Office 365 Outlook Calendar** from the **Type** drop-down list, and then select **Configure**.</span></span>

4. <span data-ttu-id="811f8-151">Seleccione **iniciar sesión...** e inicie sesión en su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="811f8-151">Select **Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="811f8-152">La cuenta está rellena automáticamente con su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="811f8-152">The account is auto-populated with your email address.</span></span>

5. <span data-ttu-id="811f8-153">Permitir la aprobación de BizTalk Server para obtener permiso para tener acceso:</span><span class="sxs-lookup"><span data-stu-id="811f8-153">Allow BizTalk Server approval for permission to access:</span></span>

    ![Permisos del calendario de Office 365](../core/media/office365-calendar-permissions.png)

6. <span data-ttu-id="811f8-155">Configurar la **extremo** propiedades:</span><span class="sxs-lookup"><span data-stu-id="811f8-155">Configure the **Endpoint** properties:</span></span>

    |<span data-ttu-id="811f8-156">Use</span><span class="sxs-lookup"><span data-stu-id="811f8-156">Use this</span></span>|<span data-ttu-id="811f8-157">Para</span><span class="sxs-lookup"><span data-stu-id="811f8-157">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="811f8-158">**Calendario**</span><span class="sxs-lookup"><span data-stu-id="811f8-158">**Calendar**</span></span> | <span data-ttu-id="811f8-159">Seleccione el calendario desde el que se recuperarán los eventos.</span><span class="sxs-lookup"><span data-stu-id="811f8-159">Select the calendar from which events will be fetched.</span></span>  |
    | <span data-ttu-id="811f8-160">**A partir de**</span><span class="sxs-lookup"><span data-stu-id="811f8-160">**Starting within**</span></span> | <span data-ttu-id="811f8-161">Seleccione el intervalo de tiempo dentro del cual un evento de calendario debe comenzar con el fin de ser recibido por BizTalk (valor predeterminado es 15 minutos).</span><span class="sxs-lookup"><span data-stu-id="811f8-161">Select the time interval within which a calendar event has to start in order to be received by BizTalk (default is 15 minutes).</span></span>  |

7. <span data-ttu-id="811f8-162">Seleccionar un calendario:</span><span class="sxs-lookup"><span data-stu-id="811f8-162">Selecting a calendar:</span></span>

    ![Calendarios de Office 365](../core/media/office365-calendars.png)

    <span data-ttu-id="811f8-164">Cuando termine, las propiedades de aspecto similares al siguiente:</span><span class="sxs-lookup"><span data-stu-id="811f8-164">When finished, your properties look similar to the following:</span></span>

    ![Propiedades de punto de conexión](../core/media/office365-calendar-receive-properties.png)

8. <span data-ttu-id="811f8-166">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="811f8-166">Select **Ok** to save your changes.</span></span>

### <a name="test-your-receive-settings"></a><span data-ttu-id="811f8-167">Prueba la configuración de recepción</span><span class="sxs-lookup"><span data-stu-id="811f8-167">Test your receive settings</span></span>

<span data-ttu-id="811f8-168">Puede usar un puerto de envío de archivos simple para recibir mensajes desde su calendario de Outlook de Office 365.</span><span class="sxs-lookup"><span data-stu-id="811f8-168">You can use a simple File send port to receive messages from your Office 365 Outlook Calendar.</span></span>

1. <span data-ttu-id="811f8-169">Crear un puerto de envío mediante el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="811f8-169">Create a send port using the File adapter.</span></span> <span data-ttu-id="811f8-170">Dentro de las propiedades de puerto de envío, establezca el **carpeta de destino** a **C:\Temp\Out\** y establezca el y **nombre de archivo** a **%MessageID%.xml** .</span><span class="sxs-lookup"><span data-stu-id="811f8-170">Within your send port properties, set the **Destination folder** to **C:\Temp\Out\**, and set the and **File name** to **%MessageID%.xml**.</span></span>
2. <span data-ttu-id="811f8-171">En el archivo de propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == <Receive Port Name>`.</span><span class="sxs-lookup"><span data-stu-id="811f8-171">In your File send port properties, set the **Filters** to  `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="811f8-172">Inicio del calendario de Outlook de Office 365 ubicación de recepción y el puerto de envío de archivo.</span><span class="sxs-lookup"><span data-stu-id="811f8-172">Start the Office 365 Outlook Calendar receive location and the File send port.</span></span>
4. <span data-ttu-id="811f8-173">Buscar mensajes en la carpeta de destino (c:\temp\out).</span><span class="sxs-lookup"><span data-stu-id="811f8-173">Look for messages in the destination folder (c:\temp\out).</span></span> 
<span data-ttu-id="811f8-174">**El esquema XML se incluye en el SDK en `\Program Files (x86)\Microsoft BizTalk Server <your version>\SDK\Schemas`.**</span><span class="sxs-lookup"><span data-stu-id="811f8-174">**The XML schema is included in the SDK at `\Program Files (x86)\Microsoft BizTalk Server <your version>\SDK\Schemas`.**</span></span>

### <a name="example-of-a-received-calendar-event-xml"></a><span data-ttu-id="811f8-175">Ejemplo de un archivo xml de eventos de calendario recibidos</span><span class="sxs-lookup"><span data-stu-id="811f8-175">Example of a received calendar event xml</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="811f8-176">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="811f8-176">Next steps</span></span>
<span data-ttu-id="811f8-177">Ver todos los [adaptadores de Office 365](office365-adapters.md), o instalar [característica Pack 3](https://aka.ms/bts2016fp3).</span><span class="sxs-lookup"><span data-stu-id="811f8-177">See all the [Office 365 adapters](office365-adapters.md), or install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>