---
title: 'Paso 7: Crear e implementar el ejemplo de SDK de LOBWebApplication | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- double action tutorial, deploying solutions
ms.assetid: f61de666-ebda-4831-9669-598e9284e4c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a0716c854c20f5ea7fa7d2ad91576cb142f6a02
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996189"
---
# <a name="step-7-building-and-deploying-the-lobwebapplication-sdk-sample"></a>Paso 7: Crear e implementar el ejemplo de SDK de LOBWebApplication
En este paso, creará la aplicación de línea de negocio (LOB) que Fabrikam usa para enviar solicitudes de Proceso de interfaz de socio (PIP) a Contoso. Puede encontrar el proyecto LOBWebApplication en el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] carpeta del SDK. Para ejecutar la aplicación Web, tendrá que crear un directorio virtual de Microsoft Internet Information Services (IIS) y, a continuación, compile el proyecto de LOBWebApplication.  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a>Para crear el directorio virtual LOBWebApplication  
  
1.  Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.  
  
2.  En la ventana Administrador de Internet Information Services, expanda **< nombre_equipo > (equipo local)** y, a continuación, expanda **sitios Web**.  
  
3.  Haga clic con el botón secundario en **Sitio Web predeterminado**, elija **Nuevo**y, a continuación, haga clic en **Directorio virtual**.  
  
4.  En el **Welcometo el Asistente para creación de un directorio Virtual** página, haga clic en **siguiente**.  
  
5.  En la página **Alias del directorio virtual** , en el cuadro **Alias** , escriba **LOBWebApplication**y, a continuación, haga clic en **Siguiente**.  
  
6.  En la página **Directorio de contenido del sitio Web** , haga clic en **Examinar**. En el cuadro de diálogo Buscar carpeta, mover a ***\<unidad\>*:\Program comunes\Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication**y, a continuación, Haga clic en **Aceptar**. Haga clic en **Siguiente**.  
  
7.  En la página **Permisos de acceso de directorio virtual** , anule la selección de **Leer**, seleccione **Ejecutar scripts (por ejemplo, ASP)** y, a continuación, haga clic en **Siguiente**.  
  
8.  En la página **Ha completado correctamente el Asistente para crear un directorio Virtual** , haga clic en **Finalizar** para crear el directorio virtual.  
  
### <a name="to-exclude-the-lobwebapplication-web-site-from-the-sharepoint-configuration"></a>Para excluir el sitio web LOBWebApplication de la configuración de SharePoint  
  
1.  Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administración central de SharePoint**.  
  
2.  En la página web **Administración central** , en la sección **Configuración del servidor virtual** , seleccione **Extender o actualizar el servidor virtual**.  
  
3.  Si no ve la dirección URL configurada en el equipo, haga clic en **Lista completa**.  
  
4.  En la página **Lista de servidor virtual** , seleccione **Sitio web predeterminado**.  
  
5.  En la sección **Administración del servidor virtual** , haga clic en **Definir rutas de acceso administradas**.  
  
6.  En la sección **Agregar nueva ruta de acceso** , en el cuadro **Ruta de acceso** , escriba **/LOBWebApplication**.  
  
7.  En **Tipo**, seleccione **Ruta excluida**y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-build-the-lobwebapplication-project"></a>Para compilar el proyecto LOBWebApplication  
  
1.  Haga clic en **Inicio**, elija **Todos los programas**, **Microsoft Visual Studio 2008**y, a continuación, haga clic en **Microsoft Visual Studio 2008**.  
  
2.  En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto o solución**.  
  
3.  En el cuadro de diálogo Abrir proyecto, vaya a ***\<unidad\>*:\Program comunes\Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication**, seleccione el  **LOBWebApplication.sln** archivo de solución y, a continuación, haga clic en **abierto**.  
  
4.  En el Explorador de soluciones, haga clic en **http://localhost/LOBWebApplication**y, a continuación, haga clic en **Agregar referencia**.  
  
5.  En el cuadro de diálogo Agregar referencia, haga clic en **Examinar**. En el cuadro de diálogo Agregar referencia, vaya a ***\<unidad\>*:\Program comunes\Microsoft BizTalk \<versión\> Accelerator for RosettaNet\Bin** carpeta.  
  
6.  En la carpeta Bin, seleccione los ensamblados **Microsoft.Solutions.BTARN.ConfigurationManager.dll** y **Microsoft.Solutions.BTARN.Shared.dll** assemblies, y then click **Abrir**.  
  
7.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Agregar referencia** .  
  
8.  En el explorador de soluciones, haga clic con el botón derecho en **Solución 'LOBWebApplication'** y, luego, haga clic en **Compilar solución**.  
  
9. Haga clic con el botón derecho en **default.aspx**y, a continuación, haga clic en **Establecer como página de inicio**.  
  
## <a name="see-also"></a>Vea también  
 [Prueba del tutorial de doble acción](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)