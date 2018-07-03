---
title: Cómo mover la base de datos2 del análisis BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, Analysis database [BAM]
- Analysis database [BAM], migrating
ms.assetid: b0320273-4840-4573-bb82-bba95021535e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 237f951a4795ef6571a72989be22893d57572df9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011797"
---
# <a name="how-to-move-the-bam-analysis-database"></a><span data-ttu-id="8cdc4-102">Cómo mover la base de datos de análisis de BAM</span><span class="sxs-lookup"><span data-stu-id="8cdc4-102">How to Move the BAM Analysis Database</span></span>
<span data-ttu-id="8cdc4-103">Este procedimiento se puede utilizar para mover la base de datos de análisis de BAM a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="8cdc4-103">You can use this procedure to move the BAM Analysis database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8cdc4-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8cdc4-104">Prerequisites</span></span>  
 <span data-ttu-id="8cdc4-105">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8cdc4-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-analysis-database"></a><span data-ttu-id="8cdc4-106">Para mover la base de datos de análisis de BAM</span><span class="sxs-lookup"><span data-stu-id="8cdc4-106">To move the BAM Analysis database</span></span>  
  
1. <span data-ttu-id="8cdc4-107">Obtenga una copia del archivo .xml utilizado para restaurar BAM:</span><span class="sxs-lookup"><span data-stu-id="8cdc4-107">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="8cdc4-108">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8cdc4-108">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="8cdc4-109">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="8cdc4-109">At the command prompt, navigate to the following directory:</span></span>  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="8cdc4-110">Tracking</span><span class="sxs-lookup"><span data-stu-id="8cdc4-110">Tracking</span></span>  
  
   3. <span data-ttu-id="8cdc4-111">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="8cdc4-111">At the command prompt, type:</span></span>  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="8cdc4-112">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="8cdc4-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2. <span data-ttu-id="8cdc4-113">Siga las instrucciones en libros en pantalla de SQL Server sobre cómo realizar una copia de seguridad de la base de datos en el servidor anterior.</span><span class="sxs-lookup"><span data-stu-id="8cdc4-113">Follow the instructions in SQL Server Books Online on how to back up the database on the old server.</span></span>  
  
3. <span data-ttu-id="8cdc4-114">Copie la base de datos de análisis de BAM en el nuevo servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8cdc4-114">Copy the BAM Analysis database to the new SQL Server.</span></span>  
  
4. <span data-ttu-id="8cdc4-115">Siga las instrucciones en Libros en pantalla de SQL Server para la creación de una copia de seguridad de una base de datos en el servidor nuevo.</span><span class="sxs-lookup"><span data-stu-id="8cdc4-115">Follow the instructions in SQL Server Books Online on how to restore the database on the new server.</span></span>  
  
5. <span data-ttu-id="8cdc4-116">Edite el archivo BAMConfiguration.xml y cambie el valor de ServerName en la sección AnalysisDatabase DeploymentUnit al nombre del nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="8cdc4-116">Edit the BAMConfiguration.xml file and change the ServerName in the AnalysisDatabase DeploymentUnit section to the new server name.</span></span>  
  
6. <span data-ttu-id="8cdc4-117">Guarde el archivo BAMConfiguration.xml y ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="8cdc4-117">Save and close the BAMConfiguration.xml file.</span></span>  
  
7. <span data-ttu-id="8cdc4-118">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8cdc4-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="8cdc4-119">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="8cdc4-119">At the command prompt, navigate to the following directory:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="8cdc4-120">Tracking</span><span class="sxs-lookup"><span data-stu-id="8cdc4-120">Tracking</span></span>  
  
9. <span data-ttu-id="8cdc4-121">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="8cdc4-121">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="8cdc4-122">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="8cdc4-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cdc4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cdc4-123">See Also</span></span>  
 [<span data-ttu-id="8cdc4-124">Mover bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8cdc4-124">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)