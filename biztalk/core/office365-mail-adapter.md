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
ms.openlocfilehash: daea28056180b436f226fa32b6179bfb1e091f7a
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946216"
---
# <a name="send-and-receive-email-with-office-365-outlook-email-adapter---biztalk-server"></a><span data-ttu-id="14697-104">Enviar y recibir correo electrónico con el adaptador de correo electrónico de Office 365 Outlook - servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="14697-104">Send and receive email with Office 365 Outlook Email adapter - BizTalk Server</span></span>

<span data-ttu-id="14697-105">El adaptador de correo electrónico de Outlook de Office 365 le permite enviar y recibir mensajes de correo desde su correo electrónico de Outlook de Office 365 desde BizTalk.</span><span class="sxs-lookup"><span data-stu-id="14697-105">The Office 365 Outlook Email Adapter allows you to send and receive mails from your Office 365 Outlook Email from BizTalk.</span></span>

## <a name="send-mail-using-a-send-port"></a><span data-ttu-id="14697-106">Enviar correo mediante un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="14697-106">Send mail using a send port</span></span>

1. <span data-ttu-id="14697-107">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y seleccione **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="14697-107">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="14697-108">[Crear un puerto de envío](../core/how-to-create-a-send-port2.md) proporciona alguna orientación.</span><span class="sxs-lookup"><span data-stu-id="14697-108">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="14697-109">Escriba un **nombre**.</span><span class="sxs-lookup"><span data-stu-id="14697-109">Enter a **Name**.</span></span> <span data-ttu-id="14697-110">En **transporte**, establezca el **tipo** a **correo electrónico de Outlook de Office 365**y seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="14697-110">In **Transport**, set the **Type** to **Office 365 Outlook Email**, and select **Configure**.</span></span>

3. <span data-ttu-id="14697-111">Seleccione **iniciar sesión...** e inicie sesión en su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="14697-111">Select **Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="14697-112">La cuenta está rellena automáticamente con su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="14697-112">The account is auto-populated with your email address.</span></span>

4. <span data-ttu-id="14697-113">Permitir la aprobación de BizTalk Server para obtener permiso para tener acceso:</span><span class="sxs-lookup"><span data-stu-id="14697-113">Allow BizTalk Server approval for permission to access:</span></span>

    ![Permisos de correo electrónico de Office 365](../core/media/office365-mail-permissions.png)

5. <span data-ttu-id="14697-115">Configure sus propiedades predeterminadas de correo electrónico de Office 365 Outlook:</span><span class="sxs-lookup"><span data-stu-id="14697-115">Configure your Office 365 Outlook Email default properties:</span></span>

    |<span data-ttu-id="14697-116">Use</span><span class="sxs-lookup"><span data-stu-id="14697-116">Use this</span></span>|<span data-ttu-id="14697-117">Para</span><span class="sxs-lookup"><span data-stu-id="14697-117">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="14697-118">**Para**</span><span class="sxs-lookup"><span data-stu-id="14697-118">**To**</span></span> | <span data-ttu-id="14697-119">Especifique su valor predeterminado para las direcciones de correo electrónico separadas por ';' (máximo de 256 caracteres)</span><span class="sxs-lookup"><span data-stu-id="14697-119">Specify your default To mail addresses separated by ';' (256 character max)</span></span>|
    | <span data-ttu-id="14697-120">**CC**</span><span class="sxs-lookup"><span data-stu-id="14697-120">**CC**</span></span> | <span data-ttu-id="14697-121">Especifique las direcciones de correo electrónico predeterminada CC separadas por ';' (máximo de 256 caracteres)</span><span class="sxs-lookup"><span data-stu-id="14697-121">Specify your default CC mail addresses separated by ';' (256 character max)</span></span>|
    | <span data-ttu-id="14697-122">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="14697-122">**Subject**</span></span> | <span data-ttu-id="14697-123">Mencione al asunto de correo electrónico predeterminado.</span><span class="sxs-lookup"><span data-stu-id="14697-123">Mention your default mail subject.</span></span> <span data-ttu-id="14697-124">(máximo de 256 caracteres)</span><span class="sxs-lookup"><span data-stu-id="14697-124">(256 character max)</span></span> |
    | <span data-ttu-id="14697-125">**Importancia**</span><span class="sxs-lookup"><span data-stu-id="14697-125">**Importance**</span></span> | <span data-ttu-id="14697-126">Seleccione el valor de importancia.</span><span class="sxs-lookup"><span data-stu-id="14697-126">Select your value of Importance.</span></span> <span data-ttu-id="14697-127">Lista desplegable contiene valores **baja**, **Normal** y **alta** con **Normal** el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="14697-127">Dropdown contains values **Low**, **Normal** and **High** with **Normal** being the default.</span></span> |

    <span data-ttu-id="14697-128">Cuando termine, las propiedades de aspecto similares al siguiente:</span><span class="sxs-lookup"><span data-stu-id="14697-128">When finished, your properties look similar to the following:</span></span>

    ![Propiedades de punto de conexión](../core/media/office365-mail-send-properties.png)

