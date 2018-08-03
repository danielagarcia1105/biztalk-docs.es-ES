---
title: Usar el adaptador de contacto de Outlook de Office 365 | Microsoft Docs
description: Enviar mensajes mediante el adaptador de contacto de Outlook de Office 365 en BizTalk Server. Para ello, cree un puerto de envío mediante el adaptador de Outlook y usar un mensaje XML de ejemplo para crear un contacto en la cuenta de Office 365 Outlook.
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
ms.openlocfilehash: 3185e080be7a4222ac51072506eb9657eb7b1e1b
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946234"
---
# <a name="create-a-contact-using-the-office-365-outlook-contact-adapter---biztalk-server"></a><span data-ttu-id="a9c6c-104">Crear un contacto mediante el adaptador de contacto de Office 365 Outlook - servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a9c6c-104">Create a contact using the Office 365 Outlook Contact adapter - BizTalk Server</span></span>

<span data-ttu-id="a9c6c-105">Utilice el adaptador de contacto de Outlook de Office 365 en BizTalk Server para crear contactos en Office 365 Outlook.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-105">Use the Office 365 Outlook Contact adapter in BizTalk Server to create contacts in your Office 365 Outlook.</span></span>

## <a name="create-a-contact-using-a-send-port"></a><span data-ttu-id="a9c6c-106">Crear un contacto mediante un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="a9c6c-106">Create a contact using a send port</span></span>

1. <span data-ttu-id="a9c6c-107">En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y seleccione **puerto de envío unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-107">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="a9c6c-108">[Crear un puerto de envío](../core/how-to-create-a-send-port2.md) proporciona alguna orientación.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-108">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="a9c6c-109">Escriba un **nombre**.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-109">Enter a **Name**.</span></span> <span data-ttu-id="a9c6c-110">En **transporte**, establezca el **tipo** a **contacto de Outlook de Office 365**y seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-110">In **Transport**, set the **Type** to **Office 365 Outlook Contact**, and select **Configure**.</span></span>

3. <span data-ttu-id="a9c6c-111">Seleccione **iniciar sesión...** e inicie sesión en su cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-111">Select **Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="a9c6c-112">La cuenta está rellena automáticamente con su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-112">The account is auto-populated with your email address.</span></span>

4. <span data-ttu-id="a9c6c-113">Permitir la aprobación de BizTalk Server para obtener permiso para tener acceso:</span><span class="sxs-lookup"><span data-stu-id="a9c6c-113">Allow BizTalk Server approval for permission to access:</span></span>

    ![Permisos de contacto de Office 365](../core/media/office365-contact-permissions.png)

5. <span data-ttu-id="a9c6c-115">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-115">Select **Ok** to save your changes.</span></span>

### <a name="test-the-send-port"></a><span data-ttu-id="a9c6c-116">Probar el puerto de envío</span><span class="sxs-lookup"><span data-stu-id="a9c6c-116">Test the send port</span></span>

<span data-ttu-id="a9c6c-117">Puede usar un simple archivo de puerto de recepción y ubicación para crear un evento en el adaptador de contacto de Outlook de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-117">You can use a simple File receive port and location to create an event on your Office 365 Outlook Contact adapter.</span></span>

