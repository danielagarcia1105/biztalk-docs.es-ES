---
title: LOBWebApplication | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, LOBWebApplication
- ASPX pages, LOBWebApplication utility
- virtual servers
- ASPX pages, submitting actions
- LOBWebApplication
- ASPX pages, response messages
- LOBWebApplication utility
ms.assetid: 2d578efd-72a9-4621-9274-30792bf94b6c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9120d9078303092740fdbfc27b6932b7849cc6a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002109"
---
# <a name="lobwebapplication"></a>LOBWebApplication
Use la utilidad de LOBWebApplication para enviar un mensaje de acción o respuesta de una página ASPX a un socio comercial, simulando una aplicación Web de línea de negocio real.  
  
 Una vez haya configurado la página ASPX, la página de inicio y escriba los parámetros de un mensaje: el principal y organizaciones asociadas; el código PIP, versión y el Id. de instancia; y la categoría del mensaje. A continuación, puede modificar el contenido del servicio y enviar el mensaje.  
  
## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*unidad*\>\Program Files (86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication  
  
## <a name="adding-a-virtual-server-for-lobwebapplication"></a>Agregar un servidor Virtual de LOBWebApplication  
  
#### <a name="to-add-a-virtual-server"></a>Para agregar un servidor virtual  
  
1.  Haga clic en **iniciar**, apunte a **AllPrograms**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  En el Administrador de servicios de información, expanda  **\<nombre_equipo\> (equipo local)**, expanda **sitios Web**y, a continuación, haga clic en **sitio Web predeterminado**.  
  
3.  Seleccione **New**y, a continuación, haga clic en **directorio Virtual**.  
  
4.  En el **Asistente para crear un directorio Virtual** página, haga clic en **siguiente**y, a continuación, escriba un alias para el sitio, como **LOBWebApplication**.  
  
5.  En el **directorio de contenido del sitio Web** página, haga clic en **examinar**, mover a \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication, haga clic en **Aceptar**y, a continuación, haga clic en **siguiente**.  
  
6.  En el **permisos de acceso del directorio Virtual** página, seleccione **lectura** y **ejecutar secuencias de comandos**y, a continuación, haga clic en **siguiente**. Haga clic en **Finalizar**.  
  
7.  Agregue el usuario de la cuenta de servicio que se usó para configurar BTARN, por ejemplo, hostsvc a la STS_WPG.  
  
8.  Eliminar todos los archivos de los archivos ASP.NET C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary. Es posible que deba ejecutar el programa iisreset para desbloquear los archivos antes de que se pueden eliminar.  
  
9. En el Administrador de IIS, establezca LOBWebApplication para ejecutarse en el BTARNHTTPReceivePool del grupo de aplicaciones.  
  
10. En el Administrador de IIS, en la sección de propiedades de seguridad del directorio de la utilidad de LOBWebApplication, deshabilite la opción para el directorio virtual para ejecutarlo como anónimo.  
  
## <a name="building-lobwebapplication"></a>Creación LOBWebApplication  
  
#### <a name="to-build-lobwebapplication"></a>Para compilar LOBWebApplication  
  
1. Inicie Visual Studio.  
  
2. En el **archivo**, apunte a **abierto**y, a continuación, haga clic en **Abrir solución**.  
  
3. Mover a \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication, seleccione  **LOBWebApplication.sln**y, a continuación, haga clic en **abierto**.  
  
   > [!NOTE]
   >  Si no ha agregado un servidor virtual de LOBWebApplication, no se abrirá correctamente en la solución [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
4. Haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
5. En el **Agregar referencia** cuadro de diálogo, haga clic en **examinar**, mover a \< *unidad*\>: \Program Files (x86) \Microsoft BizTalk \< versión\> Accelerator for RosettaNet\Bin, seleccione los archivos Microsoft.Solutions.BTARN.ConfigurationManager.dll y Microsoft.Solutions.BTARN.Shared.dll y, a continuación, haga clic en **abierto**.  
  
6. Haga clic en **LOBWebApplication**y, a continuación, haga clic en **compilar**.  
  
## <a name="running-lobwebapplication"></a>Ejecución de LOBWebApplication  
  
#### <a name="to-run-lobwebapplication-and-submit-a-message"></a>Para ejecutar LOBWebApplication y enviar un mensaje  
  
1.  Haga clic en **iniciar**, apunte a **todos los programas**y, a continuación, haga clic en **Internet Explorer**.  
  
2.  En Internet Explorer, en el **dirección** , escriba http://localhost/LOBWebApplicationy, a continuación, haga clic en **vaya**.  
  
3.  En el **enviar mensaje** diálogo cuadro, escriba la organización principal, la organización del asociado, el código PIP, la versión PIP, el identificador de instancia PIP y la categoría del mensaje.  
  
4.  Modificar el contenido del servicio según sea necesario.  
  
5.  Haga clic en **Enviar**.  
  
## <a name="remarks"></a>Notas  
 La utilidad de LOBWebApplication genera una instancia del mensaje a partir del PIP especificado y escribe el contenido del servicio de la instancia de mensaje generado en la página ASPX. Para ello, la utilidad utiliza la misma técnica que usa para generar una instancia de mensaje correcto directamente a partir de un PIP. Para obtener más información, consulte [crear una instancia de mensaje bien formado a partir de un PIP](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md). Puede rellenar cualquier campo de contenido del servicio en la página ASPX con datos reales para generar una instancia real del mensaje.  
  
 Use la utilidad de LOBWebApplication para simular una aplicación Web de línea de negocio enviando un mensaje. Use la utilidad LOBApplication para simular una aplicación de escritorio de línea de negocio enviando un mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [LOBApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)
