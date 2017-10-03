---
title: "Paso 2: Configurar e iniciar la aplicación 1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cb061ca-acf4-4de4-a634-b3bb98876989
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc9c3c027126d3a461bf99329b70fda57b9be647
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-and-start-the-application"></a>Paso 2: Configurar e iniciar la aplicación
![Paso 2 de 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, configurará e iniciará la aplicación EAISolution.  
  
 **Propósito:** la configuración está relacionada principalmente con enlace.  Un enlace crea una asignación entre un extremo lógico, como un puerto de orquestación o un vínculo de rol, y un extremo físico, como una entidad o un puerto de envío o recepción. Permite la comunicación entre componentes diferentes de una solución empresarial de BizTalk. Puede crear enlaces mediante la consola de administración de BizTalk Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Tenga en cuenta los siguientes requisitos antes de iniciar este paso:  
  
-   Antes de comenzar este paso debe completar [paso 1: implementar los proyectos](../core/step-1-deploy-the-projects.md).  
  
-   Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="procedures"></a>Procedimientos  
 La aplicación de BizTalk es una característica de BizTalk Server que facilita y agiliza la implementación, administración y solución de problemas de las soluciones empresariales de BizTalk Server. Una aplicación de BizTalk es una agrupación lógica de elementos, denominados "artefactos", que se utiliza en una solución empresarial de BizTalk Server.  Para obtener más información, consulte [¿qué es una aplicación de BizTalk?](../core/what-is-a-biztalk-application.md).  En [paso 1: implementar los proyectos](../core/step-1-deploy-the-projects.md), configuramos el nombre de la aplicación como "EAISolution" antes de implementar los proyectos.  Así pues, la aplicación EAISolution contiene la orquestación, los dos esquemas y la asignación.  
  
#### <a name="to-open-the-eaisolution-application-from-biztalk-server-administration-console"></a>Para abrir la aplicación EAISolution desde la consola de administración de BizTalk Server  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  
  
2.  En el árbol de consola en el lado izquierdo de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], haga clic en **grupo de BizTalk**y, a continuación, haga clic en **actualizar**.  
  
3.  Expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, haga clic en **EAISolution**.  
  
 En [lección 2: definir el proceso empresarial](../core/lesson-2-define-the-business-process.md), hemos creado una orquestación.  En la orquestación, se definieron los puertos lógicos.  En los procedimientos siguientes, se definirán los puertos físicos y se vincularán a los puertos lógicos.  
  
#### <a name="to-create-the-receiverequest-port"></a>Para crear el puerto ReceiveRequest  
  
1.  Desde la consola de administración de BizTalk Server, en la **EAISolution** nodo, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **unidireccional Puerto de recepción**.  
  
2.  En la ficha General, realice una de las acciones siguientes:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **EAISolutionReceiveRequestPort**.|  
    |**Habilitar enrutamiento para mensajes con errores**|(clear)|  
  
3.  Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **nuevo**.  
  
4.  Desde Ubicación de recepción1 - Propiedades de ubicación de recepción, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **EAISolutionReceiveRequestLocation**.|  
    |**Tipo**|Seleccione **archivo**.|  
    |**Controlador de recepción**|Seleccionar **BizTalkServerApplication**.|  
    |**La canalización de recepción**|Seleccione **XMLReceive**.|  
  
5.  Haga clic en **configurar**.  
  
6.  Desde Propiedades de transporte de archivo, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Carpeta de recepción**|Tipo de **C:\BTSTutorials\WareHouse\Request**.|  
  
7.  Haga clic en **Aceptar** tres veces.  
  
#### <a name="to-create-the-senddecline-port"></a>Para crear el puerto SendDecline  
  
1.  Desde la consola de administración de BizTalk Server, en la **EAISolution** nodo, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **unidireccional estático Puerto de envío**.  
  
2.  En la ficha General, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **EAISolutionSendDeclinePort**.|  
    |**Tipo**|Seleccione **archivo**.|  
    |**Controlador de envío**|Seleccione **BizTAlkServerApplication**.|  
    |**Canalización de envío**|Seleccione **XMLTransmit**.|  
  
3.  Haga clic en **configurar**.  
  
4.  Desde Propiedades de transporte de archivo, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Carpeta de recepción**|Tipo de **C:\BTSTutorials\WareHouse\RequestDecline**.|  
    |**Nombre de archivo**|Tipo de **RequestDecline_%MessageID%.xml**.|  
  
5.  Haga clic en **Aceptar** dos veces.  
  
#### <a name="to-create-the-sendtoerp-port"></a>Para crear el puerto SendToERP  
  
1.  Desde la consola de administración de BizTalk Server, en la **EAISolution** nodo, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **unidireccional estático Puerto de envío**.  
  
2.  En la ficha General, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **EAISolutionSendToERPPort**.|  
    |**Tipo**|Seleccione **archivo**.|  
    |**Controlador de envío**|Seleccione **BizTAlkServerApplication**.|  
    |**Canalización de envío**|Seleccione **XMLTransmit**.|  
  
3.  Haga clic en **configurar**.  
  
4.  Desde Propiedades de transporte de archivo, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Carpeta de recepción**|Tipo de **C:\BTSTutorials\ERP\Request**.|  
    |**Nombre de archivo**|Tipo de **Request_%MessageID%.xml**.|  
  
5.  Haga clic en **Aceptar** dos veces.  
  
#### <a name="to-bind-the-ports"></a>Para enlazar los puertos  
  
1.  Desde la consola de administración de BizTalk Server, haga clic en **EAISolution**y, a continuación, haga clic en **configurar**.  
  
2.  Desde Configurar aplicación, en el panel izquierdo, haga clic en **EAIProcess**.  Esta es la orquestación que se ha creado.  
  
3.  En el panel derecho, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Host**|Seleccionar **BizTalkServerApplication**.|  
    |**Puerto de recepción** para **ReceiveRequestPort**|Seleccione **EAISolutionReceiveReqeustPort**.|  
    |**Grupos de puertos de puertos de envío** para **ReceiveRequestPort**|Seleccione **EAISolutionSendDeclinePort**.|  
    |**Puerto de recepción** para **ReceiveRequestPort**|Seleccione **EAISolutionSendToERPPort**.|  
  
4.  Haga clic en **Aceptar** para guardar la configuración.  
  
#### <a name="to-start-the-application"></a>Para iniciar la aplicación  
  
1.  Desde la consola de administración de BizTalk Server, haga clic en **EAISolution**y, a continuación, haga clic en **iniciar**.  
  
2.  En el cuadro de diálogo, haga clic en **iniciar**.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha configurado e iniciado la aplicación EAIApplication.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Se probará cómo la solución EAI procesa mensajes en [paso 3: probar la solución](../core/step-3-test-the-solution2.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Implementar los proyectos](../core/step-1-deploy-the-projects.md)   
 [Paso 3: Probar la solución](../core/step-3-test-the-solution2.md)