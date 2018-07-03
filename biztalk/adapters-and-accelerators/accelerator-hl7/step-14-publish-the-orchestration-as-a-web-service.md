---
title: 'Paso 14: Publicar la orquestación como un servicio Web | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- publishing, orchestrations
- Web services, orchestrations
- message enrichment tutorial, orchestrations
- publishing, Web services
- message enrichment tutorial, Web services
ms.assetid: 8f29a7be-a679-4ca6-a648-35338d9e9e98
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64bcc47364cca427f2fc02a807528e7105a40837
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992085"
---
# <a name="step-14-publish-the-orchestration-as-a-web-service"></a>Paso 14: Publicar la orquestación como un servicio Web
En este paso, usará al Asistente para publicar servicios Web de BizTalk para publicar una orquestación como un servicio Web.  
  
 Antes de publicar la orquestación como un servicio Web, deberá asegurarse de que la cuenta de inicio de sesión para BizTalkServerIsolatedHost es parte del grupo de usuarios de hosts aislados de BizTalk, por lo que tiene acceso a las bases de datos de BizTalk. Esto es necesario porque el controlador de recepción para la ubicación de recepción SOAPReceivePort creado por el Asistente de publicación de servicio Web para este tutorial es BizTalkServerIsolatedHost, no BizTalkServerApplication. El controlador de recepción es BizTalkServerIsolatedHost porque el adaptador de SOAP se ejecuta en el proceso de IIS, no el proceso de BizTalk.  
  
### <a name="to-ensure-access-privileges-for-the-soapreceiveport-receive-location"></a>Para garantizar el acceso de ubicación de recepción privilegios para la SOAPReceivePort  
  
1.  En la consola de administración de BizTalk Server, bajo **instancias de Host** en el **configuración de plataforma** nodo, haga clic en **BizTalkServerIsolatedHost**y, a continuación, haga clic en  **Propiedades**. En el cuadro de diálogo Propiedades, haga clic en **configurar**. Tenga en cuenta la **inicio de sesión** cuenta.  
  
2.  En el cuadro de diálogo Administración de equipos en **grupos** en el **usuarios y grupos locales** nodo, haga doble clic en **usuarios de hosts aislados de BizTalk**. Si tiene en cuenta el inicio de sesión **BizTalkServerIsolatedHost** no es un miembro de **BizTalkServerIsolatedHost**, agréguelo al grupo.  
  
### <a name="to-run-the-biztalk-web-services-publishing-wizard"></a>Para ejecutar al Asistente para publicar servicios Web de BizTalk  
  
1. En el Explorador de soluciones de Visual Studio, haga clic en **solución 'BTAHL7V22Common'**. En el **herramientas** menú, haga clic en **Asistente para publicación de BizTalk Web Services**.  
  
2. En el **Asistente para publicación de BizTalk Web Services**, en el **bienvenida** página, haga clic en **siguiente**.  
  
3. En el **crear servicio Web** página, seleccione **publicar orquestaciones de BizTalk como servicios web**y, a continuación, haga clic en **siguiente**.  
  
4. En el **ensamblado de BizTalk** página, en el **archivo de ensamblado de BizTalk (\*.dll)** campo, busque o escriba  **\< *unidad* \>: \Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**, haga clic en **BTAHL7 Project.dll**, haga clic en **abierto**y, a continuación, haga clic en **siguiente**.  
  
5. En el **orquestaciones y puertos** , asegúrese de que todos los nodos están seleccionados y, a continuación, haga clic en **siguiente**.  
  
6. En el **propiedades del servicio Web** página, para **espacio de nombres de destino del servicio web**, tipo **http://localhost**y, a continuación, haga clic en **siguiente**.  
  
7. En el **proyecto de servicio Web** página, seleccione **permitir acceso anónimo al servicio web** y **ubicaciones de recepción de BizTalk crea en la siguiente aplicación**. Seleccione **BizTalk Application 1** para la aplicación. Mantenga el valor predeterminado el **ubicación** campo. Haga clic en **siguiente** para aceptar la ubicación predeterminada del proyecto.  
  
8. En el **resumen del proyecto de servicio Web** página, haga clic en **crear** para generar el proyecto de servicio Web ASP.NET.  
  
9. Haga clic en **Finalizar** para cerrar el asistente.  
  
10. Abra la consola de administración de BizTalk Server. En la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **BizTalk Application 1** .  
  
11. Haga clic en **ubicaciones de recepción**, haga clic en **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**y, a continuación, haga clic en **propiedades**.  
  
12. En el cuadro de diálogo Propiedades de ubicación de recepción, haga clic en **canalización de recepción**, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLReceive** desde la lista desplegable y, a continuación, haga clic en **Aceptar**.  
  
13. Haga clic en **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**y, a continuación, haga clic en **habilitar**.  
  
    Continúe con [paso 15: configurar el envío y puertos de recepción](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)