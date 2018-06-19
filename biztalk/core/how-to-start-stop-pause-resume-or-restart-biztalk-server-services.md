---
title: Pasos para reiniciar los servicios, o apagar | Documentos de Microsoft
description: Iniciar, detener, pausar, reanudar o reiniciar el servidor de BizTalk services, o apagar el equipo de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d6449ba-2892-49c6-a697-847608d10ec5
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9860625480c2c3e469736989415b4e1510cf6707
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973410"
---
# <a name="restart-biztalk-services-or-shut-down-the-biztalk-server"></a>Reiniciar servicios de BizTalk, o apagar el servidor BizTalk Server

En la tabla siguiente se enumeran los servicios de BizTalk Server que se pueden iniciar, detener, pausar, reanudar o reiniciar:  
  
|Nombre|Descripción|Tipo de inicio|Dependencias|  
|----------|-----------------|------------------|------------------|  
|Servicio de BizTalk grupo:  *\<BizTalkServerApplication\>*|Proporciona el servicio de aplicaciones de BizTalk Server.|Automático|-Servicio de inicio de sesión único (SSO) Enterprise<br />: El registro de eventos<br />-Llamada a procedimiento remoto (RPC)|  
|Servicio de inicio de sesión único (SSO) empresarial|Proporciona servicios de inicio de sesión único a aplicaciones empresariales.|Automático|Con servidor SQL Server instalado localmente:<br /><br /> -Aplicación del sistema COM +<br />-Llamada a procedimiento remoto (RPC)<br />-SQL Server (MSSQLSERVER)<br /><br /> Con servidor SQL Server instalado de forma remota:<br /><br /> -Aplicación del sistema COM +<br />-Llamada a procedimiento remoto (RPC) None|  
|Servicio de actualización de motor de reglas|Notifica a los usuarios acerca de la implementación o anulación de implementación de directivas.|Automática|Ninguno|  
  
 
## <a name="start-stop-pause-resume-or-restart-a-biztalk-server-service"></a>Iniciar, detener, pausar, reanudar o reiniciar un servicio de BizTalk Server  
 Puede iniciar, detener, pausar, reanudar o reiniciar un servicio de BizTalk Server mediante Services.msc, o mediante el símbolo del sistema.

### <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe ser miembro del grupo de administradores en el equipo local, o tener delegada la autoridad correspondiente. Si el equipo forma parte de un dominio, los miembros del grupo de administradores de dominio podrían llevar a cabo este procedimiento. Como práctica de seguridad recomendada, considere la posibilidad de utilizar la opción Ejecutar para realizar este procedimiento. 
  
### <a name="use-services-in-control-panel"></a>Usar los servicios en el Panel de Control  
  
1.  Abra Servicios. Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **services.msc**.  
  
2.  Haga clic en el servicio de BizTalk Server apropiado y, a continuación, haga clic en **iniciar**, **detener**, **pausa**, **reanudar**, o  **Reinicie**.  
  
### <a name="use-a-command-prompt"></a>Utilice un símbolo del sistema  
  
1.  En el menú Inicio, haga clic en **símbolo**, seleccione **más**y seleccione **ejecutar como administrador**
  
2.  Escriba uno de los siguientes valores, donde *ServiceName* es el nombre del servicio de BizTalk Server que desea iniciar, detener, pausar o reanudar:  
  
    -   Para iniciar un servicio, escriba:  
  
         **Net start** *ServiceName*  
  
    -   Para detener un servicio, escriba:  
  
         **net stop** *ServiceName*  
  
    -   Para pausar un servicio, escriba:  
  
         **net pause** *ServiceName*  
  
    -   Para reanudar un servicio, escriba:  
  
         **NET continuar** *ServiceName*  

    |Servicio de BizTalk|ServiceName|  
    |---|---|  
    |Grupo de BizTalk del servicio de BizTalk: BizTalkServerApplication|btssvc$biztalkserverapplication|  
    |Servicio de inicio de sesión único (SSO) empresarial|Entsso|  
    |Servicio de actualización de motor de reglas|ruleengineupdateservice|
  
## <a name="shut-down-biztalk-server"></a>Apagar el servidor BizTalk Server  

### <a name="prerequisites"></a>Requisitos previos  
-   Inicie sesión con una cuenta que sea miembro del grupo de administradores locales en el servidor de BizTalk que desea apagar. Esto es necesario para poder detener los servicios.  
-   Inicie sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server o grupo de operadores de BizTalk Server. 

### <a name="task-overview"></a>Información general sobre tareas
1.  Realice una detención parcial de cada aplicación activa para deshabilitar las ubicaciones de recepción y detener las orquestaciones y los puertos de envío. Solo debe detener una aplicación completamente si va a quitarla o implementarla nuevamente. Para obtener más información, consulte [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).  
  
2.  Detenga las instancias de host. Para obtener más información, consulte [cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md).  
  
3.  Apague los servicios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Vea **cómo iniciar, detener, pausar, reanudar o reiniciar los servicios de BizTalk Server** (en este tema).
  
4.  Apague Internet Information Services (IIS) o detenga los sitios web y los grupos de aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si va a apagar el servidor completamente, puede omitir este paso. Si detiene [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar el mantenimiento o para implementar o anular la implementación de una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe realizar este paso. Si solo detiene los sitios web y los grupos de aplicaciones asociados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el resto de procesos relacionados con IIS se seguirán ejecutando.  
  
     El procedimiento de este paso depende, en parte, de la versión de IIS que se esté usando. IIS 6 permite detener sitios web y grupos de aplicaciones. Con IIS 6, también se puede detener el Servicio de administración de IIS para apagar toda la actividad de IIS, incluidos los grupos de aplicaciones y los sitios web. IIS 7.0 es más modular que IIS 6.0, y no tiene un conmutador único que se pueda usar para detener todas las actividades de IIS 7.0, por lo que deberá detener los sitios web y los grupos de aplicaciones por separado.  
  
     Para obtener una lista de grupos de aplicaciones y aplicaciones virtuales (sitios Web y servicios Web) utilizadas por BizTalk Server, vea [configurar BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).  
  
 Para obtener información sobre cómo iniciar y detener los grupos de aplicaciones en IIS, consulte [http://go.microsoft.com/fwlink/?LinkID=140513](http://go.microsoft.com/fwlink/?LinkID=140513).  
  
 Para obtener información sobre cómo iniciar y detener el servidor Web en IIS, consulte [http://go.microsoft.com/fwlink/?LinkId=140695](http://go.microsoft.com/fwlink/?LinkId=140695).  
  
## <a name="see-also"></a>Vea también  
 [Cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md)   
 [Cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md)   