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
# <a name="event-hub-adapter-in-biztalk"></a><span data-ttu-id="37c63-103">Adaptador del centro de eventos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="37c63-103">Event Hub adapter in BizTalk</span></span>

## <a name="overview"></a><span data-ttu-id="37c63-104">Información general</span><span class="sxs-lookup"><span data-stu-id="37c63-104">Overview</span></span>
<span data-ttu-id="37c63-105">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, puede enviar y recibir mensajes entre BizTalk Server y Azure Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="37c63-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, you can send and receive messages between BizTalk Server and Azure Event Hubs.</span></span> 

<span data-ttu-id="37c63-106">Azure Event Hubs es una plataforma, de streaming de datos altamente escalables y puede recibir y procesar millones de eventos por segundo.</span><span class="sxs-lookup"><span data-stu-id="37c63-106">Azure Event Hubs is a highly scalable data streaming platform, and can receive and process millions of events per second.</span></span> <span data-ttu-id="37c63-107">[¿Qué es Event Hubs? ](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) proporciona más detalles.</span><span class="sxs-lookup"><span data-stu-id="37c63-107">[What is Event Hubs?](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) provides more details.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="37c63-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="37c63-108">Prerequisites</span></span>

* <span data-ttu-id="37c63-109">Crear un [centro de eventos y el espacio de nombres de Azure event hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)</span><span class="sxs-lookup"><span data-stu-id="37c63-109">Create an [Azure event hubs namespace and event hub](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)</span></span>
* <span data-ttu-id="37c63-110">Crear un [cuenta de almacenamiento de blobs de Azure con un contenedor](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)</span><span class="sxs-lookup"><span data-stu-id="37c63-110">Create an [Azure blob storage account with a container](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)</span></span>
* <span data-ttu-id="37c63-111">Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="37c63-111">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your BizTalk Server</span></span>

<span data-ttu-id="37c63-112">Ya se ha creado el centro de eventos y tiene las cadenas de conexión que necesita para enviar y recibir eventos.</span><span class="sxs-lookup"><span data-stu-id="37c63-112">Your event hub is now created, and you have the connection strings you need to send and receive events.</span></span>

## <a name="send-messages-to-event-hubs"></a><span data-ttu-id="37c63-113">Enviar mensajes a Event Hubs</span><span class="sxs-lookup"><span data-stu-id="37c63-113">Send messages to Event Hubs</span></span>

1.  <span data-ttu-id="37c63-114">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y seleccione **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="37c63-114">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="37c63-115">[Crear un puerto de envío](../core/how-to-create-a-send-port2.md) proporciona alguna orientación.</span><span class="sxs-lookup"><span data-stu-id="37c63-115">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="37c63-116">Escriba un **nombre**.</span><span class="sxs-lookup"><span data-stu-id="37c63-116">Enter a **Name**.</span></span> <span data-ttu-id="37c63-117">En **transporte**, establezca el **tipo** a **EventHub**y seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="37c63-117">In **Transport**, set the **Type** to **EventHub**, and select **Configure**.</span></span> 

3. <span data-ttu-id="37c63-118">Configurar la **cuenta de Azure** propiedades:</span><span class="sxs-lookup"><span data-stu-id="37c63-118">Configure the **Azure Account** properties:</span></span> 

    |<span data-ttu-id="37c63-119">Use</span><span class="sxs-lookup"><span data-stu-id="37c63-119">Use this</span></span>|<span data-ttu-id="37c63-120">Para</span><span class="sxs-lookup"><span data-stu-id="37c63-120">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="37c63-121">**Inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="37c63-121">**Sign-in**</span></span> | <span data-ttu-id="37c63-122">Inicie sesión en su cuenta de Azure</span><span class="sxs-lookup"><span data-stu-id="37c63-122">Sign into your Azure account</span></span> |
    | <span data-ttu-id="37c63-123">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="37c63-123">**Subscription**</span></span> | <span data-ttu-id="37c63-124">Seleccione la suscripción que tiene el espacio de nombres de Event hubs</span><span class="sxs-lookup"><span data-stu-id="37c63-124">Select the subscription that has your EventHubs namespace</span></span> |
    | <span data-ttu-id="37c63-125">**Grupo de recursos**</span><span class="sxs-lookup"><span data-stu-id="37c63-125">**Resource Group**</span></span> | <span data-ttu-id="37c63-126">Seleccione el grupo de recursos que tiene el espacio de nombres de Event hubs</span><span class="sxs-lookup"><span data-stu-id="37c63-126">Select your resource group that has your EventHubs namespace</span></span> |

