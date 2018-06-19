---
title: Cómo agrupar SSO y un Host de BizTalk en el mismo Group1 clúster | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 413cc8f4-f343-4c1c-8b79-3b15cb4c101d
caps.latest.revision: 44
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a72b6e343d2e417a718c238181fefdea8e5cceba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250628"
---
# <a name="how-to-cluster-sso-and-a-biztalk-host-in-the-same-cluster-group"></a>Cómo agrupar SSO y un host de BizTalk en el mismo grupo de clúster
Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es posible agrupar uno o varios hosts de BizTalk y el servicio de inicio de sesión único empresarial (SSO) en el mismo clúster de Windows Server.  
  
> [!NOTE]
>  La correcta puesta en práctica de esta estrategia exige la creación de alguna instancia de host de BizTalk y del servicio SSO como recursos de clúster en el mismo grupo de clústeres.  
  
 El uso de la organización por clústeres de Windows con uno o varios hosts de BizTalk y SSO se suele incluirse en una de las siguientes categorías:  
  
1.  Agrupación en clústeres del servidor secreto principal de SSO y de uno o varios hosts de BizTalk en el mismo grupo de clústeres.  
  
     En este escenario, la dependencia entre los hosts de BizTalk en clúster y el servicio SSO agrupado se mantiene por lo que si el grupo de clúster es la conmutación por error, todos los recursos se muevan con el grupo.  
  
     Si el servicio SSO está configurado como un recurso en clúster en un equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe crear un servicio web de IIS en clúster en el mismo grupo de clústeres. Esto debe hacerse para asegurarse de que todas las instancias de host aislado se ejecuten en el nodo de clúster en el que se ejecuta el servicio SSO. Con esto se garantiza que los adaptadores que se ejecuten en una instancia de host aislado tendrán acceso al servicio SSO, puesto que las instancias de host aislado se ejecutan en IIS.  
  
    > [!NOTE]
    >  Si está ejecutando una instancia de un host de BizTalk en el mismo nodo de clúster que ejecuta una instancia en clúster del servicio SSO, la instancia en clúster del servicio SSO no se conmutarán por error a menos que se ha detenido la instancia del host de BizTalk. Una instancia del host de BizTalk mantiene una dependencia con la instancia agrupada del servicio SSO se ejecuta en el nodo del clúster e impide que la instancia del servicio SSO en clúster de conmutación por error. Por ello, se recomienda no crear una instancia que no está en clúster de un host de BizTalk para que se ejecute en el mismo nodo de clúster en el que se ejecuta una instancia en clúster del servicio SSO.  
  
2.  Agrupación en clúster del servicio SSO (servidor secreto no principal) y uno o varios hosts de BizTalk en el mismo grupo de clústeres. En este escenario, se requiere la disponibilidad de un servidor secreto principal remoto. En este escenario, la dependencia entre los hosts de BizTalk en clúster y el servicio SSO en clúster se mantiene para que, en el caso de que se efectúe una conmutación por error del grupo de clústeres, todos los recursos se muevan con el grupo.  
  
     Si el servicio SSO está configurado como un recurso en clúster en un equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe crear un servicio web de IIS en clúster en el mismo grupo de clústeres. Esto debe hacerse para asegurarse de que todas las instancias de host aislado se ejecuten en el nodo de clúster en el que se ejecuta el servicio SSO. Con esto se garantiza que los adaptadores que se ejecuten en una instancia de host aislado tendrán acceso al servicio SSO, puesto que las instancias de host aislado se ejecutan en IIS.  
  
    > [!NOTE]
    >  Si una instancia de host de BizTalk que no está en clúster se ejecuta en el mismo nodo de clúster en el que se ejecuta una instancia en clúster del servicio SSO, entonces no será posible efectuar la conmutación por error de la instancia en clúster del servicio SSO, a menos que se detenga la instancia que no está en clúster del host de BizTalk. Una instancia que no está en clúster de host de BizTalk mantiene una dependencia con la instancia en clúster del servicio SSO que se ejecuta en el nodo de clúster e impide la conmutación por error de ésta. Por este motivo, se recomienda que no cree una instancia de un host de BizTalk para que se ejecute en el mismo nodo de clúster que ejecuta una instancia en clúster del servicio SSO.  
  
