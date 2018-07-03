---
title: Ejecutando Orchestrations2 | Microsoft Docs
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
- creating strong name keys
- compiling orchestrations
- host instances, stopping and restarting
- deployment, orchestrations
- orchestrations, compiling
- orchestrations, deploying
- stopping host instances
- restarting host instances
ms.assetid: a098d552-d302-44f6-9af9-d77d16549fd3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c299486c8ca43b34ba93ce434245b52b30e567aa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981053"
---
# <a name="running-orchestrations"></a>Orquestaciones en ejecución
Los procedimientos siguientes describen cómo generar, implementar, enlazar e iniciar una orquestación.  
  
## <a name="creating-a-strong-name-key"></a>Creación de clave de nombre seguro  
  
#### <a name="to-create-a-strong-name-key"></a>Para crear una clave de nombre seguro  
  
1. Abra un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema.  
  
2. Vaya al directorio de un proyecto existente y presione ENTRAR.  
  
    Por ejemplo:  
  
    **\<unidad\>: \Adapter_Install\biztalk\my_project**  
  
3. Escriba lo siguiente en el símbolo del sistema y presione ENTRAR:  
  
    `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a>Compilación e implementación de una orquestación  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a>Para compilar e implementar una orquestación  
  
1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el **SSOSchedule** del proyecto y seleccione **propiedades**.  
  
2. Haga clic en **propiedades comunes**y expanda el **ensamblado** nodo.  
  
3. Escriba la ruta de acceso a SSOSchedule.snk en el **archivo clave de ensamblado** cuadro de texto.  
  
4. Compruebe que Configuration Properties\Deployment\Server sea un punto (.) o el nombre del equipo y, a continuación, haga clic en **Aceptar**.  
  
5. En el Explorador de soluciones, haga clic en **SSOSchedule**y, a continuación, haga clic en **recompilar**.  
  
6. Haga clic en **SSOSchedule**y, a continuación, haga clic en **implementar**.  
  
## <a name="starting-the-orchestration"></a>Inicio de la orquestación  
  
#### <a name="to-start-the-orchestration"></a>Para iniciar la orquestación  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server.**  
  
2. En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda deseado aplicación y, a continuación, haga clic en **orquestaciones**.  
  
3. En el panel de detalles, haga clic en la orquestación y haga clic en **iniciar**.  
  
## <a name="stopping-and-restarting-a-host-instance"></a>Detención y reinicio de una instancia de host  
 Después de implementar el ejemplo, debe reiniciar la instancia de host.  
  
#### <a name="to-stop-and-restart-a-host-instance"></a>Para detener y reiniciar una instancia de host  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server.**  
  
2. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en  **Las instancias de host**.  
  
3. En el panel derecho, haga clic en la instancia de host (por ejemplo, el nombre del equipo) y haga clic en **detener**.  
  
    El estado de la instancia de host cambia a **detenido**.  
  
4. En el panel derecho, haga clic en la instancia de host y haga clic en **iniciar**.  
  
    El estado de la instancia de host cambia a **Inicio pendiente**.  
  
    Para cambiar el estado a **ejecutando** y haga clic en **actualizar**, o haga clic en la instancia de host y, a continuación, haga clic en **actualizar**.  
  
## <a name="see-also"></a>Vea también  
 [Proteger el adaptador](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)