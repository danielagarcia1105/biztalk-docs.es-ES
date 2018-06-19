---
title: 'Cómo: crear un itinerario para dinámicamente enrutar un mensaje a una dirección de correo electrónico mediante una consulta LDAP | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d9929dd-5e45-4b0d-90df-52a35e68b0ba
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 751eaf381b762372652bb77ddf6f00ffe43971c2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010117"
---
# <a name="how-to-create-an-itinerary-to-dynamically-route-a-message-to-an-email-address-using-an-ldap-query"></a>Cómo: crear un itinerario para dinámicamente enrutar un mensaje a una dirección de correo electrónico mediante una consulta LDAP
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo crear un itinerario que consulta una dirección de correo electrónico a través de LDAP (Protocolo ligero de acceso a directorios) y, a continuación, envía un mensaje de correo electrónico al extremo resuelto mediante el adaptador de SMTP del servidor de BizTalk.  
  
 En este tema "Cómo...", se realizarán los pasos siguientes:  
  
-   Crear una lista de distribución itinerario para dirigir de manera dinámica un mensaje mediante una consulta LDAP.  
  
-   Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
 El equipo en el que se completará esta sección debe tener el servicio de directorio de Microsoft Active Directory configurado y en ejecución (no es necesario que el equipo es el controlador de dominio, pero debe estar conectado al dominio). Además, debe ser un servidor SMTP configurado y en ejecución; Para probar el resultado de este tema "Cómo...", debe tener un cliente con el que se va a comprobar el correo electrónico enviado por ESB.  
  
 Las instrucciones de esta sección presupone una organización denominada Global Bank, con un dominio de globalbank.com, con un Active Directory unidad organizativa denominada a Employees que contiene un usuario denominado a John Evans con una dirección de correo electrónico válida en su perfil (por ejemplo, johne@globalbank.com). No es necesario replicar estos factores del entorno; Sin embargo, para fines de volver a crear esta implementación en su entorno, tenga en cuenta estos factores y realice las sustituciones según sea necesario.  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model"></a>Para crear un modelo de lenguaje de específico de dominio (DSL) itinerarios de ESB  
  
1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, escriba **LdapResolution** en el **nombre** cuadro y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>Para configurar las propiedades de la itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **LdapResolution.itinerary**. En el **LdapResolution** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.  
  
    2.  En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).  
  
    3.  En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\LdapResolution** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.  
  
        > [!NOTE]
        >  Este paso permite exportar el itinerario como XML en una ubicación de archivo local. Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB. Complete este proceso más adelante en este tema "Cómo...".  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de la itinerario  
  
1.  En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteMessageEmail**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.  
  
        > [!NOTE]
        >  Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería). Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.  
  
    3.  En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.  
  
3.  Haga clic en el **resolución** colección de la **RouteMessageEmail** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **LdapResolver**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **LDAP resolución extensión**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **SMTP**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **{correo}**  
  
    5.  Haga clic en el **SearchRoot** propiedad y, a continuación, escriba **ou = empleados, dc = globalbank, dc = com**  
  
        > [!NOTE]
        >  Si no ha configurado el entorno según las especificaciones de la sección "Requisitos previos", reemplace los valores de la propiedad anterior con los que son adecuados para su entorno.  
  
    6.  Haga clic en el **filtro** propiedad y, a continuación, cambie el valor a **(&(objectClass=User) (&#124;(givenName=john)))**  
  
        > [!NOTE]
        >  Escriba el valor anterior para reemplazar el texto existente.  
  
    7.  En el **ThrowErrorIfNotFound** la lista desplegable, haga clic en **True**.  
  
4.  En la ventana Propiedades, haga clic en el **configuración de extremo** propiedad y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
    1.  En el **configuración de extremo** cuadro de diálogo, haga clic en el **EmailBodyText** propiedad y, a continuación, escriba **orden está listo para ser procesado**.  
  
    2.  Haga clic en el **de** propiedad y, a continuación, escriba  **orders@globalbank.com** .  
  
    3.  Haga clic en el **MessagePartsAttachment** propiedad y, a continuación, escriba **2**.  
  
    4.  Haga clic en el **asunto** propiedad y, a continuación, escriba **orden para {givenName}**.  
  
    5.  Configurar la **SMTPAuthentication, SMTPHost, nombre de usuario,** y **contraseña** propiedades mediante la información de conexión para su entorno local.  
  
    6.  Haga clic en **Aceptar** para cerrar el **configuración de extremo** cuadro de diálogo.  
  
5.  Haga clic en el **LdapResolver** resolución y, a continuación, haga clic en **configuración de la resolución de prueba**.  
  
6.  En la ventana de salida, compruebe el sujeto en el que se resuelven **configuración de extremo** valor es **orden John**y, a continuación, compruebe que el resuelto **transporte ubicación** es el asociado a la cuenta del usuario en Active Directory de dirección de correo electrónico (por ejemplo, johne@globalbank.com).  
  
7.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteMessageEmail** elemento del modelo.  
  
8.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **RouteMessageEmail** elemento del modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **EmailNAOrderDoc**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
9. En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **RouteMessageEmail** elemento del modelo y la **EmailNAOrderDoc**elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.  
  
    3.  En el **fuera de rampa** lista desplegable lista, expanda **EmailNAOrderDoc**y, a continuación, haga clic en **controladores de envío**.  
  
10. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **RouteMessageEmail** elemento de modelo para el **SendPortFilter** elemento del modelo.  
  
11. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **EmailNAOrderDoc** elemento del modelo.  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>Para exportar el modelo para su uso con el cliente de prueba de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **LdapResolution** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  La versión XML del itinerario se abre en Visual Studio.  
  
2.  Guarde todos los artefactos de proyecto.  
  
3.  En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (LdapResolution.xml).  
  
#### <a name="to-test-the-itinerary"></a>Para probar el itinerario  
  
1.  Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).  
  
2.  En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.  
  
3.  En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries. Seleccione **LdapResolution.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.  
  
4.  Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.  
  
5.  En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.  
  
6.  En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos. Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.  
  
7.  Haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.  
  
8.  Abra Microsoft Outlook Express (o el cliente de correo electrónico de su elección) y comprobar la entrega del mensaje al correo electrónico de John Evans.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Uso de resolución y enrutamiento dinámicos](../esb-toolkit/using-dynamic-resolution-and-routing.md)