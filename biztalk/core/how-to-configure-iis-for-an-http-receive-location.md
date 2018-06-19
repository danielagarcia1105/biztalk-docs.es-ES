---
title: Configurar IIS para la ubicación de recepción HTTP | Documentos de Microsoft
description: Crear la aplicación de recepción de HTTP de BTS en IIS y probar la configuración del grupo de aplicaciones de BizTalk Server
ms.custom: ''
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e09768d6616a33a4900995f3dd3225fa34318b3c
ms.sourcegitcommit: 75d35f6f230f0846c29a4b146c6d5b074e60b13c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2017
ms.locfileid: "22645176"
---
# <a name="configure-iis-for-an-http-receive-location"></a>Configurar IIS para la ubicación de recepción de HTTP
HTTP ubicación de recepción utiliza una aplicación de Internet Information Services (IIS). Ubicación dentro de IIS de recepción de este tema se enumeran los pasos para habilitar HTTP. 

Dependiendo del sistema operativo, los pasos para configurar la aplicación de IIS pueden variar. Siga estos pasos como guía, como la interfaz de usuario puede ser diferente en el sistema operativo.
  
## <a name="32-bit-vs-64-bit"></a>32 y 64 bits

HTTP ubicación de recepción utiliza la BTSHTTPReceive.dll. Hay 32 bits y una versión de 64 bits del archivo DLL. Elija qué versión desea utilizar. procesos de 64 bits tienen más memoria disponible, por lo que si se procesan mensajes más grandes, la versión de 64 bits puede ser más apropiada. 

**ubicación de instalación de 32 bits**: *archivos de programa (x86) \Microsoft BizTalk Server\HttpReceive*.
**ubicación de instalación de 64 bits**: *\Microsoft BizTalk Server\HttpReceive64 (x86) de archivos de programa*

Para ejecutar la versión de 64 bits de HTTP en modo nativo de 64 bits del adaptador de recepción, abra un símbolo del sistema y ejecute los siguientes scripts:  

1. Tipo:`cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  

2. Tipo:`C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  No será válida ninguna configuración de IIS que haga que SOAP y HTTP compartan el mismo proceso. Sólo puede haber un receptor aislado por proceso.  
  
##  <a name="configure-the-iis-application"></a>Configurar la aplicación de IIS
  
1.  Abra **Internet Information Services** (abrir **el administrador del servidor**, seleccione **herramientas**y seleccione **Administrador de Internet Information Services**). 
  
2.  En IIS, seleccione el nombre del servidor. En el **vista características**, haga doble clic en **asignaciones de controlador**. En el panel Acciones, seleccione **Agregar asignación de Script**.  
  
    > [!NOTE]
    >  Al configurar la asignación de script en el nivel de servidor web, la asignación se aplica a todos los sitios web. Si desea restringir la asignación a un sitio Web específico o una carpeta virtual, seleccione ese sitio web o una carpeta y, a continuación, agregue la asignación de script.  
  
3.  En **Agregar asignación de Script**, seleccione **ruta de acceso de solicitud**y el tipo de `BtsHttpReceive.dll`.  
  
4.  En **ejecutable**, seleccione los puntos suspensivos (**...** ) y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive. Seleccione **BtsHttpReceive.dll**y, a continuación, seleccione **abiertos**.  
  
5.  En **nombre**, escriba `BizTalk HTTP Receive`y, a continuación, seleccione **restricciones de solicitudes**. En esta ventana:
  
    1. En **verbos**, seleccione **uno de los siguientes verbos**y escriba `POST`.  
  
    2. En **acceso**, seleccione **Script**y, a continuación, seleccione **Aceptar**.  
  
    3. Cuando se le pida que permita la extensión ISAPI, seleccione **Sí**.  
  
6. Crear un nuevo grupo de aplicaciones (haga clic en **grupos de aplicaciones**, seleccione **Agregar grupo de aplicaciones**). **Nombre** el grupo de aplicaciones (como `BTSHTTPReceive`), seleccione **NET Framework v4.0.30319**y seleccione **Aceptar**.  
  
    > [!NOTE]
    >  El número de versión de .NET puede variar según la versión de .NET Framework instalada en el equipo.  
  
     Aparece el nuevo grupo de aplicaciones.  
  
7. Seleccione el nuevo grupo de aplicaciones y abra el **configuración avanzada** (**acciones** panel). En esta ventana:

    - **Habilitar aplicación de 32 bits**: establézcalo **True** si ha elegido 32 bits **BtsHttpReceive.dll**
    - **Procesar modelo** sección, **identidad**: seleccione los puntos suspensivos (**...** ), seleccione **cuenta personalizada**y, a continuación, **establecer** a una cuenta que sea miembro de la **usuarios de hosts aislados de BizTalk** y **IIS_WPG** grupos. Seleccione **Aceptar**. 
  
8. Agregar una nueva aplicación para el sitio web (haga clic en el **sitio Web predeterminado**, seleccione **Agregar aplicación**). En esta ventana:
  
    1. **Alias** : escriba un alias que asocian a la aplicación (como `BTS HTTP Receive`y, a continuación, **seleccione**.  
    2. Seleccione el nuevo grupo de aplicaciones recién creado y, a continuación, seleccione **Aceptar**.  
    3. **Ruta de acceso física**: seleccione los puntos suspensivos (**...** ) y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.  
    4. **Configuración de pruebas** para comprobar que no existen errores en la **Probar conexión** cuadro de diálogo. **Cerrar**y, a continuación, seleccione **Aceptar**.  
  
    > [!TIP]
    > Si la configuración de pruebas, se devuelve una advertencia, la identidad del grupo de aplicaciones puede que falten permisos a una carpeta o el acceso a un grupo. Como un paso de la solución de problemas, seleccione **conectar como**, escriba la **nombre de usuario** y **contraseña** para una cuenta de usuario que sea miembro del grupo Administradores. 

9. Aparece la nueva aplicación aparece en **sitios Web predeterminados**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar ubicación de recepción de HTTP](../core/how-to-configure-an-http-receive-location.md)
