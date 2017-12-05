---
title: "Mediante el Asistente para configuración de MQSAgent COM + | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mqsagent.wizard
helpviewer_keywords:
- MQSeries adapters, MQSAgent COM+ Configuration Wizard
- configuring [MQSeries adapters], MQSAgent COM+ Configuration Wizard
- MQSAgent COM+ Configuration Wizard
ms.assetid: f106700a-7f57-4c83-9344-6525fc10544d
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6e8b625bcc3accbefda193c52459616691c265
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="using-the-mqsagent-com-configuration-wizard"></a>Mediante el Asistente para configuración de MQSAgent COM +
El Asistente para configuración de MQSAgent COM+ permite configurar MQSAgent, la parte de aplicación COM+ (componente MQSeries) del adaptador. El asistente define la identidad de aplicación del componente, así como el nombre de función y los usuarios incluidos en dicha función. El nombre del componente MQSAgent COM + creado con el Asistente de configuración de MQSAgent COM + es **MQSAgent2**.  
  
> [!NOTE]
>  La aplicación MQSAgent COM+ se admite en un servidor de Windows de 64 bits. Se ejecutará como proceso de 32 bits en WOW64. Un equipo basado en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se ejecute en una versión de 64 bits de Windows Server se puede comunicar con un equipo remoto de 32 bits que tenga instalado MQSAgent.  
  
> [!NOTE]
>  MQSeries Agent y el ejecutable del Asistente de configuración de MQSAgent COM + **MQSConfigWiz.exe** no se instalan si actualiza desde BizTalk Server 2009 a BizTalk Server. Después de actualizar a BizTalk Server de BizTalk Server 2009 vuelva a ejecutar el programa de instalación, seleccione la **modificar** opción y seleccione MQSeries Agent en Software adicional para instalar estos componentes.  
  
## <a name="to-set-the-application-identity"></a>Para definir la identidad de la aplicación  
  
-   Use la **identidad de aplicación** página del Asistente configuración de MQSAgent COM + para configurar la identidad de aplicación para MQSAgent como se indica a continuación:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Usuario interactivo**|Utilizar la cuenta de inicio de sesión actual como identidad de la aplicación.|  
    |**Servicio local**|Definir la identidad de la aplicación con una cuenta de servicio integrada.|  
    |**Servicio de red**|Definir la identidad de la aplicación con una cuenta de servicio integrada con acceso a la red.|  
    |**Este usuario**|Definir la identidad de aplicación con el nombre de usuario indicado.|  
  
> [!NOTE]
>  Se recomienda no utilizar cuentas con permisos administrativos para definir la identidad de la aplicación. La cuenta deberá tener el mínimo de permisos necesarios: permisos de lectura y escritura para las colas de MQSeries.  
  
## <a name="to-name-the-role-and-add-users-to-it"></a>Para dar un nombre a la función y agregarle usuarios  
  
-   Use la **nombre de la función** página del Asistente configuración de MQSAgent COM + para asignar un nombre y los usuarios a la función, como se indica a continuación:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de rol**|Escriba el nombre del rol.|  
    |**Usuarios**|Ver los usuarios que pertenecen a la función.|  
    |**Agregar**|Agregar usuarios a la función. Se trata de cuentas de servicio de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que usan el adaptador.|  
  
> [!NOTE]
>  Agregue a la función sólo las cuentas que necesitan tener acceso al adaptador.  
  
## <a name="to-set-the-msdtc-security-configuration-on-the-windows-server-2008-computer-to-no-authentication-required"></a>Para definir la configuración de seguridad de MSDTC del equipo de Windows Server 2008 como No se requiere autenticación  
 Si la aplicación MQSAgent COM + está instalada en un [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] equipo y el adaptador de MQSeries (que se instala con BizTalk Server) se instala en un [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] equipo, la configuración de seguridad de MSDTC en el [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] equipo debe establecerse en **No se requiere autenticación**. Siga estos pasos para establecer la configuración de seguridad de MSDTC como No se requiere autenticación:  
  
1.  Haga clic en **iniciar** y, a continuación, haga clic en **el Panel de Control**.  
  
2.  Haga doble clic en **herramientas administrativas**.  
  
3.  Haga doble clic en **servicios de componentes** para iniciar el **servicios de componentes** interfaz de administración.  
  
4.  Expanda **servicios de componentes**, expanda **equipos**y, a continuación, expanda **Mi PC**.  
  
