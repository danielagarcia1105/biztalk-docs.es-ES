---
title: "Cómo configurar IIS para la ubicación de recepción HTTP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 64-bit support, HTTP adapters
- HTTP adapters, IIS
- configuring [HTTP adapters], IIS
- receive locations, IIS
- IIS, receive locations
- HTTP adapters, 64-bit support
- IIS, HTTP adapters
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1daa535c546bef0b390f0f7f84c45d546ac0005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-iis-for-an-http-receive-location"></a>Cómo configurar IIS para la ubicación de recepción de HTTP
En función de la versión de Microsoft Windows que se esté utilizando, se tendrá que configurar Servicios de Internet Information Server (IIS) de forma distinta para trabajar con la ubicación de recepción del adaptador de HTTP.  
  
 Si el sistema operativo es [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], IIS 7.0 proporciona dos modos de aislamiento de aplicaciones diferentes para proteger aplicaciones web. El modo de aislamiento de proceso de trabajo es el modo predeterminado. Se puede configurar la ubicación de recepción del adaptador de HTTP para trabajar con cualquiera de los dos modos, aunque se recomienda el modo de aislamiento de proceso de trabajo por su funcionalidad de seguridad mejorada.  
  
> [!NOTE]
>  Si el sistema operativo es la x64 edición de [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], la versión de 64 bits de HTTP de recepción adaptador se instala en el  *\<unidad >***\Program Files (x86) \Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\HttpReceive64** directorio de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de forma predeterminada. Para ejecutar la versión de 64 bits del adaptador de recepción HTTP en el modo nativo de 64 bits, debe ejecutar la siguiente secuencia de comandos desde una línea de comandos:  
>   
>  `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  
>   
>  `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  No será válida ninguna configuración de IIS que haga que SOAP y HTTP compartan el mismo proceso. Sólo puede haber un receptor aislado por proceso.  
  
### <a name="to-configure-the-iis-70-worker-process-isolation-mode-to-work-with-the-http-adapter-receive-location"></a>Para configurar el modo de aislamiento de proceso de trabajo de IIS 7.0 para que funcione con el adaptador de HTTP ubicación de recepción  
  
1.  Haga clic en **iniciar**, seleccione **configuración**y, a continuación, haga clic en **el Panel de Control**.  
  
2.  En el Panel de Control, haga doble clic en **herramientas administrativas**.  
  
3.  En Herramientas administrativas, haga doble clic en **Internet Information Services**.  
  
4.  En Internet Information Services, seleccione la entrada del servidor Web raíz. En el **vista características**, haga doble clic en **asignaciones de controlador**y, a continuación, en el panel Acciones, haga clic en **Agregar asignación de Script**.  
  
    > [!NOTE]
    >  Si configura la asignación de script en el nivel de servidor web, esta asignación se aplicará a todos los sitios web secundarios. Si desea restringir la asignación a un sitio web específico o a una carpeta virtual, seleccione el sitio o carpeta de destino en lugar del servidor web.  
  
5.  En el **Agregar asignación de Script** cuadro de diálogo, en la **ruta de acceso de solicitud** , escriba `BtsHttpReceive.dll`.  
  
6.  En el **ejecutable** , a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive. Seleccione **BtsHttpReceive.dll** y, a continuación, haga clic en **Aceptar**.  
  
7.  En el **nombre** , escriba `BizTalk HTTP Receive`y, a continuación, haga clic en **restricciones de solicitudes**.  
  
8.  En el **restricciones de solicitudes** cuadro de diálogo, haga clic en el **verbos** ficha y, a continuación, seleccione **uno de los siguientes verbos**. Escriba `POST` como verbo.  
  
9. En el **acceso** ficha, seleccione **Script**y, a continuación, haga clic en **Aceptar**.  
  
10. Cuando se le solicite que permita la extensión ISAPI, haga clic en **Sí**.  
  
11. Haga clic en **grupos de aplicaciones**, seleccione **New**y, a continuación, haga clic en **grupo de aplicaciones**.  
  
12. En el **Agregar grupo de aplicaciones** cuadro de diálogo, en la **nombre** , escriba un nombre para el grupo de aplicaciones. Seleccione **NET Framework v4.0.30319** y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  El número de versión puede variar en función de la versión de .NET Framework instalada en el equipo.  
  
     El nuevo grupo de aplicaciones aparece en la lista de **grupos de aplicaciones**.  
  
13. En **grupos de aplicaciones**, en la **vista características**, seleccione el nuevo grupo de aplicaciones y, a continuación, haga clic en **configuración avanzada** en el panel Acciones.  
  
14. En el **configuración avanzada** cuadro de diálogo, en la **modelo de proceso** sección, en la **identidad** , a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
15. En el **identidad del grupo de aplicaciones** cuadro de diálogo, seleccione **cuenta personalizada**y, a continuación, haga clic en **establecer**. Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Configuración avanzada** .  
  
16. En el Administrador de IIS, abra el **sitios** carpeta. Haga clic en el **sitio Web predeterminado** y, a continuación, haga clic en **Agregar aplicación**.  
  
17. En el **Agregar aplicación** cuadro de diálogo **Alias**, escriba un alias para asociarlo con la aplicación y, a continuación, haga clic en **seleccione**.  
  
18. En el **Seleccionar grupo de aplicaciones** cuadro de diálogo, seleccione el nuevo grupo de aplicaciones que creó anteriormente y, a continuación, haga clic en **Aceptar**.  
  
19. Haga clic en el botón de puntos suspensivos (**...** ) botón y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive para la **ruta de acceso física**.  
  
20. Haga clic en **conectar como** y escriba la **nombre de usuario** y **contraseña** para una cuenta de usuario que es miembro del grupo Administradores y, a continuación, haga clic en **Aceptar**.  
  
21. Haga clic en **configuración de pruebas** y compruebe que se muestra ningún error en la **Probar conexión** cuadro de diálogo. Haga clic en **Cerrar**y, a continuación, en **Aceptar**.  
  
22. La nueva aplicación aparece en la lista de **sitios Web predeterminados** en el Administrador de Internet Information Services (IIS).  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar ubicación de recepción de HTTP](../core/how-to-configure-an-http-receive-location.md)