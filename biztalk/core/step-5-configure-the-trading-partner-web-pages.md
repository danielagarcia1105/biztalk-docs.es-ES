---
title: 'Paso 5: Configurar las páginas Web de socios comerciales | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38c3054d-932a-42b6-a821-8b30604d8426
caps.latest.revision: 38
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd0a9be1a7df1b506c169935d12b7636155615c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001197"
---
# <a name="step-5-configure-the-trading-partner-web-pages"></a>Paso 5: Configurar las páginas Web de socios comerciales
![Paso 5 de 11](../core/media/tut-step5-of-11.gif "Tut_Step5_of_11")  
  
 En este paso, realizará las siguientes tareas para configurar páginas Web de socios comerciales:  
  
-   Habilitar el filtro ISAPI de recepción de HTTP de BTS para el transporte HTTP.  
  
-   Configurar una carpeta y una página aspx para enrutar la confirmación 997 a la organización del socio comercial Fabrikam que use el transporte HTTP. El directorio virtual de Fabrikam coloca la confirmación 997 en la \\carpeta _997ToFabrikam, que se menciona en la configuración Destination_URL del puerto de 997 envío.  
  
-   Configure la página ASPX para enrutar el mensaje original a la organización propia de Contoso. El directorio virtual de Contoso usa BTSHttpReceive.dll para recibir el mensaje AS2 y enviarlo a la ubicación de recepción.  
  
> [!NOTE]
>  Los procedimientos proporcionados en este tema son para IIS 7.0.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-enable-the-bts-isapi-filter"></a>Para habilitar el filtro ISAPI de BTS  
  
1. Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.  
  
2. Seleccione la entrada del servidor Web raíz y, en el **vista características**, haga doble clic en **asignaciones de controlador** y, a continuación, en el **acciones** panel, haga clic en **Agregar asignación de Script**.  
  
   > [!NOTE]
   >  Si configura la asignación de script en el nivel de servidor web, esta asignación se aplicará a todos los sitios web secundarios. Si desea restringir la asignación a un sitio Web específico o una carpeta virtual, seleccione el sitio de destino o la carpeta en lugar del servidor Web.  
  
3. En el **Agregar asignación de Script** diálogo cuadro, escriba `BtsHttpReceive.dll` en el **ruta de acceso de solicitud** campo.  
  
4. En el **ejecutable** , a continuación, haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive. Seleccione **BtsHttpReceive.dll**y, a continuación, haga clic en **Aceptar**.  
  
5. Escriba `BizTalk HTTP Receive` en el `Name` campo y, a continuación, haga clic en **restricciones de solicitudes**.  
  
6. En el **restricciones de solicitudes** cuadro de diálogo, seleccione el **verbos** pestaña y, a continuación, seleccione **uno de los siguientes verbos**. Escriba `POST` como verbo.  
  
7. En el **acceso** ficha, seleccione **Script**y, a continuación, haga clic en **Aceptar**.  
  
8. Haga clic en **Aceptar** y cuando se le solicite que permita la extensión ISAPI, haga clic en **Sí**.  
  
9. Haga clic en la entrada BTSHttpReceive.dll y, a continuación, seleccione **modificar permisos de características**.  
  
10. Asegúrese de que **lectura**, **Script** y **Execute** están seleccionadas y, a continuación, haga clic en **Aceptar**.  
  
11. Haga clic en **vista características**y, a continuación, haga doble clic en **restricciones de ISAPI y CGI**.  
  
12. Asegúrese de que exista una entrada para BTSHTTPReceive.dll y que **restricción** está establecido en **permitido**.  
  
    > [!NOTE]
    >  La entrada Restricción de ISAPI y CGI para BTSHTTPReceive.dll se crea automáticamente cuando crea la asignación de script.  
  
### <a name="to-configure-the-fabrikam-web-page"></a>Para configurar la página Web de Fabrikam  
  
1. En el Administrador de IIS, haga clic en **grupos de aplicaciones** y seleccione **Agregar grupo de aplicaciones**.  
  
