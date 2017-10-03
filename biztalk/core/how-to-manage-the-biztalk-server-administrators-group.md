---
title: "Cómo administrar el grupo de administradores de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Administrators group, user accounts
- BizTalk Administrators group
- user accounts, BizTalk Administrators group
- Windows Management Instrumentation (WMI), administering
- BizTalk Administrators group, privileges
- security, BizTalk Administrators group
- Administration Console [BizTalk Server], security
- Administration Console [BizTalk Server], administering
- BizTalk Administrators group, about BizTalk Administrators group
ms.assetid: 60ea689b-0b93-4fcc-b49c-6436e7be473f
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fe92c9c43ccef242d8c14b5f1aa48e0b1a8d852
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-the-biztalk-server-administrators-group"></a>Cómo administrar el grupo de administradores de BizTalk Server
El grupo de administradores de BizTalk Server cuenta con los privilegios mínimos necesarios para llevar a cabo tareas de carácter administrativo. Mediante la consola de administración de BizTalk Server o el proveedor WMI, se agregan usuarios al grupo de administradores de BizTalk Server para que puedan llevar a cabo tareas de este tipo. Cuando no es necesario que los usuarios del grupo de administradores de BizTalk Server sigan llevando a cabo tareas administrativas, es posible quitarlos de este grupo mediante la consola de administración de BizTalk Server o el proveedor WMI.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe ser miembro del grupo de administradores de dominio o del grupo de administradores.  
  
### <a name="to-add-users-to-the-local-biztalk-server-administrators-group"></a>Para agregar usuarios al grupo local de administradores de BizTalk Server  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.  
  
2.  Expanda **herramientas del sistema**, expanda **usuarios y grupos locales**y, a continuación, haga clic en el **grupos** carpeta. El contenido de la carpeta aparecerá en el panel de detalles.  
  
3.  En el panel de detalles, haga clic en **administradores de BizTalk Server**.  
  
4.  En el **acción** menú, elija **todas las tareas**y, a continuación, haga clic en **agregar al grupo**.  
  
5.  En el **propiedades de administradores de BizTalk Server** cuadro de diálogo, haga clic en **agregar**.  
  
6.  En el **buscar en** lista, seleccione el nombre de dominio o equipo.  
  
7.  En la lista que contiene los usuarios y equipos asociados con el dominio o equipo seleccionado en el paso 6, seleccione la cuenta de usuario para agregar, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
8.  Haga clic en **Aceptar** para cerrar el **propiedades de administradores de BizTalk Server** cuadro de diálogo.  
  
### <a name="to-remove-users-from-local-the-biztalk-server-administrators-group"></a>Para quitar usuarios del grupo local de administradores de BizTalk Server  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.  
  
2.  Expanda **herramientas del sistema**, expanda **usuarios y grupos locales**y, a continuación, haga clic en el **grupos** carpeta. El contenido de la carpeta aparecerá en el panel de detalles.  
  
3.  En el panel de detalles, haga clic en **administradores de BizTalk Server**.  
  
4.  En el **acción** menú, haga clic en **propiedades**.  
  
5.  En el **propiedades de administradores de BizTalk Server** cuadro de diálogo, seleccione la cuenta de usuario desea quitar y, a continuación, haga clic en **quitar**.  
  
6.  Haga clic en **Aceptar**.  
  
### <a name="to-add-users-to-the-domain-biztalk-server-administrators-group"></a>Para agregar usuarios al grupo de dominio de administradores de BizTalk Server  
  
1.  Inicie sesión en el controlador de dominio en el que se han unido las bases de datos de SQL Server mediante la cuenta de administradores de dominio.  
  
2.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **equipos y usuarios de Active Directory** a iniciar el **equipos y usuarios de Active Directory** consola.  
  
    1.  En el árbol de consola, haga clic en la carpeta que contiene el grupo de administradores de BizTalk Server al que desea agregar un miembro.  
  
    2.  En el panel de detalles, haga clic en el grupo de administradores de BizTalk Server y, a continuación, haga clic en **propiedades**.  
  
    3.  En el **miembros** , haga clic en **agregar**.  
  
    4.  En **escriba los nombres de objeto para seleccionar**, escriba el nombre del usuario y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-remove-users-from-the-domain-biztalk-server-administrators-group"></a>Procedimiento para quitar usuarios del grupo de dominio de administradores de BizTalk Server  
  
1.  Inicie sesión en el controlador de dominio que las bases de datos SQL se combinan mediante la cuenta de administradores de dominio.  
  
2.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **equipos y usuarios de Active Directory** a iniciar el **equipos y usuarios de Active Directory** consola.  
  
    1.  En el árbol de consola, haga clic en la carpeta que contiene el grupo de administradores de BizTalk Server al que desea agregar un miembro.  
  
    2.  En el panel de detalles, haga clic en el grupo de administradores de BizTalk Server y, a continuación, haga clic en **propiedades**.  
  
    3.  En el **miembros** , haga clic en el miembro que desee quitar y, a continuación, haga clic en **quitar**.  
  
    4.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la seguridad de servidor BizTalk Server](../core/managing-biztalk-server-security.md)   
 [Administración de Hosts y las cuentas de servicio](../core/managing-hosts-and-service-accounts.md)   
 [Prácticas recomendadas para administrar las cuentas de usuario y grupos de Windows](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)   
 [Grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [Administrar cuentas de usuario y grupos de Windows](../core/managing-windows-groups-and-user-accounts.md)