4. <span data-ttu-id="37c63-127">Configurar la **extremo** propiedades:</span><span class="sxs-lookup"><span data-stu-id="37c63-127">Configure the **Endpoint** properties:</span></span> 

    |<span data-ttu-id="37c63-128">Use</span><span class="sxs-lookup"><span data-stu-id="37c63-128">Use this</span></span>|<span data-ttu-id="37c63-129">Para</span><span class="sxs-lookup"><span data-stu-id="37c63-129">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="37c63-130">**Espacio de nombres**</span><span class="sxs-lookup"><span data-stu-id="37c63-130">**Namespace**</span></span> | <span data-ttu-id="37c63-131">Seleccione el espacio de nombres de Event Hubs, que es algo parecido a sb: / /*youreventhubnamespace*.servicebus.windows.net/</span><span class="sxs-lookup"><span data-stu-id="37c63-131">Select your Event Hubs namespace, which is something like sb://*youreventhubnamespace*.servicebus.windows.net/</span></span> |
    | <span data-ttu-id="37c63-132">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="37c63-132">**Name**</span></span> | <span data-ttu-id="37c63-133">Seleccione el nombre del centro de eventos (que se creó en el espacio de nombres de Event Hubs)</span><span class="sxs-lookup"><span data-stu-id="37c63-133">Select the name of your Event Hub (which was created within your Event Hubs namespace)</span></span> |
    | <span data-ttu-id="37c63-134">**Clave de partición predeterminado**</span><span class="sxs-lookup"><span data-stu-id="37c63-134">**Default Partition Key**</span></span> | <span data-ttu-id="37c63-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="37c63-135">Optional.</span></span> <span data-ttu-id="37c63-136">[Guía de programación de Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide) proporciona más detalles sobre esta clave.</span><span class="sxs-lookup"><span data-stu-id="37c63-136">[Event Hubs programming guide](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide) provides more details on this key.</span></span> |
    | <span data-ttu-id="37c63-137">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="37c63-137">**Authentication**</span></span> | <span data-ttu-id="37c63-138">**Firma de acceso de Namespace** es el valor predeterminado y usa automáticamente el RootManageSharedAccessKey que se crea cuando se crea un espacio de nombres de Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="37c63-138">**Namespace Access Signature** is the default, and automatically uses the RootManageSharedAccessKey that's created when you create an Event Hubs namespace.</span></span><br/><br/><span data-ttu-id="37c63-139">**Firma de acceso de la entidad** es la directiva SAS puede crear en el Event Hub-nivel (no los Event Hubs espacio de nombres-).</span><span class="sxs-lookup"><span data-stu-id="37c63-139">**Entity Access Signature** is the SAS policy you can create at the Event Hub-level (not the Event Hubs namespace-level).</span></span> <br/><br/><span data-ttu-id="37c63-140">[Información general de las características de Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) se explica más información.</span><span class="sxs-lookup"><span data-stu-id="37c63-140">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) explains more.</span></span> |

    <span data-ttu-id="37c63-141">Cuando termine, las propiedades de aspecto similares al siguiente:</span><span class="sxs-lookup"><span data-stu-id="37c63-141">When finished, your properties look similar to the following:</span></span> 

    ![Propiedades de punto de conexión](../core/media/event-hub-endpoint-properties.png)


5. <span data-ttu-id="37c63-143">Opcional.</span><span class="sxs-lookup"><span data-stu-id="37c63-143">Optional.</span></span> <span data-ttu-id="37c63-144">Configurar la **mensaje** propiedades.</span><span class="sxs-lookup"><span data-stu-id="37c63-144">Configure the **Message** properties.</span></span> <span data-ttu-id="37c63-145">El **Namespace para propiedades de mensaje definidas por el usuario** valor representa un esquema de mensaje de BizTalk asignado a propiedades de mensajes de Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="37c63-145">The **Namespace for User Defined Message Properties** value represents a BizTalk message schema mapped to Event Hubs message properties.</span></span>

6. <span data-ttu-id="37c63-146">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="37c63-146">Select **Ok** to save your changes.</span></span> 


### <a name="test-your-send-port"></a><span data-ttu-id="37c63-147">Probar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="37c63-147">Test your send port</span></span>

<span data-ttu-id="37c63-148">Puede usar un simple archivo de puerto de recepción y ubicación para enviar mensajes al centro de eventos de Azure.</span><span class="sxs-lookup"><span data-stu-id="37c63-148">You can use a simple File receive port and location to send messages to your Azure Event Hub.</span></span> 

1. <span data-ttu-id="37c63-149">Crear un puerto de recepción mediante el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="37c63-149">Create a receive port using the File adapter.</span></span> <span data-ttu-id="37c63-150">Dentro de la ubicación de recepción, establezca la **carpeta recepción** a **C:\Temp\In\\**y establece la máscara de archivo en  **\*.xml**.</span><span class="sxs-lookup"><span data-stu-id="37c63-150">Within your receive location,  set the **Receive folder** to **C:\Temp\In\\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="37c63-151">En el centro de eventos propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == FileReceivePort`.</span><span class="sxs-lookup"><span data-stu-id="37c63-151">In your Event Hub send port properties, set the **Filters** to `BTS.ReceivePortName == FileReceivePort`.</span></span>
3. <span data-ttu-id="37c63-152">Pegue lo siguiente en un editor de texto y guarde el archivo como **EventHubMessage.xml**.</span><span class="sxs-lookup"><span data-stu-id="37c63-152">Paste the following into a text editor, and save the file as **EventHubMessage.xml**.</span></span> <span data-ttu-id="37c63-153">Este es el mensaje de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="37c63-153">This is your sample message.</span></span> 

    ```xml
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

4. <span data-ttu-id="37c63-154">Iniciar el archivo de ubicación de recepción y el puerto de envío del centro de eventos.</span><span class="sxs-lookup"><span data-stu-id="37c63-154">Start the File receive location and the Event Hub send port.</span></span>
5. <span data-ttu-id="37c63-155">Copia **EventHubMessage.xml** mensaje de ejemplo en la carpeta de recepción (C:\Temp\In\).</span><span class="sxs-lookup"><span data-stu-id="37c63-155">Copy **EventHubMessage.xml** sample message into the receive folder (C:\Temp\In\).</span></span> <span data-ttu-id="37c63-156">El puerto de envío envía el archivo XML al centro de eventos.</span><span class="sxs-lookup"><span data-stu-id="37c63-156">The send port sends the XML file to the event hub.</span></span>

## <a name="receive-messages-from-event-hubs"></a><span data-ttu-id="37c63-157">Recibir mensajes desde Event Hubs</span><span class="sxs-lookup"><span data-stu-id="37c63-157">Receive messages from Event Hubs</span></span>

1. <span data-ttu-id="37c63-158">En la consola de administración de BizTalk Server, haga clic en **puertos de recepción**, seleccione **New**y seleccione **unidireccional puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="37c63-158">In the BizTalk Server Administration console, right-click **Receive Ports**, select **New**, and select **One-Way receive port**.</span></span> 

    <span data-ttu-id="37c63-159">[Crear un puerto de recepción](../core/how-to-create-a-receive-port.md) proporciona alguna orientación.</span><span class="sxs-lookup"><span data-stu-id="37c63-159">[Create a receive port](../core/how-to-create-a-receive-port.md) provides some guidance.</span></span>

2. <span data-ttu-id="37c63-160">Escriba un nombre y seleccione **ubicaciones de recepción**.</span><span class="sxs-lookup"><span data-stu-id="37c63-160">Enter a name, and select **Receive Locations**.</span></span> 

3. <span data-ttu-id="37c63-161">Seleccione **New**, y **nombre** la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="37c63-161">Select **New**, and **Name** the receive location.</span></span> <span data-ttu-id="37c63-162">En **transporte**, seleccione **EventHub** desde el **tipo** lista desplegable y, a continuación, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="37c63-162">In **Transport**, select **EventHub** from the **Type** drop-down list, and then select **Configure**.</span></span> 

4. <span data-ttu-id="37c63-163">Configurar la **cuenta de Azure** propiedades:</span><span class="sxs-lookup"><span data-stu-id="37c63-163">Configure the **Azure Account** properties:</span></span> 

    |<span data-ttu-id="37c63-164">Use</span><span class="sxs-lookup"><span data-stu-id="37c63-164">Use this</span></span>|<span data-ttu-id="37c63-165">Para</span><span class="sxs-lookup"><span data-stu-id="37c63-165">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="37c63-166">**Inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="37c63-166">**Sign-in**</span></span> | <span data-ttu-id="37c63-167">Inicie sesión en su cuenta de Azure</span><span class="sxs-lookup"><span data-stu-id="37c63-167">Sign into your Azure account</span></span> |
    | <span data-ttu-id="37c63-168">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="37c63-168">**Subscription**</span></span> | <span data-ttu-id="37c63-169">Seleccione la suscripción que tiene el espacio de nombres de Event hubs</span><span class="sxs-lookup"><span data-stu-id="37c63-169">Select the subscription that has your EventHubs namespace</span></span> |
    | <span data-ttu-id="37c63-170">**Grupo de recursos**</span><span class="sxs-lookup"><span data-stu-id="37c63-170">**Resource Group**</span></span> | <span data-ttu-id="37c63-171">Seleccione el grupo de recursos que tiene el espacio de nombres de Event hubs</span><span class="sxs-lookup"><span data-stu-id="37c63-171">Select your resource group that has your EventHubs namespace</span></span> |

4. <span data-ttu-id="37c63-172">Configurar la **extremo** propiedades:</span><span class="sxs-lookup"><span data-stu-id="37c63-172">Configure the **Endpoint** properties:</span></span> 

    |<span data-ttu-id="37c63-173">Use</span><span class="sxs-lookup"><span data-stu-id="37c63-173">Use this</span></span>|<span data-ttu-id="37c63-174">Para</span><span class="sxs-lookup"><span data-stu-id="37c63-174">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="37c63-175">**Espacio de nombres**</span><span class="sxs-lookup"><span data-stu-id="37c63-175">**Namespace**</span></span> | <span data-ttu-id="37c63-176">Seleccione el espacio de nombres de Event Hubs, que es algo parecido a sb: / /*youreventhubnamespace*.servicebus.windows.net/</span><span class="sxs-lookup"><span data-stu-id="37c63-176">Select your Event Hubs namespace, which is something like sb://*youreventhubnamespace*.servicebus.windows.net/</span></span> |
    | <span data-ttu-id="37c63-177">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="37c63-177">**Name**</span></span> | <span data-ttu-id="37c63-178">Seleccione el nombre del centro de eventos (que se creó en el espacio de nombres de Event Hubs)</span><span class="sxs-lookup"><span data-stu-id="37c63-178">Select the name of your Event Hub (which was created within your Event Hubs namespace)</span></span> |
    | <span data-ttu-id="37c63-179">**Grupo de consumidores**</span><span class="sxs-lookup"><span data-stu-id="37c63-179">**Consumer Group**</span></span> | <span data-ttu-id="37c63-180">Seleccione el grupo de consumidores dentro de su centro de eventos.</span><span class="sxs-lookup"><span data-stu-id="37c63-180">Select the Consumer group within your Event Hub.</span></span> <span data-ttu-id="37c63-181">Se crea automáticamente un grupo de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37c63-181">A default group is created automatically.</span></span> <br/><br/><span data-ttu-id="37c63-182">[Información general de las características de Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) proporciona más detalles.</span><span class="sxs-lookup"><span data-stu-id="37c63-182">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) provides more details.</span></span> |
    | <span data-ttu-id="37c63-183">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="37c63-183">**Authentication**</span></span> | <span data-ttu-id="37c63-184">**Firma de acceso de Namespace** es el valor predeterminado y usa automáticamente el RootManageSharedAccessKey que se crea cuando se crea un espacio de nombres de Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="37c63-184">**Namespace Access Signature** is the default, and automatically uses the RootManageSharedAccessKey that's created when you create an Event Hubs namespace.</span></span><br/><br/><span data-ttu-id="37c63-185">**Firma de acceso de la entidad** es la directiva SAS puede crear en el Event Hub-nivel (no los Event Hubs espacio de nombres-).</span><span class="sxs-lookup"><span data-stu-id="37c63-185">**Entity Access Signature** is the SAS policy you can create at the Event Hub-level (not the Event Hubs namespace-level).</span></span> <br/><br/><span data-ttu-id="37c63-186">[Información general de las características de Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) se explica más información.</span><span class="sxs-lookup"><span data-stu-id="37c63-186">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) explains more.</span></span> |

    <span data-ttu-id="37c63-187">Cuando termine, las propiedades de aspecto similares al siguiente:</span><span class="sxs-lookup"><span data-stu-id="37c63-187">When finished, your properties look similar to the following:</span></span> 

    ![Propiedades de punto de conexión](../core/media/event-hub-endpoint-receive-properties.png)

5. <span data-ttu-id="37c63-189">Configurar la **Checkpoint** propiedades.</span><span class="sxs-lookup"><span data-stu-id="37c63-189">Configure the **Checkpoint** properties.</span></span> <span data-ttu-id="37c63-190">Este adaptador usa una cuenta de almacenamiento de blobs de Azure para leer con un punto de control de eventos confiable y reanudar a partir de un reinicio.</span><span class="sxs-lookup"><span data-stu-id="37c63-190">This adapter uses an Azure blob storage account to reliably read events using a checkpoint, and resume from a restart.</span></span> 

    <span data-ttu-id="37c63-191">**Autenticación de almacenamiento** </span><span class="sxs-lookup"><span data-stu-id="37c63-191">**Storage Authentication** </span></span>  
    <span data-ttu-id="37c63-192">Seleccione un método de autenticación.</span><span class="sxs-lookup"><span data-stu-id="37c63-192">Select an authentication method.</span></span> <span data-ttu-id="37c63-193">Normalmente, se recomienda para usar una firma de acceso compartido.</span><span class="sxs-lookup"><span data-stu-id="37c63-193">Typically, it's recommended to use a Shared Access Signature.</span></span> <span data-ttu-id="37c63-194">Los siguientes vínculos son buenos recursos para ayudarle a decidir cuál es la adecuada para su escenario:</span><span class="sxs-lookup"><span data-stu-id="37c63-194">The following links are good resources to help you decide which is right for your scenario:</span></span><br/><br/>[<span data-ttu-id="37c63-195">Acerca de las cuentas de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="37c63-195">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)<br/>[<span data-ttu-id="37c63-196">Uso de firmas de acceso compartido (SAS)</span><span class="sxs-lookup"><span data-stu-id="37c63-196">Using shared access signatures (SAS)</span></span>](https://docs.microsoft.com/azure/storage/common/storage-dotnet-shared-access-signature-part-1)

    <span data-ttu-id="37c63-197">Cuando termine, las propiedades de aspecto similares al siguiente:</span><span class="sxs-lookup"><span data-stu-id="37c63-197">When finished, your properties look similar to the following:</span></span> 

    ![Propiedades de punto de control](../core/media/event-hub-receive-checkpoint.png)

6. <span data-ttu-id="37c63-199">Configurar la **mensaje** propiedades:</span><span class="sxs-lookup"><span data-stu-id="37c63-199">Configure the **Message** properties:</span></span> 

    |<span data-ttu-id="37c63-200">Use</span><span class="sxs-lookup"><span data-stu-id="37c63-200">Use this</span></span>|<span data-ttu-id="37c63-201">Para</span><span class="sxs-lookup"><span data-stu-id="37c63-201">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="37c63-202">**Namespace para el usuario define las propiedades de mensaje**</span><span class="sxs-lookup"><span data-stu-id="37c63-202">**Namespace for User Defined Message Properties**</span></span> | <span data-ttu-id="37c63-203">`http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User` es el esquema predeterminado, pero puede escribir otro esquema.</span><span class="sxs-lookup"><span data-stu-id="37c63-203">`http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User` is the default schema, but you can enter another schema.</span></span> <span data-ttu-id="37c63-204">Este valor representa un esquema de mensaje de BizTalk asignado a propiedades de mensajes de Event Hubs.</span><span class="sxs-lookup"><span data-stu-id="37c63-204">This value represents a BizTalk message schema mapped to Event Hubs message properties.</span></span> |
    | <span data-ttu-id="37c63-205">**Promocionar propiedades definidas por el usuario**</span><span class="sxs-lookup"><span data-stu-id="37c63-205">**Promote user defined properties**</span></span> | <span data-ttu-id="37c63-206">Opcional.</span><span class="sxs-lookup"><span data-stu-id="37c63-206">Optional.</span></span> <span data-ttu-id="37c63-207">Si lo prefiere puede promocionar estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="37c63-207">You can promote these properties if you prefer.</span></span> <br/><br/><span data-ttu-id="37c63-208">**NOTA**</span><span class="sxs-lookup"><span data-stu-id="37c63-208">**NOTE**</span></span><br/><span data-ttu-id="37c63-209">Las propiedades que deben promocionarse deben tener un esquema porperty implementado *antes* recibir eventos.</span><span class="sxs-lookup"><span data-stu-id="37c63-209">The properties that need to be promoted should have a porperty schema deployed *before* receiving events.</span></span>|

7. <span data-ttu-id="37c63-210">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="37c63-210">Select **Ok** to save your changes.</span></span> 

### <a name="test-your-receive-settings"></a><span data-ttu-id="37c63-211">Prueba la configuración de recepción</span><span class="sxs-lookup"><span data-stu-id="37c63-211">Test your receive settings</span></span>

<span data-ttu-id="37c63-212">Puede usar un puerto de envío de archivos simple para recibir mensajes desde el centro de eventos de Azure.</span><span class="sxs-lookup"><span data-stu-id="37c63-212">You can use a simple File send port to receive messages from your Azure Event Hub.</span></span> 

1. <span data-ttu-id="37c63-213">Crear un puerto de envío mediante el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="37c63-213">Create a send port using the File adapter.</span></span> <span data-ttu-id="37c63-214">Dentro de las propiedades de puerto de envío, establezca el **carpeta de destino** a **C:\Temp\Out\\**y establezca el y **nombre de archivo** a **%MessageID%.xml** .</span><span class="sxs-lookup"><span data-stu-id="37c63-214">Within your send port properties, set the **Destination folder** to **C:\Temp\Out\\**, and set the and **File name** to **%MessageID%.xml**.</span></span>
2. <span data-ttu-id="37c63-215">En el archivo de propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == EHReceivePort`.</span><span class="sxs-lookup"><span data-stu-id="37c63-215">In your File send port properties, set the **Filters** to  `BTS.ReceivePortName == EHReceivePort`.</span></span>
3. <span data-ttu-id="37c63-216">El centro de eventos de inicio ubicación de recepción y el puerto de envío de archivo.</span><span class="sxs-lookup"><span data-stu-id="37c63-216">Start the Event Hub receive location and the File send port.</span></span>
4. <span data-ttu-id="37c63-217">Buscar mensajes en la carpeta de destino (c:\temp\out).</span><span class="sxs-lookup"><span data-stu-id="37c63-217">Look for messages in the destination folder (c:\temp\out).</span></span>

## <a name="do-more"></a><span data-ttu-id="37c63-218">Hacer más cosas</span><span class="sxs-lookup"><span data-stu-id="37c63-218">Do more</span></span>
<span data-ttu-id="37c63-219">Event Hubs se considera la "puerta principal" para muchos otros servicios de Azure, incluido Azure Data Lake, HD Insight y mucho más.</span><span class="sxs-lookup"><span data-stu-id="37c63-219">Event Hubs is considered the "front door" to a lot of other Azure services, including Azure Data Lake, HD Insight, and more.</span></span> <span data-ttu-id="37c63-220">Se ha diseñado para procesar un lote de mensajes y procesarlos rápida.</span><span class="sxs-lookup"><span data-stu-id="37c63-220">It's designed to process a lot of messages, and process them fast.</span></span> <span data-ttu-id="37c63-221">Más información acerca de Event Hubs y sus características:</span><span class="sxs-lookup"><span data-stu-id="37c63-221">Read more about Event Hubs, and its features:</span></span> 

[<span data-ttu-id="37c63-222">Información general de las características de Event Hubs</span><span class="sxs-lookup"><span data-stu-id="37c63-222">Event Hubs features overview</span></span>](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)  
[<span data-ttu-id="37c63-223">¿Qué es Event Hubs?</span><span class="sxs-lookup"><span data-stu-id="37c63-223">What is Event Hubs?</span></span>](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