2. En el **Agregar grupo de aplicaciones** diálogo cuadro, escriba **BizTalkAppPool** en **nombre**y, a continuación, seleccione **.NET Framework V4.0.30210** en el **Versión de .NET framework** lista desplegable. Haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  El número de versión puede variar en función de la versión de [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] instalada en el equipo.  
  
3. Seleccione **grupos de aplicaciones**, en el **vista características** seleccione **BizTalkAppPool**y, a continuación, haga clic en **configuración avanzada** en el  **Acciones** panel.  
  
4. En el **configuración avanzada** cuadro de diálogo, establezca **aplicaciones de 32 bits** a **True**.  
  
   > [!NOTE]
   >  Este paso solo es necesario en equipos de 64 bits si desea que IIS se ejecute en modo de 32 bits.  
  
5. Seleccione **identidad** y, a continuación, haga clic en el **puntos suspensivos (...)**  botón.  
  
6. En el **identidad del grupo de aplicaciones** cuadro de diálogo, seleccione **cuenta personalizada** y, a continuación, haga clic en **establecer**.  
  
7. Escriba el **nombre de usuario** y **contraseña** para una cuenta de usuario que sea miembro del grupo Administradores, escriba la contraseña en **Confirmar contraseña** y, a continuación, haga clic en **Aceptar** tres veces para volver al administrador de IIS.  
  
8. En el Administrador de IIS, abra el **sitios** carpeta. Haga clic en el **sitio Web predeterminado**y, a continuación, seleccione **Agregar aplicación**.  
  
9. En el **Agregar aplicación** diálogo cuadro, escriba **Fabrikam** en **Alias**y, a continuación, haga clic en **seleccione**.  
  
10. En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione **BizTalkAppPool** y haga clic en **Aceptar**.  
  
11. Haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Fabrikam para la **ruta de acceso física**.  
  
12. Haga clic en **configuración de pruebas** y compruebe que no hay ningún error que se muestra en el **Probar conexión** cuadro de diálogo. Haga clic en **Cerrar**y, a continuación, en **Aceptar**.  
  
13. En el Administrador de IIS, seleccione el directorio virtual de Fabrikam y, en **vista características**, haga doble clic en **autenticación**.  
  
14. En **autenticación**, seleccione **autenticación anónima** y compruebe que la **estado** es **habilitado**. Si el **estado** es **deshabilitado**, haga clic en **habilitar** en el **acciones** panel.  
  
### <a name="to-configure-the-contoso-web-page"></a>Para configurar la página Web de Contoso  
  
1. En el Administrador de IIS, abra el **sitios** carpeta. Haga clic en el **sitio Web predeterminado** y, a continuación, seleccione **Agregar aplicación**.  
  
2. En el **Agregar aplicación** diálogo cuadro, escriba **Contoso** en **Alias**y, a continuación, haga clic en **seleccione**.  
  
3. En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione **BizTalkAppPool** y haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  BizTalkAppPool se creó anteriormente al configurar la página web de Fabrikam y debe configurarse en la identidad de un usuario que es miembro del grupo de administradores.  
  
4. Haga clic en el **puntos suspensivos (...)**  botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive para la **ruta de acceso física**.  
  
5. Haga clic en **configuración de pruebas** y compruebe que no hay ningún error que se muestra en el **Probar conexión** cuadro de diálogo. Haga clic en **Cerrar**y, a continuación, en **Aceptar**.  
  
6. En el Administrador de IIS, seleccione el directorio virtual de Contoso y en el **vista características**, haga doble clic en **autenticación**.  
  
7. En **autenticación**, seleccione **autenticación anónima** y compruebe que la **estado** es **habilitado**. Si el **estado** es **deshabilitado**, haga clic en **habilitar** en el **acciones** panel.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar la ubicación de recepción (**Receive_AS2**) para recibir el mensaje AS2 de Fabrikam, tal como se describe en [paso 6: configurar la ubicación de recepción de EDI / AS2](../core/step-6-configure-the-edi-as2-receive-location.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md)
