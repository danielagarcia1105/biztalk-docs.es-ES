---
title: 'Paso 1: Utilizar el Asistente para desarrollo de servicio de adaptador para crear el proyecto Web | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ea0e33c-0d8d-4656-a6f0-3008b90f93f8
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1144b7e6827882b37f6f9991a7315cdc3cdbb88d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966970"
---
# <a name="step-1-use-the-adapter-service-development-wizard-to-create-the-web-project"></a>Paso 1: Utilizar al Asistente para desarrollo de servicio de adaptador para crear el proyecto Web
![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 En este paso, creará un proyecto con Visual Studio y la [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]. El [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] recopila información sobre el adaptador, las operaciones y las configuraciones de punto de conexión y genera un proyecto Web que, a continuación, se puede implementar en IIS.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe compilar e implementar el ejemplo de eco que se describe en [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) antes de comenzar este tutorial.  
  
### <a name="to-start-the-adapter-service-development-wizard"></a>Para iniciar al Asistente de desarrollo del servicio de adaptador  
  
1.  Inicie Visual Studio y, a continuación, en la **archivo** menú, elija **New**y, a continuación, haga clic en **sitio Web**.  
  
2.  En el **nuevo sitio Web** diálogo cuadro, lleve a cabo las siguientes acciones:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Lenguaje**|Haga clic en **Visual C#**.|  
    |**Plantillas**|Haga clic en **servicio de adaptador WCF**.|  
    |**Ubicación**|Seleccione **sistema de archivos**y, a continuación, escriba **C:\Tutorials\EchoWeb** como la ruta de acceso.|  
  
3.  Haga clic en **Aceptar**.  
  
4.  En el **página de bienvenida**, haga clic en **siguiente**.  
  
### <a name="to-select-the-adapter-and-uri"></a>Para seleccionar el adaptador y el URI  
  
1.  En el **elegir las operaciones para generar un contrato de servicio** página, seleccione **echoAdapterBindingV2** desde el **selecciona un enlace** lista desplegable lista y, a continuación, haga clic en  **Configurar**.  
  
2.  En el **seguridad** pestaña de la **configurar el adaptador** cuadro de diálogo, establezca **tipo de credencial de cliente** a **nombre de usuario**y, a continuación, establezca el  **Las credenciales de nombre de usuario** como se indica a continuación:  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |**Nombre de usuario.**|username|  
    |**Contraseña**|password|  
  
    > [!NOTE]
    >  El nombre de usuario y una contraseña escritos aquí sólo se utilizan para conectar con el adaptador al realizar los pasos del asistente y no se conservan cuando se complete el asistente.  
  
3.  Haga clic en el **propiedades de URI** ficha y, a continuación, establezca las propiedades como se indica a continuación:  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |**Aplicación**|LobApplication|  
    |**EnableAuthentication**|True|  
    |**Nombre de host**|lobhostname|  
    |**EchoInUpperCase**|False|  
  
    > [!NOTE]
    >  Las propiedades URI que seleccione aquí se usará para crear el \< **cliente**\>\<**extremo** \> elementos en el archivo web.config.  
  
4.  Haga clic en el **propiedades de enlace** ficha. Tenga en cuenta los valores predeterminados y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Los valores de enlace que se usará para generar el \< **enlaces**\>\<**echoAdapterBindingV2** \> elementos en el archivo web.config.  
  
### <a name="to-select-the-contract-and-operations"></a>Para seleccionar el contrato y operaciones  
  
1.  En el **elegir las operaciones para generar un contrato de servicio** página, haga clic en **conectar**.  
  
2.  En el **seleccione una categoría de** de árbol, seleccione **categoría principal**. Este modo se rellenará el **categorías y operaciones disponibles** lista.  
  
    > [!NOTE]
    >  También puede escribir un término de búsqueda en el **búsqueda en la categoría** campo para buscar cualquier operación que contienen el término de búsqueda.  
  
3.  En el **categorías y operaciones disponibles** lista, seleccione **EchoGreetings** y haga clic en **agregar**. Este paso traslada a la operación de EchoGreetings el **agregar categorías y operaciones** lista. Las operaciones que seleccione aquí se expondrán a las aplicaciones cliente a través del código de proxy de cliente generado por el asistente.  
  
     ![Seleccionar contrato y operaciones](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")  
  
4.  Haga clic en **Siguiente**.  
  
### <a name="to-configure-service-and-endpoint-behavior"></a>Para configurar el comportamiento de servicio y extremo  
  
1.  En el **configurar comportamientos de servicio y extremo** página, escriba los siguientes valores para **configuración de comportamiento de servicio**:  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |**EnableMetadataExchange**|True|  
    |**IncludeExceptionDetailsinFault**|True|  
    |**Nombre**|customServiceBehavior|  
    |**UseServiceCertificate**|False|  
  
     Estos valores se usan para rellenar el \< **serviceBehaviors**\>.  
  
2.  Escriba los siguientes valores para **configuración de comportamiento de extremo**:  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |**Nombre**|customEndpointBehavior|  
    |**AuthenticationType**|**HTTPUsernamePassword**|  
    |**UsernameHeader**|MyUserHeader|  
    |**PasswordHeader**|MyPassHeader|  
  
     Estos valores se utilizarán para especificar el **adapterSecurityBridgeType** en el <**endpointBehaviors** elemento en Web.config.  
  
     ![Configuración de extremo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")  
  
3.  Haga clic en **Siguiente**.  
  
### <a name="to-configure-the-binding"></a>Para configurar el enlace  
  
1.  En el **configurar el enlace de punto de conexión de servicio y la dirección** página, seleccione la **BindingConfiguration** entrada en **configurar el enlace para el contrato y dirección**, y a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
2.  En el **Personalizar enlace** cuadro de diálogo, establezca **modo** a **TransportWithMessageCredential**y, a continuación, haga clic en **Aceptar**.  
  
3.  Haga clic en **aplicar**y, a continuación, haga clic en **siguiente**.  
  
4.  En el **resumen** página, revise los contratos y operaciones seleccionadas para este proyecto y, a continuación, haga clic en **finalizar**. Le presentará la solución EchoWeb, que contiene los archivos de proyecto creados por el[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha utilizado la [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] para generar un sitio Web del proyecto que, cuando se publica en IIS, va a hospedar el adaptador de eco desarrollado en [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) en IIS procesar. El proyecto Web resultante permite a los clientes de servicios Web y WCF tener acceso a las operaciones seleccionadas.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Para compilar e implementar el proyecto Web, continúe con [paso 2: implementar el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)