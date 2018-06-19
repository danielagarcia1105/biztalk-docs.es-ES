---
title: Ejecuta Orchestrations1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strong name keys, creating
- orchestrations
- host instances, stopping and restarting
- orchestrations, compiling
- orchestrations, deploying
ms.assetid: b992bdba-630d-4f28-aca8-c568f3c27968
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c215009d6b911831c74ac22b2c03ceae45e74a62
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972738"
---
# <a name="running-orchestrations"></a>Orquestaciones en ejecución
Los procedimientos siguientes describen cómo generar, implementar, enlazar e iniciar una orquestación.  
  
## <a name="creating-a-strong-name-key"></a>Creación de clave de nombre seguro  
  
#### <a name="to-create-a-strong-name-key"></a>Para crear una clave de nombre seguro  
  
1.  Inicie un símbolo del sistema de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
2.  Cambie los directorios a un proyecto existente, por ejemplo, \<unidad\>: \Adapter_Install\biztalk2010\my_project.  
  
3.  Escriba lo siguiente en el símbolo del sistema y presione ENTRAR:  
  
     `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a>Compilación e implementación de una orquestación  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a>Para compilar e implementar una orquestación  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto SSOSchedule y seleccione **propiedades**.  
  
2.  Haga clic en **propiedades comunes**y expanda el **ensamblado** nodo.  
  
3.  Escriba la ruta de acceso a SSOSchedule.snk en el **archivo de clave de ensamblado** cuadro de texto.  
  
4.  Compruebe que Configuration Properties\Deployment\Server contiene un punto (.) o el nombre del equipo y haga clic en **Aceptar**.  
  
5.  En el Explorador de soluciones, haga clic en **SSOSchedule**y haga clic en **volver a generar**.  
  
6.  Haga clic en el **SSOSchedule**y haga clic en **implementar**.  
  
## <a name="starting-the-orchestration"></a>Inicio de la orquestación  
  
#### <a name="to-start-the-orchestration"></a>Para iniciar la orquestación  
  
1.  En la consola de administración de BizTalk, seleccione la orquestación que desea iniciar.  
  
2.  Haga clic en la orquestación y haga clic en **iniciar**.  
  
## <a name="stopping-and-restarting-a-host-instance"></a>Detención y reinicio de una instancia de host  
 Después de implementar el ejemplo, debe reiniciar la instancia de host.  
  
#### <a name="to-stop-and-restart-a-host-instance"></a>Para detener y reiniciar una instancia de host  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y seleccione **administración de BizTalk Server.**  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga doble clic en el **Microsoft BizTalk Server (local)** nodo y expanda **Hosts**.  
  
3.  En el panel izquierdo, seleccione la **BizTalkServerApplication**.  
  
4.  En el panel derecho, haga clic en la instancia de host (por ejemplo, el nombre del equipo) y haga clic en **detener**.  
  
     El estado de la instancia de host cambia a **detenido**.  
  
5.  En el panel derecho, haga clic en la instancia de host y haga clic en **iniciar**.  
  
     El estado de la instancia de host cambia a **Inicio pendiente**.  
  
     Para cambiar el estado a **ejecutando**, haga clic en **actualizar**, o haga clic en la instancia de host y, a continuación, haga clic en **actualizar**.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad en el adaptador](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)