3.  Agrupación en clúster de uno o varios hosts de BizTalk en un clúster de Windows Server sin agrupar en clúster el servicio SSO. En este escenario, uno o varios hosts de BizTalk están configurados como recursos de clúster, pero el servicio SSO no está configurado como un recurso en clúster. Este diseño proporciona una alta disponibilidad de los hosts de BizTalk en clúster, aunque no ocurre lo mismo con el servicio SSO. En este escenario, si se produce un error en el servicio SSO de un nodo, también se producirá un error en los componentes de BizTalk Server que dependen de SSO. Para obtener más información acerca de cómo configurar un host de BizTalk Server como un recurso de clúster vea [cómo configurar un Host de BizTalk como recurso de clúster](http://msdn.microsoft.com/library/6e9aab00-7623-4175-bb12-ba916306f1e3).  
  
 Los siguientes procedimientos describen los pasos que deben seguirse para agrupar en clúster un host de BizTalk y el servicio SSO en el mismo clúster de Windows Server.  
  
### <a name="to-cluster-a-biztalk-host-and-the-sso-master-secret-server-on-the-same-windows-server-cluster"></a>Para agrupar un host de BizTalk y el servidor secreto principal de SSO en el mismo clúster de Windows Server  
  
1.  Si el clúster no está configurado con un recurso Coordinador de transacciones distribuidas (MSDTC) en clúster, agrupe MSDTC en un clúster de conmutación por error de Windows Server siguiendo los pasos descritos en [lista de comprobación: crear un MS DTC Resource en un equipo con Windows Server 2008 Clúster de conmutación por error](http://go.microsoft.com/fwlink/p/?LinkID=129677) (http://go.microsoft.com/fwlink/p/?LinkID=129677).  
  
2.  Instalar y configurar el servicio SSO en el clúster de Windows Server siguiendo los pasos descritos en [cómo agrupar el servidor secreto principal](http://msdn.microsoft.com/library/59895616-4178-46d0-b9ff-95589b809ff5). Dado que BizTalk Server se ejecutará en el clúster de Windows Server, instale todos los componentes de BizTalk Server necesarios, aunque, en esta ocasión, tan solo se efectuará la configuración de los componentes de SSO.  
  
3.  Clúster IIS en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo siguiendo los pasos documentados en [970759 "configuración de IIS 7.0 en un Microsoft Windows Server 2008 failover cluster" del artículo de Microsoft Knowledge Base](http://go.microsoft.com/fwlink/p/?LinkId=152793) (http://go.microsoft.com/fwlink/p/?LinkId=152793). Cree el servicio web de IIS en clúster en el mismo grupo de clústeres del servicio SSO en clúster.  
  
4.  Mueva el grupo de clúster que contiene el servicio SSO en clúster en uno de los nodos del clúster e iniciar sesión en este nodo de clúster.  
  
5.  Inicie el programa de configuración de BizTalk Server y complete la configuración de BizTalk Server en este nodo de clúster. Puesto que es el primer equipo de BizTalk Server en el grupo, haga clic en **crear un nuevo grupo de BizTalk** al configurar el grupo de BizTalk.  
  
6.  Cuando la configuración de BizTalk Server se haya completado correctamente, mueva el grupo de clústeres que contiene el servicio SSO en clúster a otro nodo de clúster e inicie sesión en éste.  
  
7.  Inicie el programa de configuración de BizTalk Server y complete la configuración de BizTalk Server en este nodo de clúster. Haga clic en **unirse a un grupo de BizTalk existente** al configurar el componente de grupo de BizTalk en este nodo del clúster, y especifique el grupo de BizTalk que creó en el primer nodo.  
  
8.  Una vez completada correctamente la configuración de BizTalk Server, cree uno o más hosts de BizTalk agrupados siguiendo los pasos descritos en [cómo configurar un Host de BizTalk como recurso de clúster](http://msdn.microsoft.com/library/6e9aab00-7623-4175-bb12-ba916306f1e3).  
  
    > [!NOTE]
    >  En este escenario, todos los hosts de BizTalk deben crearse como recursos de clúster en el mismo grupo de clústeres que el del recurso del servicio SSO en clúster. Ejecuta una instancia de host de BizTalk no agrupada en un nodo del clúster de servidores de Windows que está agrupado el servicio SSO no es una configuración admitida. Esto se debe a que la instancia de host de BizTalk que no está en clúster no se llevará a cabo correctamente si el servicio SSO en clúster se ha conmutado por error a otro nodo debido a la dependencia de una instancia de host de BizTalk del servicio SSO.  
  
### <a name="to-cluster-a-biztalk-host-and-sso-non-master-secret-server-on-the-same-windows-server-cluster-when-the-sso-master-secret-server-is-remote"></a>Para agrupar un host de BizTalk y SSO (servidor secreto no principal) en el mismo clúster de Windows Server cuando el servidor secreto principal de SSO es remoto  
  
1.  Si el clúster no está configurado con un recurso Coordinador de transacciones distribuidas (MSDTC) en clúster, agrupe MSDTC en un clúster de conmutación por error de Windows Server siguiendo los pasos descritos en [lista de comprobación: crear un MS DTC Resource en un equipo con Windows Server 2008 Clúster de conmutación por error](http://go.microsoft.com/fwlink/p/?LinkID=129677) (http://go.microsoft.com/fwlink/p/?LinkID=129677).  
  
2.  Cree grupos de dominio con los nombres **administradores de SSO** y **administradores afiliados de SSO**. Para crear una instancia en clúster del servicio SSO, debe crear el **administradores de SSO** y **administradores afiliados de SSO** grupos como grupos de dominio.  
  
3.  Cree o designe una cuenta de dominio que sea miembro de la **administradores de SSO** grupo de dominio. El servicio SSO de cada nodo se configurará para iniciar la sesión como esta cuenta de dominio. Esta cuenta debe tener la **iniciar sesión como un servicio** en cada nodo del clúster.  
  
4.  Agregue la cuenta que usas para iniciar sesión durante el proceso de instalación y configuración para el dominio **administradores de SSO** grupo.  
  
    > [!IMPORTANT]
    >  Si no se completan los pasos 3 y 4, la configuración del servicio SSO no se llevará a cabo correctamente.  
  
5.  Inicie sesión en uno de los nodos de clúster e instale [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Seleccione la opción para iniciar el programa de configuración cuando haya finalizado correctamente la instalación.  
  
6.  Elija la **configuración personalizada** opción y escriba los valores adecuados para el **el nombre del servidor de base de datos**, **nombre de usuario** y **contraseña**campos. Después de escribir estos valores, haga clic en el **configurar** el botón para continuar.  
  
7.  Establezca las opciones siguientes para la característica SSO:  
  
    1.  Active la casilla junto a **habilitar Enterprise Single Sign-On en este equipo**.  
  
    2.  Haga clic en la opción de **unir un sistema SSO existente**.  
  
    3.  Especifique valores para el nombre de la base de datos y del servidor de la base de datos de SSO existentes.  
  
    4.  Indique la cuenta de servicio SSO existente al especificar la cuenta que se va a usar para el servicio de inicio de sesión único empresarial.  
  
8.  Puesto que este es el primer servidor de BizTalk Server en el grupo de elegir la opción de **crear un nuevo grupo de BizTalk** al configurar el componente de grupo de BizTalk.  
  
9. Especifique el resto de las opciones de configuración según corresponda y aplique la configuración de BizTalk Server a este nodo.  
  
10. Una vez que la configuración de BizTalk Server haya finalizado correctamente en el primer nodo, inicie sesión en el segundo nodo e instale [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Seleccione la opción para iniciar el programa de configuración cuando haya finalizado correctamente la instalación.  
  
11. Elija la **configuración personalizada** opción y, a continuación, escriba los valores adecuados para el **el nombre del servidor de base de datos**, **nombre de usuario** y **contraseña** campos. Después de escribir estos valores, haga clic en el **configurar** el botón para continuar.  
  
12. Establezca las opciones siguientes para la característica SSO:  
  
    1.  Active la casilla junto a **habilitar Enterprise Single Sign-On en este equipo**.  
  
    2.  Haga clic en **unir un sistema SSO existente**.  
  
    3.  Especifique valores para el nombre de la base de datos y del servidor de la base de datos de SSO existentes.  
  
    4.  Indique la cuenta de servicio SSO existente al especificar la cuenta que se va a usar para el servicio de inicio de sesión único empresarial.  
  
13. Elija la opción de **unirse a un grupo de BizTalk existente** al configurar el componente de grupo de BizTalk en este nodo del clúster, y especifique el grupo de BizTalk que creó en el primer nodo.  
  
14. Especifique el resto de las opciones de configuración según corresponda y aplique la configuración de BizTalk Server a este nodo.  
  
15. Una vez completada la configuración de BizTalk Server correctamente, siga los pasos que se detallan a continuación para agrupar en clúster el servicio SSO:  
  
    1.  Detenga el servicio SSO en cada uno de los nodos del clúster. Para ello, escriba el siguiente comando en un símbolo del sistema:  
  
        ```  
        net stop entsso  
        ```  
  
    2.  En la administración de clúster de conmutación por error, mueva todos los grupos de clústeres a un nodo e inicie sesión en este último.  
  
    3.  En el panel izquierdo, haga clic para seleccionar un servicio o aplicación en clúster que contenga un recurso de dirección IP y nombre de red. Este servicio o aplicación en clúster contendrá el servicio SSO en clúster y el host de BizTalk en clúster.  
  
        > [!NOTE]
        >  Un servicio SSO en clúster no necesita de forma explícita el uso de un recurso de disco físico en clúster en el mismo grupo.  
  
    4.  Haga clic en la aplicación o servicio en clúster, seleccione **agregar un recurso**y haga clic en **servicio genérico** para mostrar la **Asistente para nuevo recurso** cuadro de diálogo.  
  
    5.  En el **Seleccionar servicio** página de la **Asistente para nuevo recurso**, seleccione **Enterprise Single Sign-On Service**y, a continuación, haga clic en **siguiente**.  
  
    6.  En el **confirmación** página haga clic en **siguiente**.  
  
    7.  En el **resumen** página haga clic en **finalizar**. Aparecerá una instancia agrupada del servicio de inicio de sesión único de empresa en **otros recursos** en el panel central de la **administración de clúster de conmutación por error** interfaz.  
  
    8.  Haga clic en la instancia en clúster del servicio de inicio de sesión único de empresa y seleccione **propiedades** para mostrar la **Enterprise Single Sign-On propiedades del servicio** cuadro de diálogo.  
  
    9. Haga clic en el **dependencias** ficha del cuadro de diálogo de propiedades y haga clic en **insertar**.  
  
    10. Haga clic en el cuadro de lista desplegable en **recursos**, seleccione la **nombre:** recurso y haga clic en **Aceptar**.  
  
        > [!IMPORTANT]
        >  Si no se agrega la dependencia a la **nombre:** recursos, los equipos de cliente SSO generarán un error similar al siguiente al intentar ponerse en contacto con esta instancia en clúster del servicio SSO:  
        >   
        >  No se pudieron recuperar los secretos principales.  
        >   
        >  Compruebe que el nombre del servidor secreto principal es correcto y está disponible. Nombre del servidor secreto: ENTSSO Código de error: 0x800706D9. No hay más extremos disponibles desde el asignador de extremos.  
  
16. Clúster IIS en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo siguiendo los pasos documentados en [970759 "configuración de IIS 7.0 en un Microsoft Windows Server 2008 failover cluster" del artículo de Microsoft Knowledge Base](http://go.microsoft.com/fwlink/p/?LinkId=152793) (http://go.microsoft.com/fwlink/p/?LinkId=152793). Crear el servicio web IIS en clúster en el mismo grupo de clúster que el servicio SSO en clúster.  
  
17. En administración de clúster de conmutación por error, haga clic en el servicio en clúster o la aplicación que contiene el servicio de inicio de sesión único empresarial en clúster y, a continuación, haga clic en **conectar este servicio o aplicación** para iniciar todos los recursos en el servicio clúster o la aplicación.  
  
18. Haga clic en la aplicación o servicio en clúster, seleccione **mover este servicio o aplicación a otro nodo**y haga clic en el segundo nodo. Este paso mueve el servicio o la aplicación en clúster que contiene el servicio Inicio de sesión único empresarial en clúster del primer nodo al segundo.  
  
19. Haga clic en el servicio de Enterprise Single Sign-On en clúster y haga clic en **dejar este servicio o aplicación sin conexión**, a continuación, haga clic en la instancia del servicio SSO en clúster y haga clic en **poner este servicio o aplicación en línea**.  
  
20. Con la utilidad de línea de comandos ssomanage, establezca el servicio SSO en clúster como el nombre del servidor de SSO para todos los usuarios. Este comando debería ejecutarse desde la carpeta de instalación de SSO en cada uno de los servidores BizTalk Server del grupo. Por ejemplo, la siguiente línea de comandos establecerá el nombre del servicio SSO en clúster como el nombre del servidor SSO para todos los usuarios.  
  
    ```  
    ssomanage -serverall SSOCLUSTER  
    ```  
  
    > [!NOTE]
    >  *SSOCLUSTER* es un marcador de posición para el recurso de nombre de red real que se crea en el grupo de clúster que contiene el servicio SSO en clúster.  
  
21. Actualice el nombre del servidor de SSO accesible en la **propiedades del grupo de BizTalk** página hacer referencia al servicio SSO en clúster. Abra **administración de BizTalk Server**, haga clic en el grupo de BizTalk, seleccione la **propiedades** elemento de menú, actualice la entrada de nombre de servidor de SSO y, a continuación, haga clic en **Aceptar**.  
  
22. Siga los pasos de [cómo configurar un Host de BizTalk como recurso de clúster](http://msdn.microsoft.com/library/6e9aab00-7623-4175-bb12-ba916306f1e3) para crear una o varias instancias de host de BizTalk en clúster en el mismo grupo de clúster que ha creado el servicio SSO en clúster.  
  
    > [!NOTE]
    >  En este escenario, todos los hosts de BizTalk deben crearse como recursos de clúster en el mismo grupo de clústeres que el del recurso del servicio SSO en clúster. La ejecución de una instancia de host de BizTalk que no está en clúster en un nodo de clúster de Windows Server en el que está agrupado en clúster el servicio SSO no es una configuración admitida. Esto se debe a que la instancia de host de BizTalk que no está en clúster no se llevará a cabo correctamente si el servicio SSO en clúster se ha conmutado por error a otro nodo debido a la dependencia de una instancia de host de BizTalk del servicio SSO.