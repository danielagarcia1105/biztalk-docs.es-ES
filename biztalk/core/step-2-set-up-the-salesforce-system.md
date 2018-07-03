---
title: 'Paso 2: Configurar el sistema de Salesforce | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a4b09fb-70a7-4eec-b1e3-f05de0e84df1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 772c18f87351d17b726ad498122715659dca79bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986533"
---
# <a name="step-2-set-up-the-salesforce-system"></a>Paso 2: Configurar el sistema de Salesforce
En este paso, configurará Salesforce para enviar notificaciones cuando se cierre una oportunidad satisfactoriamente. Para poder enviar notificaciones, debe realizar los siguientes pasos:  
  
-   Crear una cuenta en Salesforce Una cuenta representa un cliente para Northwind.  
  
-   Crear una oportunidad para la cuenta. Una oportunidad representa una oportunidad de venta potencial con el cliente. Como parte de la oportunidad, agregará también los detalles de productos en los que el cliente está interesado.  
  
-   Crear un flujo de trabajo en Salesforce.  
  
-   Crear una definición de aplicación conectada a Salesforce.  
  
> [!NOTE]
>  En este tema se asume que ya tiene una cuenta de desarrollador de Salesforce. Para crear una nueva cuenta de desarrollador en Salesforce, vaya a [ http://go.microsoft.com/fwlink/?LinkId=296424 ](http://go.microsoft.com/fwlink/?LinkId=296424).  
  
### <a name="to-create-an-account-in-salesforce"></a>Para crear una cuenta en Salesforce  
  
1.  Inicie sesión en el portal Salesforce.com con sus credenciales de desarrollador.  
  
2.  En el portal, haga clic en el **cuentas** pestaña y, a continuación, haga clic en **New**.  
  
3.  En el **nueva cuenta** página, proporcione valores para los distintos campos. Especificar un valor para **nombreCuenta** es obligatorio. Para este tutorial, especifique el nombre de cuenta como `Customer1`.  
  
4.  Haga clic en **Guardar**.  
  
### <a name="to-create-an-opportunity-for-the-customer"></a>Para crear una oportunidad para el cliente  
  
1. En el portal Salesforce.com, haga clic en el **oportunidades** ficha.  
  
2. En el **oportunidades recientes** sección, haga clic en **New**.  
  
3. En la página Oportunidad nueva, especifique los siguientes valores:  
  
   1. Especifique un **nombre de la oportunidad**, por ejemplo, `Opportunity with Customer 1`.  
  
   2. Especifique el **nombre de cuenta**. Este nombre representa la cuenta con la que está asociada esta oportunidad. Para este tutorial, establezca la cuenta en `Customer1`. Ha creado esta cuenta en el procedimiento anterior.  
  
   3. Especifique un **fecha de cierre**. Esta es la fecha en la que debería cerrarse la oportunidad.  
  
   4. Especifique un **fase**. Este valor denota la etapa actual para la oportunidad. Para empezar, puede establecer la oportunidad en cualquier valor, por ejemplo, **necesita análisis**.  
  
       ![Crear una oportunidad en Salesforce](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")  
  
      > [!NOTE]
      >  Asegúrese de que no establece la etapa en **Closed Won** para empezar. Para el escenario de este tutorial, cada vez que se establece la etapa **Closed Won** se envía una notificación a un extremo de retransmisión en [!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]. No hemos configurado esa parte de la solución aún, por lo que no debería establecer la etapa en **Closed Won**.  
  
   5. Especifique valores para otros campos opcionales y, a continuación, haga clic en **guardar**.  
  
   6. En la página oportunidad para Customer1, en el **productos** sección, haga clic en **agregar producto**.  
  
   7. En la lista de productos, seleccione los productos que el cliente está interesado y, a continuación, haga clic en **seleccione**.  
  
   8. Para cada producto seleccionado, especifique una cantidad que el cliente desea y, a continuación, haga clic en **guardar**.  
  
       ![Agregar productos a una oportunidad](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")  
  
## <a name="create-a-salesforce-workflow"></a>Crear un flujo de trabajo en Salesforce  
 En este paso, crearemos un flujo de trabajo para enviar una notificación cada vez que se cierre una oportunidad satisfactoriamente. La notificación se encuentra en el formulario de un mensaje SOAP y se envía a un extremo de retransmisión hospedado en [!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)].  
  
#### <a name="to-create-a-workflow-for-opportunities"></a>Para crear un flujo de trabajo para oportunidades  
  
1. En el portal de Salesforce, haga clic en el nombre de inicio de sesión en la esquina superior derecha de la página y, a continuación, haga clic en **instalación**.  
  
2. En el panel izquierdo, bajo **el programa de instalación de la aplicación**, expanda **crear**, expanda **flujo de trabajo y aprobaciones**y, a continuación, haga clic en **reglas de flujo de trabajo**.  
  
   > [!NOTE]
   >  Si abre la página Reglas de flujo de trabajo por primera vez, se le mostrará información para que comprenda cómo funcionan los flujos de trabajo en Salesforce. Lea la información y, a continuación, haga clic en **continuar**.  
  
3. En el **todas las reglas de flujo de trabajo** página, haga clic en **nueva regla**.  
  
4. Desde el **Seleccionar objeto** lista, haga clic en **oportunidad**y, a continuación, haga clic en **siguiente**.  
  
5. En la página siguiente, especifique estos datos:  
  
   1.  Establecer el **nombre de regla** como `Closed Opportunity`.  
  
   2.  Establecer el **criterios de evaluación** como **creado y cada vez se edita para cumplir los criterios**.  
  
   3.  Para el **criterios de regla**, establezca ejecutar la regla cuando el **se cumplen los criterios**.  
  
   4.  Establecer **campo** a **oportunidad: fase**, **operador** a **es igual a**, y **valor** a `Closed Won`.  
  
        ![Crear un flujo de trabajo de Salesforce](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")  
  
   5.  Haga clic en **guardar y siguiente**.  
  
6. Defina la acción del flujo de trabajo para la regla nueva:  
  
   1. En el **especificar acciones de flujo de trabajo** página, haga clic en **Agregar acción de flujo de trabajo** botón y, a continuación, haga clic en **nuevo mensaje saliente**.  
  
   2. Establecer el **nombre** y **nombre único** campos a `NewOp1`.  
  
   3. Especifique una descripción, como por ejemplo, el `Message sent when an opportunity is successfully closed`.  
  
   4. Especifique el **dirección URL del extremo** como `https://btssalesforce.servicebus.windows.net/notifications/opportunity`.  
  
       En este caso, **btssalesforce** es su [!INCLUDE[sb](../includes/sb-md.md)] espacio de nombres que creó en los pasos anteriores. **/Notifications/opportunity/** representa la transmisión que creamos en pasos posteriores de este tutorial.  
  
      > [!NOTE]
      >  Debe especificar el espacio de nombres de [!INCLUDE[sb](../includes/sb-md.md)] que creó anteriormente.  
  
   5. Asegúrese de que el **componente protegido** casilla está desactivada y el **enviar Id. de sesión** está activada la casilla de verificación.  
  
   6. Para **campos de oportunidad para enviar** seleccione los campos relevantes en el **campos disponibles** lista y, a continuación, haga clic en el **agregar** botón.  
  
   7. Haga clic en **guardar** y, a continuación, haga clic en **realiza**.  
  
   8. En el panel izquierdo, bajo **el programa de instalación de la aplicación**, expanda **crear**, expanda **flujo de trabajo y aprobaciones**y, a continuación, haga clic en **reglas de flujo de trabajo**. Compruebe que la **oportunidad cerrada** regla aparece allí. En el **acción** columna para el **oportunidad cerrada** de reglas, haga clic en **Activate** para activar la regla.  
  
## <a name="create-a-salesforce-connected-application"></a>Crear una aplicación conectada a Salesforce  
 Al crear una definición de aplicación conectada, se genera un conjunto de claves necesarias para solicitar tokens OAuth para obtener acceso y conectarse a Salesforce. En los últimos pasos de este tutorial, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] será la aplicación conectada que consulta a Salesforce usando la definición de aplicación conectada.  
  
#### <a name="to-create-a-connected-application-for-salesforce"></a>Para crear una aplicación conectada para Salesforce  
  
1. En el portal de Salesforce, haga clic en el nombre de inicio de sesión en la esquina superior derecha de la página y, a continuación, haga clic en **instalación**.  
  
2. En el panel izquierdo, bajo **el programa de instalación de la aplicación**, expanda **crear**y, a continuación, expanda **aplicaciones**. En el **aplicaciones** página, en el **aplicaciones conectadas a** sección, haga clic en **New**.  
  
3. En el **nueva aplicación de conexión** página, especifique lo siguiente:  
  
   1. Para **nombre de aplicación conectada**, especifique `BizTalk_Salesforce`.  
  
   2. Para **nombre del desarrollador**, especifique el registro en el nombre.  
  
   3. Para **correo electrónico de contacto**, especifique su correo electrónico.  
  
   4. Para **dirección URL de devolución de llamada**, especifique una dirección URL válida.  
  
      > [!NOTE]
      >  Debido al modo en que nos autenticamos en Salesforce en este escenario, el valor que especifique aquí no se usa.  
  
   5. En **ámbitos de OAuth disponibles**, seleccione **acceso completo**, **realizar solicitudes en su nombre en cualquier momento**, y **acceso y administrar los datos**y, a continuación, haga clic en el **agregar** botón para mover estos elementos a la **ámbitos de OAuth seleccionados**.  
  
   6. Haga clic en **Guardar**. La página que aparece contiene información sobre la **clave de consumidor** y **secreto de consumidor**. Debe tomar nota de estos valores. Los necesitará para conectarse a Salesforce desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
       ![Las claves de acceso de Salesforce](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")  
  
4. Finalmente, genere un token de seguridad necesario para conectarse a Salesforce desde ubicaciones de red desconocidas.  
  
   1.  En el panel izquierdo del portal de Salesforce, en **configuración Personal**, expanda **información Personal**y, a continuación, haga clic en **restablecer mi Token de seguridad**.  
  
   2.  Lea la advertencia y, a continuación, haga clic en **restablecer Token de seguridad**.  
  
   3.  Debería recibir el token de seguridad en la dirección de correo electrónico que especificó cuando creó su cuenta de Salesforce.  
  
## <a name="see-also"></a>Vea también  
 [6 del tutorial: Integración de BizTalk Server 2013 con Salesforce](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)