1. <span data-ttu-id="a9c6c-118">Crear un puerto de recepción mediante el adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-118">Create a receive port using the File adapter.</span></span> <span data-ttu-id="a9c6c-119">Dentro de la ubicación de recepción, establezca la **carpeta recepción** a \**C:\Temp\In\** y establece la máscara de archivo en  **\*.xml**.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-119">Within your receive location,  set the **Receive folder** to \**C:\Temp\In\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="a9c6c-120">En el adaptador de contacto de Outlook de Office 365 propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == <Receive Port Name>`.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-120">In your Office 365 Outlook Contact adapter send port properties, set the **Filters** to `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="a9c6c-121">Pegue lo siguiente en un editor de texto y guarde el archivo como **Office365Contact.xml**.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-121">Paste the following into a text editor, and save the file as **Office365Contact.xml**.</span></span> <span data-ttu-id="a9c6c-122">Este es el mensaje de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-122">This is your sample message.</span></span>

    ```xml
        <ns0:Contact xmlns:ns0="http://schemas.microsoft.com/BizTalk/Office365OutlookContacts/Send">
            <categories>categories_0</categories>
            <categories>categories_1</categories>
            <categories>categories_2</categories>
            <birthday>1999-05-31T13:20:00.000-05:00</birthday>
            <fileAs>fileAs_0</fileAs>
            <displayName>displayName_0</displayName>
            <givenName>givenName_0</givenName>
            <initials>initials_0</initials>
            <middleName>middleName_0</middleName>
            <nickName>nickName_0</nickName>
            <surname>surname_0</surname>
            <title>title_0</title>
            <yomiGivenName>yomiGivenName_0</yomiGivenName>
            <yomiSurname>yomiSurname_0</yomiSurname>
            <yomiCompanyName>yomiCompanyName_0</yomiCompanyName>
            <generation>generation_0</generation>
            <jobTitle>jobTitle_0</jobTitle>
            <companyName>companyName_0</companyName>
            <department>department_0</department>
            <officeLocation>officeLocation_0</officeLocation>
            <profession>profession_0</profession>
            <businessHomePage>businessHomePage_0</businessHomePage>
            <assistantName>assistantName_0</assistantName>
            <manager>manager_0</manager>
            <homePhones>homePhones_0</homePhones>
            <homePhones>homePhones_1</homePhones>
            <mobilePhone>mobilePhone_0</mobilePhone>
            <businessPhones>businessPhones_0</businessPhones>
            <businessPhones>businessPhones_1</businessPhones>
            <spouseName>spouseName_0</spouseName>
            <personalNotes>personalNotes_0</personalNotes>
            <children>children_0</children>
            <children>children_1</children>
            <children>children_2</children>
            <emailAddresses>
                <name>name_0</name>
                <address>address_0</address>
            </emailAddresses>
            <emailAddresses>
                <name>name_0</name>
                <address>address_0</address>
            </emailAddresses>
            <homeAddress>
                <city>city_0</city>
                <countryOrRegion>countryOrRegion_0</countryOrRegion>
                <postalCode>10000</postalCode>
                <state>state_0</state>
                <street>street_0</street>
            </homeAddress>
            <businessAddress>
                <city>city_0</city>
                <countryOrRegion>countryOrRegion_0</countryOrRegion>
                <postalCode>11111</postalCode>
                <state>state_0</state>
                <street>street_0</street>
            </businessAddress>
            <otherAddress>
                <city>city_0</city>
                <countryOrRegion>countryOrRegion_0</countryOrRegion>
                <postalCode>21222</postalCode>
                <state>state_0</state>
                <street>street_0</street>
            </otherAddress>
        </ns0:Contact>
    ```
    <span data-ttu-id="a9c6c-123">**El esquema XML se proporciona como parte del SDK de dentro de < instalación de BizTalk Folder\SDK\Schemas >**</span><span class="sxs-lookup"><span data-stu-id="a9c6c-123">**The XML schema is provided as part of the SDK inside < BizTalk Installation Folder\SDK\Schemas >**</span></span>

4. <span data-ttu-id="a9c6c-124">Iniciar el archivo de ubicación de recepción y el puerto de envío del adaptador de contacto de Outlook de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-124">Start the File receive location and the Office 365 Outlook Contact adapter send port.</span></span>
5. <span data-ttu-id="a9c6c-125">Copia **Office365Contact.xml** mensaje de ejemplo en la carpeta de recepción (C:\Temp\In\).</span><span class="sxs-lookup"><span data-stu-id="a9c6c-125">Copy **Office365Contact.xml** sample message into the receive folder (C:\Temp\In\).</span></span> <span data-ttu-id="a9c6c-126">El puerto de envío crea un contacto en su cuenta de Office 365 Outlook basado en el documento xml.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-126">The send port creates a contact in your Office 365 Outlook account based on the xml.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a9c6c-127">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a9c6c-127">Next steps</span></span>
<span data-ttu-id="a9c6c-128">Ver todos los [adaptadores de Office 365](office365-adapters.md), o instalar [característica Pack 3](https://aka.ms/bts2016fp3).</span><span class="sxs-lookup"><span data-stu-id="a9c6c-128">See all the [Office 365 adapters](office365-adapters.md), or install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>