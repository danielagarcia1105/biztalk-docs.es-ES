---
title: "Cómo mover el servidor secreto principal | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], migrating
- migrating, Master Secret server
- Master Secret server, migrating
ms.assetid: 2bc5137e-f81d-486d-bb91-7c5981896f79
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b35fae6551a95c1c2009ac9786aa791d189f338
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-master-secret-server"></a>Cómo mover el servidor secreto principal
En este tema se documentan los pasos que pueden seguirse para mover el secreto principal de un servidor a otro, así como para mover el secreto principal de un servidor a un clúster de Windows Server.  
  
### <a name="to-move-the-master-secret-from-one-server-to-another-server"></a>Para mover el secreto principal de un servidor a otro  
  
1.  Instale Microsoft Enterprise Single Sign-On (SSO) Server en el nuevo servidor secreto principal si aún no se ha instalado. Inicie el programa de instalación de Microsoft Enterprise Single Sign-On Server desde \Platform\SSO\setup.exe en el CD de [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
2.  Configure SSO empresarial en el nuevo servidor secreto principal si aún no se ha configurado. Siga los pasos que se detallan a continuación para configurar SSO empresarial:  
  
    1.  Abra la herramienta de configuración. De forma predeterminada, la herramienta de configuración se encuentra en \<unidad >: \Program Files\Common Files\Enterprise inicio de sesión único-On\Configuration.exe.  
  
    2.  Haga clic para seleccionar **SSO empresarial** en el panel izquierdo.  
  
    3.  Active la casilla situada junto a **habilitar Enterprise Single Sign-On en este equipo** en el panel derecho.  
  
    4.  Haga clic en la opción de **unir un sistema SSO existente**.  
  
    5.  Especifique el existente **nombre del servidor** y **nombre de base de datos** para el SSO opciones de base de datos.  
  
    6.  Especificar la cuenta de servicio SSO empresarial existente para la **Enterprise Single Sign-On Server para el servicio de Windows** opción.  
  
        > [!NOTE]
        >  Debe ser una cuenta de dominio.  
  
    7.  Haga clic en la opción de **aplicar configuración** y haga clic en **configurar** en el cuadro de diálogo del Asistente para configuración para completar la configuración.  
  
    8.  Haga clic en **finalizar** y cierre la herramienta de configuración.  
  
3.  Copia de seguridad del secreto principal siguiendo los pasos descritos en [cómo volver la seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md).  
  
4.  Cambie el nombre del servidor secreto principal en la base de datos de SSO para hacer referencia al nuevo servidor secreto principal. Por ejemplo, puede ser el nombre del nuevo servidor secreto maestro **NewMSSServer**. Para ello, siga estos pasos en el servidor secreto principal original:  
  
    1.  Pegue el siguiente código en un editor de texto, como notepad.exe:  
  
        ```  
        <sso>  
        <globalInfo>  
        <secretServer>NewMSSServer</secretServer>  
        </globalInfo>  
        </sso>  
        ```  
  
    2.  Guarde el archivo como archivo .xml. Por ejemplo, guarde el archivo como **NewMSSServer.xml**.  
  
    3.  En el símbolo del sistema, desplácese a la carpeta de instalación de SSO empresarial. De forma predeterminada, es la carpeta de instalación \<unidad >: \Program Files\Common Files\Enterprise Single Sign-On.  
  
    4.  Tipo de **ssomanage - updatedb** *XMLFile* para actualizar el nombre de servidor secreto principal en la base de datos.  
  
        > [!NOTE]
        >  Reemplace *XMLFile* con el nombre del archivo .xml que guardó.  
  
        > [!NOTE]
        >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
5.  Reinicie el servicio de inicio de sesión único empresarial en el nuevo servidor secreto principal.  
  
6.  Restaurar el secreto principal de copia de seguridad en el nuevo servidor secreto principal siguiendo los pasos descritos en [cómo restaurar el secreto principal](../core/how-to-restore-the-master-secret.md) en el nuevo servidor secreto principal.  
  
### <a name="to-move-the-master-secret-from-one-server-to-a-windows-server-cluster"></a>Para mover el secreto principal de un servidor a un clúster de Windows Server  
  
1.  Instalar y configurar el servicio SSO empresarial en un clúster de Windows Server siguiendo los pasos descritos en [cómo agrupar el servidor secreto principal](../core/how-to-cluster-the-master-secret-server1.md). Complete cada uno de los pasos descritos en este tema, a excepción de los pasos descritos en la **restaurar el secreto principal en el segundo nodo de clúster** sección. Puesto que va a mover el servidor secreto principal existente en el clúster no elija la opción de **crear un nuevo sistema SSO** al configurar SSO empresarial en los nodos del clúster. Al configurar cada uno de los nodos del clúster, defina las opciones siguientes para la característica de SSO empresarial en el programa de configuración de BizTalk Server:  
  
    1.  Active la casilla junto a **habilitar Enterprise Single Sign-On en este equipo**.  
  
    2.  Haga clic en la opción de **unir un sistema SSO existente**.  
  
    3.  Especifique valores para el nombre de la base de datos y del servidor de la base de datos de SSO existentes.  
  
    4.  Indique la cuenta de servicio SSO existente al especificar la cuenta que se va a utilizar para el servicio de inicio de sesión único empresarial.  
  
2.  Copie el archivo de copia de seguridad del secreto principal existente en la carpeta \Enterprise Single Sign-On en cada uno de los nodos del clúster.  
  
3.  Si este clúster de Windows Server va a alojar uno o varios hosts de BizTalk agrupados, establezca el nombre de servidor de SSO para todos los usuarios como el servidor secreto maestro agrupado con la utilidad de línea de comandos ssomanage. Este comando debe ejecutarse desde la carpeta de instalación de SSO empresarial en cada servidor BizTalk Server en el grupo. Por ejemplo, la siguiente línea de comandos establecerá el servidor secreto principal agrupado como el nombre del servidor de SSO para todos los usuarios.  
  
    ```  
    ssomanage -serverall SSOCLUSTER  
    ```  
  
    > [!NOTE]
    >  *SSOCLUSTER* es un marcador de posición para la red real de nombre de recurso que se crea en el grupo de clúster que contiene el servidor secreto principal agrupado resourceIn este escenario, todos los hosts de BizTalk deben crearse como recursos de clúster en el mismo grupo de clústeres que el recurso del servicio SSO empresarial agrupado. La ejecución de una instancia de host de BizTalk no agrupada en un nodo de clúster de Windows Server en el que está agrupado el servicio SSO empresarial no es una configuración admitida. Esto se debe a que la instancia de host de BizTalk no agrupada no se llevará a cabo correctamente si el servicio SSO empresarial agrupado se ha conmutado por error a otro nodo debido a la dependencia de una instancia de host de BizTalk del servicio SSO.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4.  En el Administrador de clústeres, haga clic en el grupo de clúster que contiene el recurso del servicio SSO empresarial y haga clic en **poner en conexión** para iniciar todos los recursos del grupo de clústeres.  
  
5.  Si este clúster de Windows Server va a alojar uno o más hosts de BizTalk agrupados, actualice el nombre de servidor de SSO accesible en la **propiedades del grupo de BizTalk** página para hacer referencia el servidor secreto principal agrupado. Iniciar **administración de BizTalk Server**, haga clic en el grupo de BizTalk y seleccione el **propiedades** menú elemento, a continuación, actualice la entrada de **nombre del servidor de SSO** y haga clic en  **Aceptar**.  
  
    > [!NOTE]
    >  En este escenario, todos los hosts de BizTalk deben crearse como recursos de clúster en el mismo grupo de clúster como el recurso del servicio SSO empresarial agrupado. La ejecución de una instancia de host de BizTalk no agrupada en un nodo de clúster de Windows Server en el que está agrupado el servicio SSO empresarial no es una configuración admitida. Esto se debe a que la instancia de host de BizTalk no agrupada no se llevará a cabo correctamente si el servicio SSO empresarial agrupado se ha conmutado por error a otro nodo debido a la dependencia de una instancia de host de BizTalk del servicio SSO.  
  
6.  Haga clic en la instancia en clúster del servicio SSO empresarial y haga clic en **poner sin conexión**, a continuación, haga clic en la instancia en clúster del servicio SSO empresarial y haga clic en **poner en conexión**.  
  
    > [!NOTE]
    >  Si no se completa este paso, puede que los intentos de restaurar el secreto principal resulten infructuosos.  
  
7.  Restaure el secreto principal del que se ha realizado una copia de seguridad en cada nodo del clúster de Windows que aloja el servidor secreto principal agrupado. Siga los pasos de [cómo restaurar el secreto principal](../core/how-to-restore-the-master-secret.md) en cada nodo del clúster de Windows que aloja el servidor secreto principal agrupado.  
  
## <a name="see-also"></a>Vea también  
 [Administrar el secreto principal](../core/managing-the-master-secret.md)