6. <span data-ttu-id="14697-130">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="14697-130">Select **Ok** to save your changes.</span></span>

### <a name="important-details"></a><span data-ttu-id="14697-131">Detalles importantes</span><span class="sxs-lookup"><span data-stu-id="14697-131">Important details</span></span>

1. <span data-ttu-id="14697-132">Sólo puede enviar mensajes de texto sin formato mediante el adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="14697-132">You can only send plain text messages using the send adapter.</span></span>
2. <span data-ttu-id="14697-133">Las propiedades predeterminadas también se actualiza con las propiedades promocionadas:</span><span class="sxs-lookup"><span data-stu-id="14697-133">The default properties may also be updated using promoted properties:</span></span>

|<span data-ttu-id="14697-134">Property</span><span class="sxs-lookup"><span data-stu-id="14697-134">Property</span></span>|<span data-ttu-id="14697-135">Propiedad promocionada</span><span class="sxs-lookup"><span data-stu-id="14697-135">Promoted property</span></span>|
|---|---|
| <span data-ttu-id="14697-136">**Para**</span><span class="sxs-lookup"><span data-stu-id="14697-136">**To**</span></span> | <span data-ttu-id="14697-137">OfficeMail.To</span><span class="sxs-lookup"><span data-stu-id="14697-137">OfficeMail.To</span></span> |
| <span data-ttu-id="14697-138">**CC**</span><span class="sxs-lookup"><span data-stu-id="14697-138">**CC**</span></span> | <span data-ttu-id="14697-139">OfficeMail.CC</span><span class="sxs-lookup"><span data-stu-id="14697-139">OfficeMail.CC</span></span> |
| <span data-ttu-id="14697-140">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="14697-140">**Subject**</span></span> | <span data-ttu-id="14697-141">OfficeMail.Subject</span><span class="sxs-lookup"><span data-stu-id="14697-141">OfficeMail.Subject</span></span> |
| <span data-ttu-id="14697-142">**Importancia**</span><span class="sxs-lookup"><span data-stu-id="14697-142">**Importance**</span></span> | <span data-ttu-id="14697-143">OfficeMail.Importance</span><span class="sxs-lookup"><span data-stu-id="14697-143">OfficeMail.Importance</span></span> |

### <a name="test-your-send-port"></a><span data-ttu-id="14697-144">Probar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="14697-144">Test your send port</span></span>

<span data-ttu-id="14697-145">Puede usar un simple archivo de puerto de recepción y ubicación para enviar mensajes a su correo electrónico de Outlook de Office 365.</span><span class="sxs-lookup"><span data-stu-id="14697-145">You can use a simple File receive port and location to send messages to your Office 365 Outlook Email.</span></span>

1. <span data-ttu-id="14697-146">Crear un puerto de recepción mediante el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="14697-146">Create a receive port using the File adapter.</span></span> <span data-ttu-id="14697-147">Dentro de la ubicación de recepción, establezca la **carpeta recepción** a \**C:\Temp\In\** y establece la máscara de archivo en  **\*.xml**.</span><span class="sxs-lookup"><span data-stu-id="14697-147">Within your receive location, set the **Receive folder** to \**C:\Temp\In\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="14697-148">En el adaptador de correo electrónico de Outlook de Office 365 propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == <Receive Port Name>`.</span><span class="sxs-lookup"><span data-stu-id="14697-148">In your Office 365 Outlook Email adapter send port properties, set the **Filters** to `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="14697-149">Pegue lo siguiente en un editor de texto y guarde el archivo como **Office365Mail.xml**.</span><span class="sxs-lookup"><span data-stu-id="14697-149">Paste the following into a text editor, and save the file as **Office365Mail.xml**.</span></span> <span data-ttu-id="14697-150">Este es el mensaje de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="14697-150">This is your sample message.</span></span>

    ```xml
    <ns0:Root xmlns:ns0="http://BizTalk_Server_Project1.Schema1"> 
        <Record> 
            <Name>BizTalk User</Name> 
            <ID>001</ID> 
        </Record> 
    </ns0:Root> 
    ```

