---
title: "Cómo comprobar el estado de actividad de un mensaje | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities, verifying status
- PeopleSoft Integration Broker
- verifying message status in PeopleSoft
- messages, verifying status
ms.assetid: b8cee6f9-0f65-4228-a87a-3f3aca6182bf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 872c1a1fcfcc905caf926c8299f56d49178a8448
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-verify-activity-status-of-a-message"></a>Cómo comprobar el estado de actividad de un  mensaje
Para crear un host y un puerto HTTP de PeopleSoft donde PeopleSoft envíe los eventos, se usa el Agente de integración de PeopleSoft. Para asegurarse de que el mensaje esté activo y enrutado, siga estos pasos.  
  
### <a name="to-verify-that-a-message-is-active-and-routed-correctly"></a>Para verificar que un mensaje esté activo y se haya enrutado correctamente  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **PeopleSoft Application Name**y, a continuación, seleccione **Application Designer**.  
  
2.  En el **PeopleSoft Sign-on** pantalla, escriba la **Id. de usuario** y **contraseña**y, a continuación, haga clic en **Aceptar**.  
  
     ![](../core/media/psadapter-24-task-userpass.gif "PSAdapter_24_Task_UserPass")  
  
     ![](../core/media/psadapter-25-task-emptydesigner.gif "PSAdapter_25_Task_EmptyDesigner")  
  
3.  En el Diseñador de aplicaciones, en la **archivo** menú, elija **abiertos**y, a continuación, seleccione **mensaje**.  
  
     ![](../core/media/psadapter-26-task-filemessage.gif "PSAdapter_26_Task_FileMessage")  
  
4.  En el **Abrir definición** pantalla, en la **nombre** , escriba `LOCATION_SYNC`y, a continuación, haga clic en **abiertos**.  
  
     ![](../core/media/psadapter-27-task-locationsync.gif "PSAdapter_27_Task_LocationSync")  
  
5.  En el **definiciones que coinciden con los criterios de selección** sección, haga doble clic en el **LOCATION_SYNC** mensaje para ver las propiedades.  
  
     ![](../core/media/psadapter-28-task-locationproperties.gif "PSAdapter_28_Task_LocationProperties")  
  
6.  En el Diseñador de aplicaciones, haga clic en **LOCATION_TBL**y seleccione **propiedades de mensaje**.  
  
     ![](../core/media/psadapter-29-task-loctionmenu.gif "PSAdapter_29_Task_LoctionMenu")  
  
7.  En el **propiedades de mensaje** pantalla, haga clic en el **Use** ficha.  
  
     Compruebe lo siguiente y, a continuación, haga clic en **Aceptar**.  
  
    1.  **Mensaje:** Active  
  
    2.  **Canal de mensaje:** ENTERPRISE_SETUP  
  
    3.  **Versión predeterminada:** VERSION_1  
  
     ![](../core/media/psadapter-30-task-messageuse.gif "PSAdapter_30_Task_MessageUse")  
  
8.  Salga de Application Designer.  
  
     De este modo, se asegura de que el estado del mensaje sea activo, de que usa VERSION_1 y de que se transmite a través del canal ENTERPRISE_SETUP en PeopleSoft.  
  
9. Configure el archivo Integration.Gateway.properties para establecer comunicación con la aplicación de PeopleSoft.  
  
     Compruebe que se hayan configurado las propiedades siguientes:  
  
    -   **Ig.ISC.ServerURL:** //server:9000  
  
    -   **Ig.ISC.UserID:** Id. para PS  
  
    -   **Ig.ISC.Password:** contraseña para PS  
  
    -   **Ig.ISC.toolsrel:** versión específica  
  
## <a name="see-also"></a>Vea también  
 [Crear un Host de HTTP de PeopleSoft y puerto](../core/creating-a-peoplesoft-http-host-and-port.md)