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
ms.openlocfilehash: da423cba141dffa8779c97cef521ade730a3c846
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752684"
---
# <a name="create-a-contact-using-the-office-365-outlook-contact-adapter---biztalk-server"></a>Crear un contacto mediante el adaptador de contacto de Office 365 Outlook - servidor BizTalk Server

Utilice el adaptador de contacto de Outlook de Office 365 en BizTalk Server para crear contactos en Office 365 Outlook.

## <a name="create-a-contact-using-a-send-port"></a>Crear un contacto mediante un puerto de envío

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y seleccione **puerto de envío unidireccional estático**.

    [Crear un puerto de envío](../core/how-to-create-a-send-port2.md) proporciona alguna orientación.

2. Escriba un **nombre**. En **transporte**, establezca el **tipo** a **contacto de Outlook de Office 365**y seleccione **configurar**.

3. Seleccione **iniciar sesión...** e inicie sesión en su cuenta de Office 365. La cuenta está rellena automáticamente con su dirección de correo electrónico.

4. Permitir la aprobación de BizTalk Server para obtener permiso para tener acceso:

    ![Permisos de contacto de Office 365](../core/media/office365-contact-permissions.png)

5. Seleccione **Aceptar** para guardar los cambios.

### <a name="test-the-send-port"></a>Probar el puerto de envío

Puede usar un simple archivo de puerto de recepción y ubicación para crear un evento en el adaptador de contacto de Outlook de Office 365.

1. Crear un puerto de recepción mediante el adaptador de archivo. Dentro de la ubicación de recepción, establezca la **carpeta recepción** a **C:\\Temp\\en\\** y establece la máscara de archivo en **\*.xml**.
2. En el adaptador de contacto de Outlook de Office 365 propiedades de puerto de envío, establezca el **filtros** a `BTS.ReceivePortName == <Receive Port Name>`.
3. Pegue lo siguiente en un editor de texto y guarde el archivo como **Office365Contact.xml**. Este es el mensaje de ejemplo.

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
    **El esquema XML se proporciona como parte SDK dentro de < carpeta de instalación de BizTalk\\SDK\\esquemas >**

4. Iniciar el archivo de ubicación de recepción y el puerto de envío del adaptador de contacto de Outlook de Office 365.
5. Copia **Office365Contact.xml** mensaje de ejemplo en la carpeta de recepción (C:\\Temp\\en\\). El puerto de envío crea un contacto en su cuenta de Office 365 Outlook basado en el documento xml.

## <a name="next-steps"></a>Pasos siguientes
Ver todos los [adaptadores de Office 365](office365-adapters.md), o instalar [característica Pack 3](https://aka.ms/bts2016fp3).