---
title: Cómo agrupar el Servidor1 de secreto maestro | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, second node
- Master Secret server, restoring
- clustering, Master Secret server
- Master Secret server, clustering
ms.assetid: ef817fa4-e43d-4e3d-8686-5bd675708001
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94355632973a60a6f126d896c77c56961a5d529a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003373"
---
# <a name="how-to-cluster-the-master-secret-server"></a>Cómo agrupar el servidor secreto principal
Se recomienda seguir las instrucciones contenidas en esta sección para agrupar el servicio de inicio de sesión único (SSO) empresarial correctamente en el servidor secreto principal.  
  
 Al organizar por clústeres el servidor secreto principal, los servidores de inicio de sesión único se comunican con la instancia agrupada activa del servidor secreto principal. De forma similar, la instancia agrupada activa del servidor secreto principal se comunica con la base de datos de SSO.  
  
 Deberá ser administrador de SSO para realizar este procedimiento.  
  
> [!CAUTION]
>  El servidor secreto principal no puede instalarse en un clúster de equilibrio de carga de red (NLB).  
  
### <a name="to-install-and-configure-enterprise-sso-on-the-cluster-nodes"></a>Para instalar y configurar SSO empresarial en los nodos de clúster  
  
1. Instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en cada nodo del clúster. En **instalación de componentes**, seleccione **Single Sign-On módulo de administración empresarial** y **Enterprise Single Sign-On servidor secreto principal**. Después de instalación se completó correctamente, realice **no** ejecutar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración.  
  
2. Crear **administradores de SSO** y **administradores afiliados de SSO** grupos de dominio. Para crear una instancia en clúster del servicio SSO empresarial, debe crear estos grupos como grupos de dominio.  
  
3. Cree o designe una cuenta de dominio que sea miembro de la **administradores de SSO** grupo de dominio. El Servicio SSO empresarial de cada nodo está configurado para iniciar sesión como esta cuenta de dominio. Esta cuenta debe tener la **iniciar sesión como un servicio** en cada nodo del clúster.  
  
4. Agregue la cuenta que usas para iniciar sesión durante el proceso de configuración para el dominio **administradores de SSO** grupo.  
  
   > [!IMPORTANT]
   >  Si no se completan los pasos 3 y 4, la configuración del servicio SSO empresarial no se lleva a cabo correctamente.  
  
5. Inicie la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
6. Seleccione **configuración personalizada** opción y escriba el **el nombre del servidor de base de datos**, **nombre de usuario**, y **contraseña** valores. Seleccione **configurar** para continuar.  
  
   > [!NOTE]
   >  Puesto que sólo se puede configurar el servicio SSO empresarial en este momento, sólo se puede especificar la cuenta de dominio creada anteriormente.  
  
7. Seleccione el **SSO empresarial** opción en el panel izquierdo y defina las siguientes opciones para la característica SSO empresarial:  
  
   1.  Seleccione el **habilitar Enterprise Single Sign-On en este equipo** casilla de verificación.  
  
   2.  Seleccione **crear un nuevo sistema SSO**.  
  
   3.  Escriba el **almacena datos** para **nombre del servidor** y **nombre de base de datos** valores.  
  
   4.  Compruebe que la cuenta de dominio creada anteriormente es la cuenta asociada con el servicio SSO empresarial.  
  
   5.  Escriba el grupo Administradores de SSO de dominio creado anteriormente como el grupo asociado con el rol Administradores de SSO.  
  
   6.  Escriba el grupo Administradores afiliados de SSO de dominio creado anteriormente como el grupo asociado con el rol Administradores afiliados de SSO.  
  
8. Seleccione el **copia de seguridad del secreto de SSO de Enterprise** opción en el panel izquierdo y proporcione los parámetros adecuados para la copia de seguridad del secreto de SSO empresarial. De forma predeterminada, el secreto de SSO empresarial está respaldado hasta  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On\\*SSOxxxx*bak.  
  
9. Haga clic en el **aplicar configuración** y revise el resumen.  
  
10. Haga clic en **siguiente** para aplicar la configuración.  
  
11. Haga clic en **finalizar** para cerrar el Asistente para configuración.  
  
12. Cierre la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
13. Inicie sesión en el nodo de clúster pasivo e inicie la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
14. Elija la **configuración personalizada** opción y escriba los mismos valores para el **el nombre del servidor de base de datos**, **nombre de usuario**, y **contraseña** que especificó al configurar el primer nodo del clúster. Tras especificar estos valores, haga clic en **configurar** para continuar.  
  
