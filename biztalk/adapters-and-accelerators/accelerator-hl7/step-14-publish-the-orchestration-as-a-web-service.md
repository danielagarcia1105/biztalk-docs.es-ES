---
title: "Paso 14: La orquestación como un servicio Web de publicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- publishing, orchestrations
- Web services, orchestrations
- message enrichment tutorial, orchestrations
- publishing, Web services
- message enrichment tutorial, Web services
ms.assetid: 8f29a7be-a679-4ca6-a648-35338d9e9e98
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c742d21dd2f2e1d95f697beea3d5d5dfa0461d2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="step-14-publish-the-orchestration-as-a-web-service"></a>Paso 14: Publicar la orquestación como servicio Web
En este paso, usa al Asistente para publicación de servicios Web de BizTalk para publicar una orquestación como un servicio Web.  
  
 Antes de publicar la orquestación como un servicio Web, debe asegurarse de que la cuenta de inicio de sesión para BizTalkServerIsolatedHost es parte del grupo de usuarios de hosts aislados de BizTalk, por lo que tiene acceso a las bases de datos de BizTalk. Esto es necesario porque el controlador de recepción para la ubicación de recepción de SOAPReceivePort que se crea mediante el Asistente de publicación de servicio Web para este tutorial es BizTalkServerIsolatedHost, no BizTalkServerApplication. El controlador de recepción es BizTalkServerIsolatedHost porque el adaptador de SOAP se ejecuta en el proceso IIS, no el proceso de BizTalk.  
  
### <a name="to-ensure-access-privileges-for-the-soapreceiveport-receive-location"></a>Para garantizar un acceso de ubicación de recepción privilegios para la SOAPReceivePort  
  
1.  En la consola de administración de BizTalk Server, en **instancias de Host** en el **configuración de plataforma** nodo, haga clic en **BizTalkServerIsolatedHost**y, a continuación, haga clic en  **Propiedades**. En el cuadro de diálogo Propiedades, haga clic en **configurar**. Tenga en cuenta el **inicio de sesión** cuenta.  
  
2.  En el cuadro de diálogo Administración de equipos, en **grupos** en el **usuarios y grupos locales** nodo, haga doble clic en **usuarios de hosts aislados de BizTalk**. Si tiene en cuenta el inicio de sesión **BizTalkServerIsolatedHost** no es un miembro de **BizTalkServerIsolatedHost**, agregar al grupo.  
  
### <a name="to-run-the-biztalk-web-services-publishing-wizard"></a>Para ejecutar al Asistente para publicación de servicios Web de BizTalk  
  
1.  En el Explorador de soluciones de Visual Studio, haga clic en **solución 'BTAHL7V22Common'**. En el **herramientas** menú, haga clic en **Asistente para publicación de BizTalk Web Services**.  
  
2.  En el **Asistente para publicación de BizTalk Web Services**, en la **bienvenida** página, haga clic en **siguiente**.  
  
3.  En el **crear servicio Web** página, seleccione **publicar orquestaciones de BizTalk como servicios web**y, a continuación, haga clic en **siguiente**.  
  
4.  En el **ensamblado de BizTalk** página, en la **archivo de ensamblado de BizTalk (\*.dll)** campo, busque o escriba  **\< *unidad* \>: \Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**, haga clic en **BTAHL7 Project.dll**, haga clic en **abiertos**y, a continuación, haga clic en **siguiente**.  
  
5.  En el **orquestaciones y puertos** página, asegúrese de que todos los nodos están seleccionados y, a continuación, haga clic en **siguiente**.  
  
6.  En el **propiedades del servicio Web** página, para **espacio de nombres de destino del servicio web**, tipo **http://localhost**y, a continuación, haga clic en **siguiente**.  
  
7.  En el **proyecto de servicio Web** página, seleccione **permitir el acceso anónimo al servicio web** y **ubicaciones de recepción de BizTalk crea en la siguiente aplicación**. Seleccione **BizTalk Application 1** para la aplicación. Mantenga el valor predeterminado el **ubicación** campo. Haga clic en **siguiente** para aceptar la ubicación predeterminada del proyecto.  
  
8.  En el **resumen del proyecto de servicio Web** página, haga clic en **crear** para generar el proyecto de servicio Web ASP.NET.  
  
9. Haga clic en **Finalizar** para cerrar el asistente.  
  
10. Abra la consola de administración de BizTalk Server. En la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **BizTalk Application 1** .  
  
11. Haga clic en **ubicaciones de recepción**, haga clic en **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**y, a continuación, haga clic en **propiedades**.  
  
12. En el cuadro de diálogo Propiedades de la ubicación de recepción, haga clic en **canalización de recepción**, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLReceive** desde la lista desplegable y, a continuación, haga clic en **Aceptar**.  
  
13. Haga clic en **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**y, a continuación, haga clic en **habilitar**.  
  
 Continúe con [paso 15: configurar el envío y puertos de recepción](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)