---
title: Cómo mover la base de datos2 del archivo BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Archive database [BAM], migrating
- migrating, Archive database [BAM]
ms.assetid: 88b96dc2-8c9c-43f5-afb9-a937e05de36b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e33b09bd4e6563800c70acfae12ff52acc2cb071
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967173"
---
# <a name="how-to-move-the-bam-archive-database"></a><span data-ttu-id="638d5-102">Cómo mover la base de datos de archivo de BAM</span><span class="sxs-lookup"><span data-stu-id="638d5-102">How to Move the BAM Archive Database</span></span>
<span data-ttu-id="638d5-103">Este procedimiento se puede utilizar para mover la base de datos de archivo de BAM a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="638d5-103">You can use this procedure to move the BAM Archive database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="638d5-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="638d5-104">Prerequisites</span></span>  
 <span data-ttu-id="638d5-105">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="638d5-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-archive-database"></a><span data-ttu-id="638d5-106">Para mover la base de datos de archivo de BAM</span><span class="sxs-lookup"><span data-stu-id="638d5-106">To move the BAM Archive database</span></span>  
  
1. <span data-ttu-id="638d5-107">Obtenga una copia del archivo .xml utilizado para restaurar BAM:</span><span class="sxs-lookup"><span data-stu-id="638d5-107">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="638d5-108">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="638d5-108">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="638d5-109">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="638d5-109">At the command prompt, navigate to the following directory:</span></span>  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="638d5-110">Tracking</span><span class="sxs-lookup"><span data-stu-id="638d5-110">Tracking</span></span>  
  
   3. <span data-ttu-id="638d5-111">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="638d5-111">At the command prompt, type:</span></span>  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="638d5-112">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="638d5-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2. <span data-ttu-id="638d5-113">Siga las instrucciones en Libros en pantalla de SQL Server para la creación de una copia de seguridad de una base de datos del antiguo servidor.</span><span class="sxs-lookup"><span data-stu-id="638d5-113">Follow the instructions in SQL Server Books Online to back up the database on the old server.</span></span>  
  
3. <span data-ttu-id="638d5-114">Copie la base de datos de archivo de BAM en el nuevo servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="638d5-114">Copy the BAM Archive database to the new SQL server.</span></span>  
  
4. <span data-ttu-id="638d5-115">Siga las instrucciones en libros en pantalla de SQL Server para restaurar la base de datos en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="638d5-115">Follow the instructions in SQL Server Books Online to restore the database on the new server.</span></span>  
  
5. <span data-ttu-id="638d5-116">Edite el archivo BAMConfiguration.xml y cambie el valor de ServerName en la sección ArchivingDatabase DeploymentUnit al nombre del nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="638d5-116">Edit the BAMConfiguration.xml file and change the ServerName in the ArchivingDatabase DeploymentUnit section to the new server name.</span></span>  
  
6. <span data-ttu-id="638d5-117">Guarde el archivo BAMConfiguration.xml y ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="638d5-117">Save and close the BAMConfiguration.xml file.</span></span>  
  
7. <span data-ttu-id="638d5-118">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="638d5-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="638d5-119">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="638d5-119">At the command prompt, navigate to the following directory:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="638d5-120">Tracking</span><span class="sxs-lookup"><span data-stu-id="638d5-120">Tracking</span></span>  
  
9. <span data-ttu-id="638d5-121">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="638d5-121">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="638d5-122">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="638d5-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="638d5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="638d5-123">See Also</span></span>  
 [<span data-ttu-id="638d5-124">Mover bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="638d5-124">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)