15. Seleccione el **SSO empresarial** opción en el panel izquierdo y defina las siguientes opciones para la característica SSO empresarial:  
  
    1.  Seleccione el **habilitar Enterprise Single Sign-On en este equipo** opción.  
  
    2.  Seleccione **unir un sistema SSO existente**.  
  
    3.  Especifique los mismos valores para la base de datos de SSO **nombre del servidor** y **nombre de base de datos** que especificó al configurar el primer nodo del clúster.  
  
    4.  Especifique el mismo valor para la cuenta de dominio que el especificado al configurar el primer nodo de clúster.  
  
16. Seleccione **aplicar configuración** para mostrar el resumen.  
  
17. Seleccione **siguiente** para aplicar la configuración.  
  
18. Seleccione **finalizar** para cerrar el Asistente para configuración.  
  
19. Cerrar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración.  
  
### <a name="to-update-the-master-secret-server-name-in-the-sso-database"></a>Para actualizar el nombre del servidor secreto principal en la base de datos de SSO  
  
1.  Escriba los comandos siguientes en un símbolo del sistema del nodo de clúster activo para detener y reiniciar el servicio SSO empresarial:  
  
    ```  
    net stop entsso  
    ```  
  
     y  
  
    ```  
    net start entsso  
    ```  
  
2.  Cambie el nombre del servidor secreto principal en la base de datos de SSO al nombre de clúster mediante los pasos que se indican a continuación.  
  
    > [!NOTE]
    >  El nombre de clúster es el nombre definido para el recurso de nombre de red creado en el grupo de clústeres o en la aplicación o servicio en clúster que contendrá el servicio SSO empresarial en clúster. Por ejemplo, el nombre puede ser *BIZTALKCLUSTER*.  
  
    1.  Pegue el código siguiente en un editor de texto:  
  
        ```  
        <sso>  
          <globalInfo>  
            <secretServer>BIZTALKCLUSTER</secretServer>  
          </globalInfo>  
        </sso>  
        ```  
  
        > [!NOTE]
        >  *BIZTALKCLUSTER* es un marcador de posición para el recurso de nombre de red real creado en el clúster o la aplicación o servicio en clúster grupo.  
  
    2.  Guarde el archivo con la extensión .xml. Por ejemplo, puede guardar el archivo con el nombre SSOCLUSTER.xml.  
  
    3.  En el símbolo del sistema, desplácese a la carpeta de instalación de SSO empresarial. De forma predeterminada, la carpeta de instalación es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
    4.  Escriba el comando siguiente en el símbolo del sistema para actualizar el servidor secreto principal en la base de datos:  
  
        ```  
        ssomanage -updatedb XMLFile  
        ```  
  
        > [!NOTE]
        >  *XMLFile* es un marcador de posición para el nombre del archivo .xml que guardó anteriormente.  
  
### <a name="to-create-the-clustered-enterprise-sso-resource"></a>Para crear el recurso SSO empresarial agrupado  
  