4. <span data-ttu-id="14697-151">Iniciar el archivo de ubicación de recepción y el puerto de envío del adaptador de correo electrónico de Outlook de Office 365.</span><span class="sxs-lookup"><span data-stu-id="14697-151">Start the File receive location and the Office 365 Outlook Email adapter send port.</span></span>
5. <span data-ttu-id="14697-152">Copia **Office365Mail.xml** mensaje de ejemplo en la carpeta de recepción (C:\Temp\In\).</span><span class="sxs-lookup"><span data-stu-id="14697-152">Copy **Office365Mail.xml** sample message into the receive folder (C:\Temp\In\).</span></span> <span data-ttu-id="14697-153">El puerto de envío envía el archivo XML como cuerpo del correo electrónico a su correo electrónico de Office 365 Outlook.</span><span class="sxs-lookup"><span data-stu-id="14697-153">The send port sends the XML file as mail body to your Office 365 Outlook Email.</span></span>

## <a name="receive-email-using-a-receive-port"></a><span data-ttu-id="14697-154">Recibir correo electrónico mediante un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="14697-154">Receive email using a receive port</span></span>

1. <span data-ttu-id="14697-155">En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**, seleccione **New**y seleccione **unidireccional puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="14697-155">In the BizTalk Server Administration console, right-click **Receive Ports**, select **New**, and select **One-Way receive port**.</span></span>

    <span data-ttu-id="14697-156">[Crear un puerto de recepción](../core/how-to-create-a-receive-port.md) proporciona alguna orientación.</span><span class="sxs-lookup"><span data-stu-id="14697-156">[Create a receive port](../core/how-to-create-a-receive-port.md) provides some guidance.</span></span>

2. <span data-ttu-id="14697-157">Escriba un nombre y seleccione **ubicaciones de recepción**.</span><span class="sxs-lookup"><span data-stu-id="14697-157">Enter a name, and select **Receive Locations**.</span></span>

3. <span data-ttu-id="14697-158">Seleccione **New**, y **nombre** la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="14697-158">Select **New**, and **Name** the receive location.</span></span> <span data-ttu-id="14697-159">En **transporte**, seleccione **correo electrónico de Outlook de Office 365** desde el **tipo** lista desplegable y, a continuación, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="14697-159">In **Transport**, select **Office 365 Outlook Email** from the **Type** drop-down list, and then select **Configure**.</span></span>

