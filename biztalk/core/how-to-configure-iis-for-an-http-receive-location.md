---
title: Configurar IIS para ubicación de recepción HTTP | Microsoft Docs
description: Crear la aplicación de recepción HTTP de BTS en IIS y probar la configuración del grupo de aplicación de BizTalk Server
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
ms.openlocfilehash: cfc616fa9834071c2ee8d2b4d63f486ff0abbeab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004829"
---
# <a name="configure-iis-for-an-http-receive-location"></a>Configurar IIS para ubicación de recepción HTTP
HTTP ubicación de recepción utiliza una aplicación dentro de Internet Information Services (IIS). Este tema se enumeran los pasos para habilitar el HTTP ubicación dentro de IIS de recepción. 

Dependiendo del sistema operativo, los pasos para configurar la aplicación de IIS pueden variar. Siga estos pasos como guía, como la interfaz de usuario puede ser diferente en su sistema operativo.
  
## <a name="32-bit-vs-64-bit"></a>32 bits frente a 64 bits

HTTP ubicación de recepción utiliza la BTSHTTPReceive.dll. Hay una versión de 64 bits del archivo DLL y de 32 bits. Elija qué versión desea utilizar. los procesos de 64 bits tienen más memoria disponible, por lo que si procesar los mensajes más grandes, a continuación, la versión de 64 bits puede ser mejor. 

**ubicación de instalación de 32 bits**: *archivos de programa (x86) \Microsoft BizTalk Server\HttpReceive*.
**ubicación de instalación de 64 bits**: *\Microsoft BizTalk Server\HttpReceive64 (x86) de archivos de programa*

Para ejecutar la versión de 64 bits de HTTP en modo nativo de 64 bits del adaptador de recepción, abra un símbolo del sistema y ejecute los siguientes scripts:  

1. Tipo: `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  

2. Tipo: `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  No será válida ninguna configuración de IIS que haga que SOAP y HTTP compartan el mismo proceso. Sólo puede haber un receptor aislado por proceso.  
  
##  <a name="configure-the-iis-application"></a>Configurar la aplicación de IIS
  
1. Abra **Internet Information Services** (abrir **administrador del servidor**, seleccione **herramientas**y seleccione **Administrador de Internet Information Services**). 
  
2. En IIS, seleccione el nombre del servidor. En el **vista características**, haga doble clic en **asignaciones de controlador**. En el panel Acciones, seleccione **Agregar asignación de Script**.  
  
   > [!NOTE]
   >  Al configurar la asignación de script en el nivel de servidor web, la asignación se aplica a todos los sitios web. Si desea restringir la asignación a un sitio Web específico o una carpeta virtual, seleccione esa carpeta o sitio web y, a continuación, agregue la asignación de script.  
  
3. En **Agregar asignación de Script**, seleccione **ruta de acceso de solicitud**y el tipo `BtsHttpReceive.dll`.  
  
4. En **ejecutable**, seleccione los puntos suspensivos (**...** ) y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive. Seleccione **BtsHttpReceive.dll**y, a continuación, seleccione **abierto**.  
  
5. En **nombre**, escriba `BizTalk HTTP Receive`y, a continuación, seleccione **restricciones de solicitudes**. En esta ventana:
  
   1. En **verbos**, seleccione **uno de los siguientes verbos**y escriba `POST`.  
  
   2. En **acceso**, seleccione **Script**y, a continuación, seleccione **Aceptar**.  
  
   3. Cuando se le solicite que permita la extensión ISAPI, seleccione **Sí**.  
  
6. Crear un nuevo grupo de aplicaciones (haga clic en **grupos de aplicaciones**, seleccione **Agregar grupo de aplicaciones**). **Nombre** el grupo de aplicaciones (como `BTSHTTPReceive`), seleccione **NET Framework v4.0.30319**y seleccione **Aceptar**.  
  
    > [!NOTE]
    >  El número de versión de .NET puede variar según la versión de .NET Framework instalada en el equipo.  
  
     Aparece el nuevo grupo de aplicaciones.  
  
7. Seleccione el nuevo grupo de aplicaciones y abra el **configuración avanzada** (**acciones** panel). En esta ventana:

    - **Habilitar aplicación de 32 bits**: establecido en **True** si eligió el 32-bit **BtsHttpReceive.dll**
    - **Procesar modelo** sección **identidad**: seleccione los puntos suspensivos (**...** ), seleccione **cuenta personalizada**y, a continuación, **establecer** a una cuenta que sea miembro de la **usuarios de hosts aislados de BizTalk** y  **IIS_WPG** grupos. Seleccione **Aceptar**. 
  
8. Agregar una nueva aplicación en el sitio web (haga clic en el **sitio Web predeterminado**, seleccione **Agregar aplicación**). En esta ventana:
  
   1. **Alias** : escriba un alias que se asocia a la aplicación (como `BTS HTTP Receive`y, a continuación, **seleccione**.  
   2. Seleccione el nuevo grupo de aplicaciones que acaba de crear y, a continuación, seleccione **Aceptar**.  
   3. **Ruta de acceso física**: seleccione los puntos suspensivos (**...** ) y vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.  
   4. **Configuración de pruebas** para comprobar que no hay ningún error en la **Probar conexión** cuadro de diálogo. **Cerrar**y, a continuación, seleccione **Aceptar**.  
  
      > [!TIP]
      > Si la configuración de pruebas, se devuelve una advertencia, la identidad del grupo de aplicaciones puede que falten permisos a una carpeta o el acceso a un grupo. Como paso de solución de problemas, seleccione **conectar como**, escriba el **nombre de usuario** y **contraseña** para una cuenta de usuario que sea miembro del grupo Administradores. 

9. Aparece la nueva aplicación aparece en **sitios Web predeterminados**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar ubicación de recepción HTTP](../core/how-to-configure-an-http-receive-location.md)
