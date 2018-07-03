---
title: Recomendaciones de seguridad para BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, BAM
- managing [BAM], security
- BAM, security
ms.assetid: 73613123-c1ed-477a-9f5c-342b2573c975
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4818540e6adaba2568226f353e7e025b8732655b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970646"
---
# <a name="bam-security-recommendations"></a>Recomendaciones de seguridad para BAM
Se recomienda seguir estas directrices para proteger e implementar BAM en el entorno:  
  
- Si utiliza [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)], el equipo de administración debe tener instalado el siguiente software para implementar BAM:  
  
  - [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]  
  
  - Herramientas de cliente de [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]  
  
  - [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] Servicios de integración  
  
  - [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] Servicios de análisis  
  
  - [!INCLUDE[SQLServer2005_SP3_long](../includes/sqlserver2005-sp3-long-md.md)], si va a usar las alertas de BAM  
  
    > [!NOTE]
    >  [!INCLUDE[SQLServer2005_SP3_short](../includes/sqlserver2005-sp3-short-md.md)] contiene [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services para [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)].  
  
  > [!NOTE]
  >  El contexto de usuario en el que se ejecuta el paquete de análisis DTS debe ser miembro del rol db_owner de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] de la base de datos de importación principal y de la base de datos de esquema de estrella de BAM. Además, la cuenta del servicio bajo la que Analysis Services se ejecuta debe ser de un administrador OLAP y un db_owner de la base de datos de esquema de estrella de BAM. Para obtener más información, vea el sitio Web de soporte técnico y de Microsoft Help en [ http://go.microsoft.com/fwlink/?LinkId=22781 ](http://go.microsoft.com/fwlink/?LinkId=22781).  
  
- Varios usuarios necesitan tener acceso a los datos activos y archivados: vendedores, gestores empresariales y otros. Estos usuarios deben tener cuentas de dominio en el dominio en que residan la base de datos de importación principal y la base de datos de análisis de BAM, pero no es necesario que sus cuentas tengan acceso a los recursos de BizTalk.  
  
- Para que los usuarios obtener acceso a vistas de los datos BAM, debe usar la utilidad de administración de BAM (BM.exe) para conceder los permisos de los usuarios a las vistas y los usuarios deben tener los inicios de sesión SQL. Para obtener más información acerca de la utilidad de administración de BAM, consulte [utilidad de administración de BAM](../core/bam-management-utility.md).  
  
- Para agregar usuarios a roles que tienen acceso a los cubos de la base de datos de análisis de BAM, debe disponer de un equipo de administración en el mismo dominio que las bases de datos de BAM.  
  
- La persona encargada de administrar BAM deberá figurar como db_owner en la base de datos de importación principal, en la base de datos de esquema de estrella y en la base de datos de archivo. Esa persona también deberá ser administrador de OLAP en la base de datos de análisis de BAM.  
  
- Si implementa libros de Microsoft Office Excel (archivos .xls), Excel debe estar instalado en el equipo de administración. Antes de implementar un libro, ábralo y asegúrese de que la seguridad de las macros está establecida en alta y que no existen advertencias.  
  
- Si no existe una necesidad empresarial de distribuir a los usuarios libros de Excel para BAM que se conectan a los datos reales, es aconsejable implementar los libros usando archivos XML. De este modo, evitará tener que instalar Excel en el equipo de administración, y no será necesario comprobar el nivel de seguridad de las macros.  
  
  > [!IMPORTANT]
  >  Al quitar permisos de un usuario en una vista, recuerde que debe eliminar cualquier suscripción a alertas que el usuario ha establecido. Para obtener más información sobre cómo quitar suscriptores de una alerta, consulte [cómo quitar suscriptores de una alerta](../core/how-to-remove-subscribers-from-an-alert.md).  
  
## <a name="see-also"></a>Vea también  
 [Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)   
 [Recomendaciones de seguridad para una implementación de BizTalk Server](../core/security-recommendations-for-a-biztalk-server-deployment.md)