---
title: 'Tutorial 5: Invocar una interfaz REST con BizTalk Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73871ca3-abd0-45ae-b379-6df76a967a80
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d45daa5f567863fd3531edb1f951ac673628fd6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967573"
---
# <a name="tutorial-5-invoking-a-rest-interface-using-biztalk-server"></a>Tutorial 5: Invocar una interfaz REST con BizTalk Server
En esta sección se proporciona un tutorial paso a paso sobre cómo invocar un extremo REST mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En este tutorial invocará un extremo REST disponible en [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace que devuelve los retrasos de vuelos de las compañías aéreas de EE. UU. El tutorial utiliza el nuevo **WCF-WebHttp** adaptador introducidas en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para invocar el extremo REST.  
  
##  <a name="BKMK_Scenario"></a> Escenario usado en este Tutorial  
 [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace proporciona la siguiente dirección URL de recurso REST para recuperar retrasos de vuelos de compañías aéreas estadounidenses:  
  
```  
https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/On_Time_Performance  
```  
  
 Si escribe esta dirección URL en la barra de direcciones de un explorador web, se le pedirán credenciales para obtener acceso al recurso. Una vez que haya iniciado sesión en el [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913), puede obtener las credenciales de la **mi cuenta** ficha de la página web. Las credenciales se muestran con el **Id. de cliente** (nombre de usuario) y **clave de cuenta principal** etiquetas (contraseña).  
  
 En este tutorial, usará la dirección URL de recursos y las credenciales para configurar un bidireccional **WCF-WebHttp** puerto de envío. La canalización de recepción del puerto de envío bidireccional recibe el mensaje de respuesta con los detalles del vuelo y publica el mensaje en la base de datos de cuadro de mensajes [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Configurará un puerto de envío de archivos que se suscriba a todos los mensajes publicados por el puerto de envío WCF-WebHttp. El puerto de envío de archivos consume el mensaje de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y lo copia en una ubicación de archivo.  
  
 En un escenario empresarial en tiempo real, el puerto de envío WCF-WebHttp se puede activar asociándolo a un proceso empresarial mayor, como una ubicación de recepción que recibe un mensaje de una aplicación empresarial. No obstante, en este tutorial, dado que el objetivo es demostrar cómo invocar una interfaz REST, puede usar una ubicación de archivo simple que reciba un mensaje ficticio para activar el puerto de envío.  
  
 De este modo, para resumir, debe realizar los siguientes pasos para configurar esta solución:  
  
1.  Configure una ubicación de recepción de FILE para seleccionar un mensaje de solicitud ficticio.  
  
2.  Configure un puerto de envío de WCF-WebHttp bidireccional para invocar la dirección URL del recurso REST y recibir una respuesta.  
  
3.  Configurar un puerto de envío de archivos unidireccional para consumir el mensaje de respuesta con los detalles de los vuelos y copiarlo en una ubicación de archivo.  
  
## <a name="set-up-your-includewinazureincludeswinazure-mdmd-marketplace-account"></a>Configurar la cuenta de [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace  
 Para acceder a los datos de retrasos de vuelos que se exponen a través del extremo REST, deberá suscribirse a la fuente de datos de ejemplo US Air Carrier Flight Delays. Para ello, realice los pasos siguientes:  
  
#### <a name="to-subscribe-to-the-data-feed"></a>Procedimiento para suscribirse a la fuente de datos  
  
1. Inicie sesión en [!INCLUDE[winazure](../includes/winazure-md.md)] Marketplace mediante su cuenta Microsoft.  
  
2. En el **datos** pestaña, busque y haga clic en el **US Air Carrier Flight Delays** service.  
  
3. En la página de servicio de datos, haga clic en **Sign Up**. En la página de suscripción, acepte los términos del contrato y, a continuación, haga clic en **registrarse** nuevo.  
  
4. En el **mi cuenta** pestaña, recuperar las credenciales para acceder al servicio de datos. Las credenciales se muestran con el **Id. de cliente** (nombre de usuario) y **clave de cuenta principal** etiquetas (contraseña). Necesitará estas credenciales al configurar el **WCF-WebHttp** puerto de envío.  
  
## <a name="set-up-your-computer"></a>Configurar el PC  
 Para configurar el escenario usado en este tutorial, debe tener [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalado y configurado en su PC. Si desea aprovisionar un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo en una VM de Windows Azure, siga las instrucciones de [configurar BizTalk Server en una máquina virtual de Azure](http://msdn.microsoft.com/library/azure/jj248689.aspx).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Configurar una ubicación de recepción de archivos](../core/step-1-configure-a-file-receive-location.md)  
  
-   [Paso 2: Configurar un puerto de envío WCF-WebHttp bidireccional](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md)  
  
-   [Paso 3: Configurar un puerto de envío de archivos unidireccional](../core/step-3-configure-a-one-way-file-send-port.md)  
  
-   [Paso 4: Probar la solución](../core/step-4-test-the-solution.md)