1.  Si el clúster no está configurado con un recurso Coordinador de transacciones distribuidas (MSDTC) agrupado, a continuación, siga los pasos descritos en el artículo "Mejora error tolerancia en BizTalk Server por usando un clúster de Windows Server" en [ http://go.microsoft.com/fwlink/?LinkId=69207 ](http://go.microsoft.com/fwlink/?LinkId=69207) para crear un recurso MSDTC agrupado.  
  
2.  Haga clic en **iniciar**, **programas**, **herramientas administrativas**y, a continuación, **administración del clúster de conmutación por error** para iniciar el clúster de conmutación por error Programa de administración.  
  
3.  En el panel izquierdo, haga clic en **administración del clúster de conmutación por error** y haga clic en **administrar un clúster**.  
  
4.  En el **seleccione un clúster para administrar** diálogo cuadro, escriba el clúster para administrar y haga clic en **Aceptar**.  
  
5.  En el panel izquierdo, haga clic para seleccionar un servicio o aplicación en clúster que contenga un recurso de dirección IP y nombre de red. Siga los pasos de [cómo crear un grupo de clústeres con un disco, dirección IP y nombre de recurso](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md) para crear un grupo con un recurso de dirección IP y nombre de red si no existe.  
  
    > [!NOTE]
    >  Un servicio SSO empresarial en clúster no necesita de forma explícita el uso de un recurso de disco físico en clúster en el mismo grupo.  
  
6.  Haga clic en el servicio en clúster o la aplicación, elija **agregar un recurso**y haga clic en **servicio genérico** para mostrar el **Asistente para nuevo recurso** cuadro de diálogo.  
  
    > [!IMPORTANT]
    >  En el **parámetros de servicio genérico** cuadro de diálogo, si no hace clic para seleccionar el **usar el nombre de red para el nombre del equipo** casilla de verificación, los equipos de cliente SSO generarán un error similar al siguiente cuando se intente ponerse en contacto con esta instancia en clúster del servicio SSO empresarial:  
    >   
    >  No se pudieron recuperar los secretos principales.  
    >   
    >  Compruebe que el nombre del servidor secreto principal es correcto y está disponible. Nombre del servidor secreto: ENTSSO Código de error: 0x800706D9. No hay más extremos disponibles desde el asignador de extremos.  
  
7.  En el **Seleccionar servicio** página de la **Asistente para nuevo recurso**, haga clic para seleccionar **Enterprise Single Sign-On Service** y haga clic en **siguiente**.  
  
8.  En el **confirmación** página haga clic en **siguiente**.  
  
9. En el **resumen** página haga clic en **finalizar**. Aparecerá una instancia agrupada del servicio de inicio de sesión único de Enterprise en **otros recursos** en el panel central de la **administración del clúster de conmutación por error** interfaz.  
  
10. Haga clic en la instancia en clúster de que el servicio de inicio de sesión único de Enterprise y seleccione **propiedades** para mostrar el **Enterprise Single Sign-On propiedades del servicio** cuadro de diálogo.  
  
11. Haga clic en el **dependencias** ficha del cuadro de diálogo de propiedades y haga clic en **insertar**.  
  
12. Haga clic en el cuadro de lista desplegable bajo **recursos**, seleccione el **nombre:** recursos y haga clic en **Aceptar**.  
  
### <a name="to-restore-the-master-secret-on-the-second-cluster-node"></a>Para restaurar el secreto principal en el segundo nodo de clúster  
  
1.  En administración de clúster de conmutación por error, a la derecha, haga clic en el servicio en clúster o la aplicación que contiene el servicio de inicio de sesión único empresarial en clúster y, a continuación, haga clic en **conectar este servicio o aplicación** para iniciar todos los recursos en el servicio en clúster o la aplicación.  
  
2.  Haga clic en el servicio en clúster o la aplicación, elija **mover este servicio o aplicación a otro nodo**y haga clic en el segundo nodo. Este paso mueve el servicio o la aplicación en clúster que contiene el servicio Inicio de sesión único empresarial en clúster del primer nodo al segundo.  
  
3.  Haga clic en el servicio Enterprise Single Sign-On en clúster y haga clic en **desconectar este servicio o aplicación**, a continuación, haga clic en la instancia agrupada del servicio SSO empresarial y haga clic en **poner este servicio o aplicación en línea**.  
  
    > [!NOTE]
    >  Si no se completa este paso, es posible que el intento de restaurar el secreto principal resulte infructuoso.  
  
4.  Copie el archivo de copia de seguridad del secreto principal del primer nodo a la carpeta de instalación \Enterprise Single Sign-On del segundo nodo. De forma predeterminada, la carpeta de instalación es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
5.  Inicie sesión en el segundo nodo y, en un símbolo del sistema, cambie a la carpeta de instalación de SSO empresarial.  
  
6.  Para restaurar el secreto principal en el segundo nodo, escriba el comando siguiente en el símbolo del sistema:  
  
    ```  
    ssoconfig -restoresecret RestoreFile  
    ```  
  
    > [!NOTE]
    >  Reemplace *RestoreFile* con la ruta de acceso y el nombre del archivo de copia de seguridad que contiene el secreto principal.  
  
     El secreto principal se almacena en el Registro en la siguiente ubicación:  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS  
  
7.  Mueva la aplicación o servicio en clúster que contiene el servicio de inicio de sesión único empresarial en clúster de este nodo de clúster a otro nodo de clúster para garantizar la funcionalidad de conmutación por error. A continuación, mueva el grupo de clúster en el sentido contrario para comprobar la funcionalidad de conmutación por recuperación.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear un grupo de clústeres con un disco, la dirección IP y el recurso de nombre](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md)
