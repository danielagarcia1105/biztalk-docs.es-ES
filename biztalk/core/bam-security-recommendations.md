---
title: Recomendaciones de seguridad BAM | Documentos de Microsoft
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
ms.openlocfilehash: 7f26cd3051dd296cc2849cb9c8ba7f8aa1d7ac6a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232188"
---
# <a name="bam-security-recommendations"></a><span data-ttu-id="57b31-102">Recomendaciones de seguridad para BAM</span><span class="sxs-lookup"><span data-stu-id="57b31-102">BAM Security Recommendations</span></span>
<span data-ttu-id="57b31-103">Se recomienda seguir estas directrices para proteger e implementar BAM en el entorno:</span><span class="sxs-lookup"><span data-stu-id="57b31-103">We recommend that you follow these guidelines for securing and deploying BAM in your environment:</span></span>  
  
-   <span data-ttu-id="57b31-104">Si utiliza [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)], el equipo de administración debe tener instalado el siguiente software para implementar BAM:</span><span class="sxs-lookup"><span data-stu-id="57b31-104">If you are using [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)], the administration computer must have the following software installed to deploy BAM:</span></span>  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]  
  
    -   <span data-ttu-id="57b31-105">Herramientas de cliente de [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57b31-105">[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] client tools</span></span>  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]<span data-ttu-id="57b31-106">Servicios de integración</span><span class="sxs-lookup"><span data-stu-id="57b31-106"> Integration Services</span></span>  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]<span data-ttu-id="57b31-107"> Servicios de análisis</span><span class="sxs-lookup"><span data-stu-id="57b31-107"> Analysis Services</span></span>  
  
    -   [!INCLUDE[SQLServer2005_SP3_long](../includes/sqlserver2005-sp3-long-md.md)]<span data-ttu-id="57b31-108">, si va a usar las alertas de BAM</span><span class="sxs-lookup"><span data-stu-id="57b31-108">, if you will be using BAM alerts</span></span>  
  
        > [!NOTE]
        >  [!INCLUDE[SQLServer2005_SP3_short](../includes/sqlserver2005-sp3-short-md.md)]<span data-ttu-id="57b31-109"> contiene [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services para [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57b31-109"> contains [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services for [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="57b31-110">El contexto de usuario en el que se ejecuta el paquete de análisis DTS debe ser miembro del rol db_owner de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] de la base de datos de importación principal y de la base de datos de esquema de estrella de BAM.</span><span class="sxs-lookup"><span data-stu-id="57b31-110">The user context under which the analysis DTS package runs must be a member of the db_owner [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] role of the BAM Primary Import and BAM Star Schema databases.</span></span> <span data-ttu-id="57b31-111">Además, la cuenta del servicio bajo la que Analysis Services se ejecuta debe ser de un administrador OLAP y un db_owner de la base de datos de esquema de estrella de BAM.</span><span class="sxs-lookup"><span data-stu-id="57b31-111">In addition, the service account under which Analysis Services runs must be an OLAP administrator and must be a db_owner of the BAM Star Schema database.</span></span> <span data-ttu-id="57b31-112">Para obtener más información, vea el sitio Web de soporte técnico y Microsoft Help en [http://go.microsoft.com/fwlink/?LinkId=22781](http://go.microsoft.com/fwlink/?LinkId=22781).</span><span class="sxs-lookup"><span data-stu-id="57b31-112">For more information, see the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=22781](http://go.microsoft.com/fwlink/?LinkId=22781).</span></span>  
  
-   <span data-ttu-id="57b31-113">Varios usuarios necesitan tener acceso a los datos activos y archivados: vendedores, gestores empresariales y otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="57b31-113">Multiple users need access to the live and archived data: salespeople, business managers, and others.</span></span> <span data-ttu-id="57b31-114">Estos usuarios deben tener cuentas de dominio en el dominio en que residan la base de datos de importación principal y la base de datos de análisis de BAM, pero no es necesario que sus cuentas tengan acceso a los recursos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="57b31-114">These users must have domain accounts in the domain where the BAM Primary Import and BAM Analysis databases are (corporate domain), but their accounts do not need to have access to BizTalk resources.</span></span>  
  
-   <span data-ttu-id="57b31-115">Para que los usuarios obtener acceso a vistas de los datos BAM, debe usar la utilidad de administración de BAM (BM.exe) para conceder los permisos de los usuarios a las vistas y los usuarios deben tener los inicios de sesión SQL.</span><span class="sxs-lookup"><span data-stu-id="57b31-115">For users to access views of the BAM data, you must use the BAM management utility (BM.exe) to grant the users permissions to the views, and the users must have SQL logins.</span></span> <span data-ttu-id="57b31-116">Para obtener más información acerca de la utilidad de administración de BAM, consulte [utilidad de administración de BAM](../core/bam-management-utility.md).</span><span class="sxs-lookup"><span data-stu-id="57b31-116">For more information about the BAM management utility, see [BAM Management Utility](../core/bam-management-utility.md).</span></span>  
  
-   <span data-ttu-id="57b31-117">Para agregar usuarios a roles que tienen acceso a los cubos de la base de datos de análisis de BAM, debe disponer de un equipo de administración en el mismo dominio que las bases de datos de BAM.</span><span class="sxs-lookup"><span data-stu-id="57b31-117">To add users to roles that have access to the cubes in the BAM Analysis database, you must have an administration computer in the same domain as the BAM databases.</span></span>  
  
-   <span data-ttu-id="57b31-118">La persona encargada de administrar BAM deberá figurar como db_owner en la base de datos de importación principal, en la base de datos de esquema de estrella y en la base de datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="57b31-118">The person administering BAM must be db_owner for the BAM Primary Import, Star Schema, and BAM Archive databases.</span></span> <span data-ttu-id="57b31-119">Esa persona también deberá ser administrador de OLAP en la base de datos de análisis de BAM.</span><span class="sxs-lookup"><span data-stu-id="57b31-119">That person must also be an OLAP administrator for the BAM Analysis database.</span></span>  
  
-   <span data-ttu-id="57b31-120">Si implementa libros de Microsoft Office Excel (archivos .xls), Excel debe estar instalado en el equipo de administración.</span><span class="sxs-lookup"><span data-stu-id="57b31-120">If you are deploying Microsoft Office Excel workbooks (.xls files), Excel must be installed on the administration computer.</span></span> <span data-ttu-id="57b31-121">Antes de implementar un libro, ábralo y asegúrese de que la seguridad de las macros está establecida en alta y que no existen advertencias.</span><span class="sxs-lookup"><span data-stu-id="57b31-121">Before you deploy a workbook, open it and ensure that the macro security is set to high, and that there are no warnings.</span></span>  
  
-   <span data-ttu-id="57b31-122">Si no existe una necesidad empresarial de distribuir a los usuarios libros de Excel para BAM que se conectan a los datos reales, es aconsejable implementar los libros usando archivos XML.</span><span class="sxs-lookup"><span data-stu-id="57b31-122">If there is no business need to distribute to the users BAM Excel workbooks that connect to the real data, we recommend that you deploy the workbooks by using XML files.</span></span> <span data-ttu-id="57b31-123">De este modo, evitará tener que instalar Excel en el equipo de administración, y no será necesario comprobar el nivel de seguridad de las macros.</span><span class="sxs-lookup"><span data-stu-id="57b31-123">This eliminates the need to install Excel on the administration computer, and the need to verify the macro security level.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="57b31-124">Al quitar permisos de un usuario en una vista, debe olvidar eliminar cualquier suscripción a alertas que el usuario ha establecido.</span><span class="sxs-lookup"><span data-stu-id="57b31-124">When you remove a user's permissions on a view, you must also remember to eliminate any subscriptions to alerts that the user has set.</span></span> <span data-ttu-id="57b31-125">Para obtener más información sobre cómo quitar suscriptores de una alerta, consulte [cómo quitar suscriptores de una alerta](../core/how-to-remove-subscribers-from-an-alert.md).</span><span class="sxs-lookup"><span data-stu-id="57b31-125">For more information about removing subscribers from an alert, see [How to Remove Subscribers from an Alert](../core/how-to-remove-subscribers-from-an-alert.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57b31-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="57b31-126">See Also</span></span>  
 <span data-ttu-id="57b31-127">[Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="57b31-127">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 [<span data-ttu-id="57b31-128">Recomendaciones de seguridad para una implementación de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="57b31-128">Security Recommendations for a BizTalk Server Deployment</span></span>](../core/security-recommendations-for-a-biztalk-server-deployment.md)