5.  Haga clic en **Mi PC** y haga clic en el **propiedades** elemento de menú.  
  
6.  En el **Mi PC** cuadro de diálogo, haga clic en el **MSDTC** ficha y, a continuación, haga clic en **configuración de seguridad**.  
  
7.  En el **configuración de seguridad** cuadro de diálogo, en la **comunicación con el Administrador de transacciones** sección, seleccione **No se requiere autenticación**. Si aparece un cuadro de diálogo, haga clic en **Sí** reiniciar el Service DTC MS.  
  
8.  Una vez reiniciado el servicio MS DTC, haga clic en **Aceptar** y haga clic en **Aceptar** otra vez para cerrar el **Mi PC** cuadro de diálogo.  
  
9. Cerrar la **servicios de componentes** interfaz de administración.  
  
## <a name="to-configure-the-mqsagent-runtime-components-to-run-under-an-alternative-set-of-credentials"></a>Para configurar los componentes de tiempo de ejecución de MQSAgent para ejecutarlos en un conjunto de credenciales alternativas  
 La aplicación MQSAgent COM+ incluye componentes tanto para la administración, como para el tiempo de ejecución. Si desea separar esta funcionalidad en diferentes aplicaciones COM+ por motivos de seguridad, siga estos pasos en el equipo en el que se ha instalado la aplicación MQSAgent COM+:  
  
1.  Habilite los cambios para el componente MQSAgent COM+.  
  
    -   Haga clic en **iniciar** y, a continuación, haga clic en **el Panel de Control**.  
  
    -   Haga doble clic en **herramientas administrativas**.  
  
    -   Haga doble clic en **servicios de componentes** para iniciar el **servicios de componentes** interfaz de administración.  
  
    -   Expanda **servicios de componentes**, expanda **Mi PC**, expanda **aplicaciones COM +**, haga clic en el **MQSAgent2** aplicación COM + y, a continuación, haga clic en **propiedades**.  
  
    -   Haga clic en el **avanzadas** pestaña y desactive la opción **Deshabilitar cambios**.  
  
    -   Haga clic en **Aceptar**.  
  
2.  Cree una nueva aplicación COM+ para los componentes de tiempo de ejecución de MQSAgent.  
  
    -   Haga clic en **aplicaciones COM +**, haga clic en **New**, **aplicación** para mostrar la **Asistente para instalación de aplicación COM +** y haga clic en  **Siguiente**.  
  
    -   Haga clic en **crear una aplicación vacía**.  
  
    -   Escriba el nombre **MQSAgent2RunTime**, deje la opción predeterminada para **aplicación de servidor** habilitado y haga clic en **siguiente**.  
  
    -   Seleccione la opción de **este usuario**, escriba la información de cuenta correspondiente y haga clic en **siguiente**.  
  
        > [!NOTE]
        >  Esta cuenta debe tener **conectar** y **colocar** o **obtener** permisos en IBM WebSphere MQ adecuado para las colas de Windows. Puede establecer los permisos adecuados para esta cuenta con la **setmqaut** comando disponible con IBM WebSphere MQ. Para obtener más información sobre la **setmqaut** comando consulte la documentación de IBM WebSphere MQ.  
  
    -   Haga clic en **siguiente** en el **agregar funciones de aplicación** cuadro de diálogo.  
  
    -   Haga clic en **siguiente** en el **agregar usuarios a funciones** cuadro de diálogo.  
  
    -   Haga clic en **Finalizar**.  
  
3.  Mueva los componentes de ejecución a la nueva aplicación COM+  
  
    -   Expanda el **MQSAgent2** aplicación COM +.  
  
    -   Expanda **componentes**.  
  
    -   Haga clic en el **MQSAgent2.MQSAgent.1** componente y haga clic en **mover** para mostrar la **mover componentes (s)** cuadro de diálogo.  
  
    -   Seleccione **MQSAgent2RunTime** en **seleccione un destino** y haga clic en **Aceptar**.  
  
    -   Repita estos pasos para la **MQSAgent2.MQSBroker.1** y **MQSAgent2.MQSProxy.1** componentes.  
  
## <a name="see-also"></a>Vea también  
 [Controladores de recepción y envío de cómo configurar el adaptador de MQSeries](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md)   
 [Configuración del adaptador de MQSeries](../core/configuring-the-mqseries-adapter.md)