4. <span data-ttu-id="14697-160">Seleccione **[iniciar sesión...** e inicie sesión en su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="14697-160">Select **[Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="14697-161">La cuenta está rellena automáticamente con su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="14697-161">The account is auto-populated with your email address.</span></span>

5. <span data-ttu-id="14697-162">Permitir la aprobación de BizTalk Server para obtener permiso para tener acceso:</span><span class="sxs-lookup"><span data-stu-id="14697-162">Allow BizTalk Server approval for permission to access:</span></span>

    ![Permisos de correo electrónico de Office 365](../core/media/office365-mail-permissions.png)

6. <span data-ttu-id="14697-164">Configurar la **extremo** propiedades:</span><span class="sxs-lookup"><span data-stu-id="14697-164">Configure the **Endpoint** properties:</span></span>

    |<span data-ttu-id="14697-165">Use</span><span class="sxs-lookup"><span data-stu-id="14697-165">Use this</span></span>|<span data-ttu-id="14697-166">Para</span><span class="sxs-lookup"><span data-stu-id="14697-166">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="14697-167">**Carpeta**</span><span class="sxs-lookup"><span data-stu-id="14697-167">**Folder**</span></span> | <span data-ttu-id="14697-168">Seleccione la carpeta para recibir correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="14697-168">Select the folder to get email.</span></span> <span data-ttu-id="14697-169">La carpeta predeterminada es la Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="14697-169">The default folder is Inbox.</span></span> <span data-ttu-id="14697-170">Tenga en cuenta que las carpetas no son de naturaleza recursiva.</span><span class="sxs-lookup"><span data-stu-id="14697-170">Note that folders aren’t recursive in nature.</span></span> <span data-ttu-id="14697-171">Por ejemplo, correo electrónico de las subcarpetas no pudo recuperar.</span><span class="sxs-lookup"><span data-stu-id="14697-171">For example, email from subfolders aren’t retreived.</span></span> |
    | <span data-ttu-id="14697-172">**Iniciar desde**</span><span class="sxs-lookup"><span data-stu-id="14697-172">**Start from**</span></span> | <span data-ttu-id="14697-173">Especifique cómo se recibe correo electrónico de Office 365.</span><span class="sxs-lookup"><span data-stu-id="14697-173">Enter how email is received from Office 365.</span></span> <span data-ttu-id="14697-174">Este valor indica receivedTimeStamp de un correo electrónico en Office 365 Outlook.</span><span class="sxs-lookup"><span data-stu-id="14697-174">This value indicates receivedTimeStamp of an email in Office 365 Outlook.</span></span> <span data-ttu-id="14697-175">Correo electrónico más reciente que se reciben los valores introducidos.</span><span class="sxs-lookup"><span data-stu-id="14697-175">Email more recent than the entered values are received.</span></span>  |
    | <span data-ttu-id="14697-176">**Solo los mensajes no leídos**</span><span class="sxs-lookup"><span data-stu-id="14697-176">**Unread mails only**</span></span> | <span data-ttu-id="14697-177">Active esta opción para leer solo correo electrónico no leído.</span><span class="sxs-lookup"><span data-stu-id="14697-177">Check this to read only unread email.</span></span> <span data-ttu-id="14697-178">Manténgala desactivada para leer todo el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="14697-178">Keep it unchecked to read all email.</span></span> |
    | <span data-ttu-id="14697-179">**Acción posterior**</span><span class="sxs-lookup"><span data-stu-id="14697-179">**Post Action**</span></span> | <span data-ttu-id="14697-180">Seleccione una acción posterior a realizarse una vez que se lee un correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="14697-180">Select a post action to be performed after an email is read.</span></span> <span data-ttu-id="14697-181">**Ninguno** es el valor predeterminado y no hace nada después de correo electrónico es recibido por BizTalk.</span><span class="sxs-lookup"><span data-stu-id="14697-181">**None** is the default, and does nothing after email is received by BizTalk.</span></span> <span data-ttu-id="14697-182">**Marcar como leído** implica, que después de que BizTalk recibe un correo electrónico, el correo electrónico del buzón se marcará como leído.</span><span class="sxs-lookup"><span data-stu-id="14697-182">**Mark as read** implies, that after an email is received by BizTalk, the email in your mailbox is marked as read.</span></span> <span data-ttu-id="14697-183">**Eliminar** implica, que después de que BizTalk recibe un correo electrónico, se elimina el correo electrónico del buzón.</span><span class="sxs-lookup"><span data-stu-id="14697-183">**Delete** implies, that after an email is received by BizTalk, the email in your mailbox is deleted.</span></span> <span data-ttu-id="14697-184">Acciones de publicación se realizan en forma de mejor esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="14697-184">Post actions are performed on a best-effort basis.</span></span>|

    <span data-ttu-id="14697-185">Cuando termine, las propiedades de aspecto similares al siguiente:</span><span class="sxs-lookup"><span data-stu-id="14697-185">When finished, your properties look similar to the following:</span></span>

    ![Propiedades de punto de conexión](../core/media/office365-mail-receive-properties.png)

7. <span data-ttu-id="14697-187">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="14697-187">Select **Ok** to save your changes.</span></span>

### <a name="test-your-receive-settings"></a><span data-ttu-id="14697-188">Prueba la configuración de recepción</span><span class="sxs-lookup"><span data-stu-id="14697-188">Test your receive settings</span></span>

<span data-ttu-id="14697-189">Puede usar un puerto de envío de archivos simple para recibir mensajes desde su correo electrónico de Outlook de Office 365.</span><span class="sxs-lookup"><span data-stu-id="14697-189">You can use a simple File send port to receive messages from your Office 365 Outlook Email.</span></span>

1. <span data-ttu-id="14697-190">Crear un puerto de envío mediante el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="14697-190">Create a send port using the File adapter.</span></span> <span data-ttu-id="14697-191">Dentro de las propiedades de puerto de envío, establezca el **carpeta de destino** a **C:\Temp\Out\** y establezca el y **nombre de archivo** a **%MessageID%.xml** .</span><span class="sxs-lookup"><span data-stu-id="14697-191">Within your send port properties, set the **Destination folder** to **C:\Temp\Out\**, and set the and **File name** to **%MessageID%.xml**.</span></span>
2. <span data-ttu-id="14697-192">En el archivo de propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == <Receive Port Name>`.</span><span class="sxs-lookup"><span data-stu-id="14697-192">In your File send port properties, set the **Filters** to  `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="14697-193">Iniciar el correo electrónico de Outlook de Office 365 ubicación de recepción y el puerto de envío de archivo.</span><span class="sxs-lookup"><span data-stu-id="14697-193">Start the Office 365 Outlook Email receive location and the File send port.</span></span>
4. <span data-ttu-id="14697-194">Buscar mensajes en la carpeta de destino (c:\temp\out).</span><span class="sxs-lookup"><span data-stu-id="14697-194">Look for messages in the destination folder (c:\temp\out).</span></span>

### <a name="promoted-properties-from-receive-pipeline"></a><span data-ttu-id="14697-195">Propiedades promocionadas de canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="14697-195">Promoted Properties from receive pipeline</span></span>

<span data-ttu-id="14697-196">Las siguientes propiedades de la canalización de recepción se promueven de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="14697-196">The following properties from the Receive Pipeline are promoted by default:</span></span>

|<span data-ttu-id="14697-197">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="14697-197">Property Name</span></span>| <span data-ttu-id="14697-198">Propiedad promocionada</span><span class="sxs-lookup"><span data-stu-id="14697-198">Promoted Property</span></span>|
|---|---|
| <span data-ttu-id="14697-199">**Importancia**</span><span class="sxs-lookup"><span data-stu-id="14697-199">**Importance**</span></span> | <span data-ttu-id="14697-200">OfficeMail.ReceivedMailImportance</span><span class="sxs-lookup"><span data-stu-id="14697-200">OfficeMail.ReceivedMailImportance</span></span> |
| <span data-ttu-id="14697-201">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="14697-201">**Subject**</span></span> | <span data-ttu-id="14697-202">OfficeMail.ReceivedMailSubject</span><span class="sxs-lookup"><span data-stu-id="14697-202">OfficeMail.ReceivedMailSubject</span></span> |
| <span data-ttu-id="14697-203">**SenderName**</span><span class="sxs-lookup"><span data-stu-id="14697-203">**SenderName**</span></span> | <span data-ttu-id="14697-204">OfficeMail.SenderName</span><span class="sxs-lookup"><span data-stu-id="14697-204">OfficeMail.SenderName</span></span> |
| <span data-ttu-id="14697-205">**SenderAddress**</span><span class="sxs-lookup"><span data-stu-id="14697-205">**SenderAddress**</span></span> | <span data-ttu-id="14697-206">OfficeMail.SenderAddress</span><span class="sxs-lookup"><span data-stu-id="14697-206">OfficeMail.SenderAddress</span></span> |
| <span data-ttu-id="14697-207">**Tieneadjuntos**</span><span class="sxs-lookup"><span data-stu-id="14697-207">**HasAttachments**</span></span>| <span data-ttu-id="14697-208">OfficeMail.HasAttachments</span><span class="sxs-lookup"><span data-stu-id="14697-208">OfficeMail.HasAttachments</span></span> |

> [!NOTE]
> <span data-ttu-id="14697-209">Solo el contenido del cuerpo del correo electrónico se pasa al mensaje.</span><span class="sxs-lookup"><span data-stu-id="14697-209">Only the body content of the Email is passed through to the message.</span></span>

## <a name="next-steps"></a><span data-ttu-id="14697-210">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="14697-210">Next steps</span></span>
<span data-ttu-id="14697-211">Ver todos los [adaptadores de Office 365](office365-adapters.md), o instalar [característica Pack 3](https://aka.ms/bts2016fp3).</span><span class="sxs-lookup"><span data-stu-id="14697-211">See all the [Office 365 adapters](office365-adapters.md), or install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>