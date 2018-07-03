---
title: Mantenimiento de la confiabilidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09cdce13-a75b-44d7-8388-7a868bb51c69
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faf58e24442d2a17bace7b0d56393d1c793b9cd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985677"
---
# <a name="maintaining-reliability"></a>Mantenimiento de la confiabilidad
Esta sección proporciona información acerca de cómo resolver problemas de confiabilidad con un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema. Estos problemas se pueden detectar mediante las comprobaciones de mantenimiento rutinario que se realizan en el [listas de comprobación de mantenimiento de rutina](../technical-guides/routine-maintenance-checklists.md) sección de este documento.  

 Además de los temas de esta sección, otros temas en este documento trata problemas de confiabilidad. Estos temas se muestran en [secciones relacionadas](../technical-guides/maintaining-reliability.md#BKMK_Related) a continuación.  

## <a name="testing-group-failover"></a>Probar la conmutación por error de grupo  
 Realice los procedimientos de esta sección como parte de las comprobaciones de confiabilidad que se debe realizar mensuales. Estos procedimientos incluyen pruebas de la directiva de conmutación por error de grupo y comprobar si pueden conmutar por error los recursos del grupo.  

> [!NOTE]  
>  Si el equipo está unido a un dominio, los miembros del grupo Administradores del dominio deben ser capaz de llevar a cabo este procedimiento.  

> [!NOTE]  
>  Para llevar a cabo los procedimientos de esta sección, debe ser iniciado sesión como miembro del grupo Administradores en el equipo local, o bien tener delegada la autoridad adecuada.  

 Realice los pasos siguientes para probar la conmutación por error de grupo en equipos que ejecutan Windows Server 2008.  

#### <a name="to-test-a-group-failover-policy"></a>Para probar una directiva de conmutación por error de grupo  

1.  Asegúrese de que ha instalado el **agrupación en clústeres de conmutación por error** característica en al menos dos equipo que ejecute Windows Server 2008 con el fin de crear un clúster de conmutación por error de Windows de dos nodos. Para obtener instrucciones sobre cómo instalar esta característica, consulte [instalar la característica de clústeres de conmutación por error](http://go.microsoft.com/fwlink/?LinkId=157259) (http://go.microsoft.com/fwlink/?LinkId=157259).  

2.  Abra Administración de clúster de conmutación por error, haga clic en **iniciar**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **administración del clúster de conmutación por error**.  

3.  En el árbol de consola, expanda el nodo del clúster, el **servicios y aplicaciones** nodo, haga clic en la instancia en clúster de conmutación por error y, a continuación, haga clic en la aplicación **propiedades**.  

4.  En el **conmutación por error** pestaña, establezca **máximo de errores en el período especificado** en 0 y, a continuación, haga clic en **Aceptar**.  

5.  En el árbol de consola, expanda el **servicios y aplicaciones** nodo.  

6.  En el panel de detalles, haga clic en un recurso y, a continuación, haga clic en **propiedades**.  

7.  En el **directivas** pestaña, establezca **número máximo de reinicios en el período especificado** en 0 y, a continuación, haga clic en **Aceptar**.  

8.  Haga clic en el recurso, haga clic en **más acciones**y, a continuación, haga clic en **simular un error de este recurso**. Compruebe si el grupo reacciona en función de la directiva que especificó en el paso anterior.  

9. Haga clic en la instancia en clúster de conmutación por error y, a continuación, haga clic en la aplicación **propiedades**.  

10. En el **conmutación por error** pestaña, establezca **máximo de errores en el período especificado** a 1 y, a continuación, haga clic en **Aceptar**.  

11. Haga clic en el recurso y seleccione **conectar este recurso**.  

#### <a name="to-test-whether-group-resources-can-fail-over"></a>Para comprobar si puede conmutar por error del grupo de recursos  

1.  Asegúrese de que ha instalado el **agrupación en clústeres de conmutación por error** característica en el equipo que ejecuta Windows Server 2008. Para obtener instrucciones sobre cómo instalar esta característica, consulte [instalar la característica de clústeres de conmutación por error](http://go.microsoft.com/fwlink/?LinkId=157259) (http://go.microsoft.com/fwlink/?LinkId=157259).  

2.  Abra Administración de clúster de conmutación por error, haga clic en **iniciar**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **administración del clúster de conmutación por error**.  

3.  En el árbol de consola, expanda el nodo del clúster, el **servicios y aplicaciones** nodo y, a continuación, haga clic en la instancia en clúster de conmutación por error de la aplicación.  

4.  En el **acción** menú, haga clic en **mover este servicio o aplicación a otro nodo**y, a continuación, haga clic en el nodo al que la aplicación de conmutación por error.  

5.  En el **confirme la acción** diálogo cuadro, elija la opción de mover la aplicación en el nodo seleccionado.  

6.  Asegúrese de que el nodo al que se ha movido la aplicación aparece en el **propietario actual** en el panel de detalles de la aplicación.  

##  <a name="BKMK_BTSGrp"></a> Asegurarse de varios servidores forman parte de un grupo de BizTalk  
 Para garantizar la confiabilidad de un sistema, al menos dos servidores físicos de BizTalk deben formar parte del grupo de BizTalk.  Si necesita agregar un servidor a un grupo de BizTalk, tenga en cuenta lo siguiente:  

- Un servidor sólo se puede asociar con un grupo de BizTalk. Si un servidor pertenece ya a otro grupo, debe quitar primero ese servidor del grupo actual para poder agregarlo al grupo nuevo. Para obtener más información sobre cómo quitar un servidor de un grupo de BizTalk, vea "Cómo para quitar un servidor de un grupo" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkId=155577 ](http://go.microsoft.com/fwlink/?LinkId=155577).  

- Los grupos de BizTalk asociados con servidores diferentes en un entorno de BizTalk Server no interactúan si no es para intercambiar mensajes.  

- El motor de tiempo de ejecución de BizTalk Server debe estar instalado en el equipo que desea agregar al grupo de BizTalk.  

> [!NOTE]  
>  Para llevar a cabo los procedimientos de este tema, debe haber iniciado sesión como miembro del grupo de administradores de SSO y como miembro del grupo Administradores de Windows.  

#### <a name="to-determine-whether-at-least-two-physical-biztalk-servers-are-part-of-the-biztalk-group"></a>Para determinar si al menos dos servidores BizTalk físicos forman parte del grupo de BizTalk  

1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **iniciar**, seleccionando **todos los programas**, seleccionando **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y, a continuación, haga clic en **Administración de BizTalk Server**.  

2. Expanda el [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] nodo, expanda el **grupo de BizTalk** nodo y, a continuación, expanda el **configuración de plataforma** nodo.  

3. Haga clic en el **servidores** nodo. Compruebe que aparece más de un servidor en el **servidores** panel.  

   > [!NOTE]  
   >  Para ver información acerca del servidor, haga clic en el servidor, seleccione **vista**y, a continuación, haga clic en **página concentrador de grupo**.  

#### <a name="to-add-a-server-to-a-biztalk-group"></a>Para agregar un servidor a un grupo de BizTalk  

1. En el equipo que desea agregar a un grupo de BizTalk, haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y, a continuación, haga clic en  **Configuración de BizTalk Server**.  

2. En **configuración de Microsoft BizTalk Server 2010**, seleccione **configuración personalizada**.  

3. En **el nombre del servidor de base de datos**, escriba el nombre de SQL server para el grupo de BizTalk que se va a unir el servidor.  

4. En **credencial de servicio**, escriba el nombre de usuario correspondiente y la contraseña que use los servicios y, a continuación, haga clic en **configurar**.  

5. En el árbol de navegación en el lado izquierdo de la pantalla, haga clic en **SSO empresarial**.  

6. En el **Enterprise Single Sign-On** página, haga clic en **unir un sistema SSO existente**.  

   > [!NOTE]  
   >  Asegúrese de que el nombre del servidor y el nombre de la base de datos señalen al servidor de base de datos SSO principal para el grupo de BizTalk que se va a unir el servidor.  

7. En el árbol de navegación en el lado izquierdo de la pantalla, haga clic en **grupo**.  

8. En el **grupo** página, haga clic en **unirse a un grupo de BizTalk existente**.  

   > [!NOTE]  
   >  Asegúrese de que el nombre del servidor y el nombre de la base de datos señalen a las bases de datos para el grupo de BizTalk que se va a unir el servidor.  

9. En la barra de menús, haga clic en **aplicar configuración** configurar Enterprise Single Sign-On y el grupo en este equipo.  

##  <a name="BKMK_Related"></a> Secciones relacionadas  

- Para obtener información sobre la comprobación de discos con errores en el RAID de hardware, vea "Ver propiedades del disco" en la Ayuda del producto Windows Server 2003 en [ http://go.microsoft.com/fwlink/?linkid=104161 ](http://go.microsoft.com/fwlink/?linkid=104161).  

- Para obtener información acerca de la comprobación manual de los mensajes suspendidos, consulte "Investigating orquestación, puerto y errores de mensaje" en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda en [ http://go.microsoft.com/fwlink/?LinkID=154512 ](http://go.microsoft.com/fwlink/?LinkID=154512).  

- Para obtener información sobre cómo asegurarse de que cada host tiene una instancia en ejecución en al menos dos servidores físicos de BizTalk, consulte [alta disponibilidad para Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md).  

- Para obtener información sobre cómo asegurarse de que cada host tiene una instancia en ejecución en al menos dos servidores físicos de BizTalk, consulte [escalado horizontal de Hosts recibir](../technical-guides/scaling-out-receiving-hosts.md).  

- Para obtener información sobre cómo asegurarse de que para servicios agrupados en clústeres de conmutación por error se ha probado, consulte [agrupación en clústeres el servidor secreto principal](../technical-guides/clustering-the-master-secret-server.md).  

- Para obtener información sobre cómo asegurarse de que las bases de datos de BizTalk están agrupados en servicios de SQL, vea [agrupación en clústeres el BizTalk Server2](../technical-guides/clustering-the-biztalk-server-databases2.md).  

- Para obtener información acerca de cómo determinar si se está usando cualquier código inestable (que requieren los hosts independientes), consulte [alta disponibilidad para Hosts de BizTalk](../technical-guides/high-availability-for-biztalk-hosts.md).  

- Para obtener información acerca de cómo realizar pruebas funcionales de todas las nuevas aplicaciones de BizTalk, consulte [probar una aplicación](../technical-guides/testing-an-application.md)
