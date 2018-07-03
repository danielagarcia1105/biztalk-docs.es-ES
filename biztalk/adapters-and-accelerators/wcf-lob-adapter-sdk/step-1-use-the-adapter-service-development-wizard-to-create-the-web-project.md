---
title: 'Paso 1: Usar el Asistente para desarrollo de servicio de adaptador para crear el proyecto Web | Microsoft Docs'
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
ms.openlocfilehash: 5fb8737f51f9e0b6afe3d61218f69015c1cd5d72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984037"
---
# <a name="step-1-use-the-adapter-service-development-wizard-to-create-the-web-project"></a>Paso 1: Usar al Asistente para desarrollo de servicio de adaptador para crear el proyecto Web
![Paso 1 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 En este paso, creará un proyecto mediante Visual Studio y el [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]. El [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] recopila información sobre el adaptador, operaciones y las configuraciones de punto de conexión y genera un proyecto Web que, a continuación, se puede implementar en IIS.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe compilar e implementar el eco de ejemplo se describe en [Tutorial 1: desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) antes de comenzar este tutorial.  
  
### <a name="to-start-the-adapter-service-development-wizard"></a>Para iniciar al Asistente para desarrollo de servicio de adaptador  
  
1.  Inicie Visual Studio y, a continuación, en el **archivo** menú, elija **New**y, a continuación, haga clic en **sitio Web**.  
  
2.  En el **nuevo sitio Web** diálogo cuadro, lleve a cabo las siguientes acciones:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Lenguaje**|Haga clic en **Visual C#**.|  
    |**Templates** (Plantillas [C++])|Haga clic en **servicio de adaptador WCF**.|  
    |**Ubicación**|Seleccione **sistema de archivos**y, a continuación, escriba **C:\Tutorials\EchoWeb** como la ruta de acceso.|  
  
3.  Haga clic en **Aceptar**.  
  
4.  En el **página de bienvenida**, haga clic en **siguiente**.  
  
### <a name="to-select-the-adapter-and-uri"></a>Para seleccionar el adaptador y el URI  
  
1.  En el **elegir las operaciones para generar un contrato de servicio** página, seleccione **echoAdapterBindingV2** desde el **selecciona un enlace** desplegable lista y, a continuación, haga clic en  **Configurar**.  
  
2.  En el **seguridad** pestaña de la **configurar el adaptador** cuadro de diálogo, establezca **tipo de credencial de cliente** a **nombre de usuario**y, a continuación, establezca el  **Las credenciales de nombre de usuario** como sigue:  
  
    |Property|Valor|  
    |--------------|-----------|  
    |**Nombre de usuario.**|username|  
    |**Contraseña**|password|  
  
    > [!NOTE]
    >  El nombre de usuario y contraseña que especifique aquí solo se usan para conectarse al adaptador mientras realiza los pasos del asistente y no se conservan cuando se complete el asistente.  
  
3.  Haga clic en el **propiedades de URI** pestaña y, a continuación, establezca las propiedades como sigue:  
  
    |Property|Valor|  
    |--------------|-----------|  
    |**Aplicación**|LobApplication|  
    |**EnableAuthentication**|True|  
    |**Nombre de host**|lobhostname|  
    |**EchoInUpperCase**|False|  
  
    > [!NOTE]
    >  Las propiedades URI seleccionadas aquí se usará para crear el \< **cliente**\>\<**extremo** \> elementos en el archivo web.config.  
  
4.  Haga clic en el **las propiedades de enlace** ficha. Tenga en cuenta los valores predeterminados y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Los valores de enlace que se usará para generar el \< **enlaces**\>\<**echoAdapterBindingV2** \> elementos en el archivo web.config.  
  
### <a name="to-select-the-contract-and-operations"></a>Para seleccionar el contrato y operaciones  
  
1.  En el **elegir las operaciones para generar un contrato de servicio** página, haga clic en **Connect**.  
  
2.  En el **seleccionar una categoría** de árbol, seleccione **categoría principal**. Esto rellena el **operaciones y categorías disponibles** lista.  
  
    > [!NOTE]
    >  También puede escribir un término de búsqueda en el **búsqueda en la categoría** campo para buscar cualquier operación que contienen el término de búsqueda.  
  
3.  En el **operaciones y categorías disponibles** lista, seleccione **EchoGreetings** y haga clic en **agregar**. Esto mueve a la operación EchoGreetings el **agregar categorías y operaciones** lista. Las operaciones seleccionadas aquí se verá expuestas a las aplicaciones cliente a través del código de proxy de cliente generado por el asistente.  
  
     ![Seleccionar contrato y operaciones](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")  
  
4.  Haga clic en **Siguiente**.  
  
### <a name="to-configure-service-and-endpoint-behavior"></a>Para configurar el comportamiento de servicio y extremo  
  
1.  En el **configurar comportamientos del servicio y extremo** , escriba los siguientes valores para **configuración del comportamiento de servicio**:  
  
    |Property|Valor|  
    |--------------|-----------|  
    |**EnableMetadataExchange**|True|  
    |**IncludeExceptionDetailsinFault**|True|  
    |**Nombre**|customServiceBehavior|  
    |**UseServiceCertificate**|False|  
  
     Estos valores se usan para rellenar el \< **serviceBehaviors**\>.  
  
2.  Escriba los siguientes valores para **configuración del comportamiento de punto de conexión**:  
  
    |Property|Valor|  
    |--------------|-----------|  
    |**Nombre**|customEndpointBehavior|  
    |**AuthenticationType**|**HTTPUsernamePassword**|  
    |**UsernameHeader**|MyUserHeader|  
    |**PasswordHeader**|MyPassHeader|  
  
     Estos valores se usarán para especificar el **adapterSecurityBridgeType** en el <**endpointBehaviors** elemento web.confg.  
  
     ![Configuración de extremo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")  
  
3.  Haga clic en **Siguiente**.  
  
### <a name="to-configure-the-binding"></a>Para configurar el enlace  
  
1. En el **configurar el enlace del punto de conexión de servicio y la dirección** página, seleccione el **BindingConfiguration** entrada en **configurar el enlace para el contrato y dirección**, y a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
2. En el **Personalizar enlace** cuadro de diálogo, establezca **modo** a **TransportWithMessageCredential**y, a continuación, haga clic en **Aceptar**.  
  
3. Haga clic en **aplicar**y, a continuación, haga clic en **siguiente**.  
  
4. En el **resumen** , revise los contratos y operaciones seleccionadas para este proyecto y, a continuación, haga clic en **finalizar**. Se mostrará con la solución EchoWeb, que contiene los archivos de proyecto creados por el [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha utilizado el [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] para generar un sitio Web del proyecto que, cuando se publica en IIS, va a hospedar el adaptador de Echo desarrollado en [Tutorial 1: desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) en IIS el proceso. El proyecto resultante de la Web permite a los clientes WCF y servicios Web tener acceso a las operaciones seleccionadas.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Para compilar e implementar el proyecto Web, continúe con [paso 2: implementar el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 1: Desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)