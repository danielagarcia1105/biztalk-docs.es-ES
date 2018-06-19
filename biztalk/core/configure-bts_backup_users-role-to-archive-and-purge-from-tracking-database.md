---
title: Cómo configurar la función BTS_BACKUP_USERS para archivar y purgar datos de la base de datos de seguimiento de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- purging, BTS_BACKUP_USERS role
- Tracking database, purging
- BTS_BACKUP_USERS role
- DTA Purge and Archive job
- archiving [Tracking database], BTS_BACKUP_USERS role
- archiving [Tracking database], DTA Purge and Archive job
- Tracking database, BTS_BACKUP_USERS role
- Tracking database, archiving
- purging, DTA Purge and Archive job
ms.assetid: c27aad2a-5788-4236-b5eb-ca730bf79851
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923fb083f3755259ab2176541213d1637ce872c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232452"
---
# <a name="how-to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="cfb34-102">Cómo configurar el rol BTS_BACKUP_USERS para archivar y purgar datos de la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="cfb34-102">How to Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="cfb34-103">Por lo general, el trabajo DTA Purge and Archive (BizTAlkDTADb) se ejecuta utilizando las credenciales de usuario de la cuenta de servicio del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cfb34-103">The DTA Purge and Archive (BizTAlkDTADb) job normally runs using the credentials of the logged-on SQL Server Agent service account user.</span></span> <span data-ttu-id="cfb34-104">Para obtener una mayor seguridad, puede configurar el trabajo DTA Purge and Archive (BizTalkDTADb) para que se ejecute utilizando las credenciales de una cuenta que sea miembro de la función BTS_BACKUP_USERS.</span><span class="sxs-lookup"><span data-stu-id="cfb34-104">For added security, however, you can configure the DTA Purge and Archive (BizTalkDTADb) job to run using the credentials of an account which is a member of the BTS_BACKUP_USERS role.</span></span> <span data-ttu-id="cfb34-105">De esta forma, se evita la elevación de privilegios mediante la ejecución de trabajos del Agente SQL Server en cuentas con permisos básicos.</span><span class="sxs-lookup"><span data-stu-id="cfb34-105">This helps to prevent elevation of privileges by running SQL Server Agent jobs under accounts with essential permissions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cfb34-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cfb34-106">Prerequisites</span></span>  
 <span data-ttu-id="cfb34-107">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cfb34-107">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-configure-the-btsbackupusers-role-for-archiving-and-purging-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="cfb34-108">Procedimiento para configurar la función BTS_BACKUP_USERS para el archivo y depurado de datos de la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="cfb34-108">To configure the BTS_BACKUP_USERS role for archiving and purging data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="cfb34-109">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft SQL Server 2008 SP2**y, a continuación, haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="cfb34-109">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="cfb34-110">En el **conectar al servidor** cuadro de diálogo, especifique el nombre del servidor SQL donde reside la base de datos de seguimiento de BizTalk (BizTalkDTADb) y el tipo de autenticación adecuado y, a continuación, haga clic en **conectar** a conectar con el servidor SQL Server apropiado.</span><span class="sxs-lookup"><span data-stu-id="cfb34-110">In the **Connect to Server** dialog box, specify the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
3.  <span data-ttu-id="cfb34-111">En **Microsoft SQL Server Management Studio**, haga doble clic en **BizTalkDTADb**, haga doble clic en **seguridad**, haga doble clic en **Roles**, y a continuación, haga doble clic en **Roles de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="cfb34-111">In **Microsoft SQL Server Management Studio**, double-click **BizTalkDTADb**, double-click **Security**, double-click **Roles**, and then double-click **Database Roles**.</span></span>  
  
4.  <span data-ttu-id="cfb34-112">En el **detalles del explorador de objetos** panel, haga doble clic en **BTS_BACKUP_USERS**.</span><span class="sxs-lookup"><span data-stu-id="cfb34-112">In the **Object Explorer Details** pane, double-click **BTS_BACKUP_USERS**.</span></span>  
  
5.  <span data-ttu-id="cfb34-113">En el **propiedades del rol de base de datos – BTS_BACKUP_USERS** cuadro de diálogo **miembros de este rol**, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="cfb34-113">In the **Database Role Properties – BTS_BACKUP_USERS** dialog box, under **Members of this role**, click **Add**.</span></span>  
  
6.  <span data-ttu-id="cfb34-114">En el **Seleccionar base de datos de usuario o rol** cuadro de diálogo, escriba una cuenta de usuario con credenciales de servicio del Agente SQL Server y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cfb34-114">In the **Select Database User or Role** dialog box, enter a user account with SQL Server Agent Service credentials, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb34-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfb34-115">See Also</span></span>  
 [<span data-ttu-id="cfb34-116">Archivar y purgar la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="cfb34-116">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)