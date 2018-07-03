---
title: Cómo mover la base de datos1 del esquema de estrella de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Star Schema database [BAM], migrating
- migrating, Star Schema database [BAM]
ms.assetid: b4a5f8fc-0dc4-4987-b96f-ecd49bd4dba3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3068c9d1c72c30c51f77d9fad7b8ddf5881ed09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983413"
---
# <a name="how-to-move-the-bam-star-schema-database"></a><span data-ttu-id="807d4-102">Cómo mover la base de datos de esquema de estrella de BAM</span><span class="sxs-lookup"><span data-stu-id="807d4-102">How to Move the BAM Star Schema Database</span></span>
<span data-ttu-id="807d4-103">Este procedimiento se puede utilizar para mover la base de datos de esquema de estrella de BAM a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="807d4-103">You can use this procedure to move the BAM Star Schema database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="807d4-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="807d4-104">Prerequisites</span></span>  
 <span data-ttu-id="807d4-105">Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="807d4-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-star-schema-database"></a><span data-ttu-id="807d4-106">Para mover la base de datos de esquema de estrella de BAM</span><span class="sxs-lookup"><span data-stu-id="807d4-106">To move the BAM Star Schema database</span></span>  
  
1. <span data-ttu-id="807d4-107">Obtenga una copia del archivo .xml utilizado para restaurar BAM:</span><span class="sxs-lookup"><span data-stu-id="807d4-107">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="807d4-108">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="807d4-108">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="807d4-109">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="807d4-109">At the command prompt, navigate to the following directory:</span></span>  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="807d4-110">Tracking</span><span class="sxs-lookup"><span data-stu-id="807d4-110">Tracking</span></span>  
  
   3. <span data-ttu-id="807d4-111">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="807d4-111">At the command prompt, type:</span></span>  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="807d4-112">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="807d4-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2. <span data-ttu-id="807d4-113">Siga las instrucciones en libros en pantalla de SQL Server sobre cómo realizar una copia de seguridad de la base de datos en el servidor anterior.</span><span class="sxs-lookup"><span data-stu-id="807d4-113">Follow the instructions in SQL Server Books Online on how to back up the database on the old server.</span></span>  
  
3. <span data-ttu-id="807d4-114">Copie la base de datos de esquema de estrella de BAM en el nuevo servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="807d4-114">Copy the BAM Star Schema database to the new SQL Server.</span></span>  
  
4. <span data-ttu-id="807d4-115">Siga las instrucciones en Libros en pantalla de SQL Server para la creación de una copia de seguridad de una base de datos en el servidor nuevo.</span><span class="sxs-lookup"><span data-stu-id="807d4-115">Follow the instructions in SQL Server Books Online on how to restore the database on the new server.</span></span>  
  
5. <span data-ttu-id="807d4-116">Edite el archivo BAMConfiguration.xml y cambie el valor de ServerName en la sección StarSchemaDatabase DeploymentUnit al nombre del nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="807d4-116">Edit the BAMConfiguration.xml file and change the ServerName in the StarSchemaDatabase DeploymentUnit section to the new server name.</span></span>  
  
6. <span data-ttu-id="807d4-117">Guarde el archivo BAMConfiguration.xml y ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="807d4-117">Save and close the BAMConfiguration.xml file.</span></span>  
  
7. <span data-ttu-id="807d4-118">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="807d4-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="807d4-119">En el símbolo del sistema, desplácese al directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="807d4-119">At the command prompt, navigate to the following directory:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="807d4-120">Tracking</span><span class="sxs-lookup"><span data-stu-id="807d4-120">Tracking</span></span>  
  
9. <span data-ttu-id="807d4-121">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="807d4-121">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="807d4-122">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="807d4-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
10. <span data-ttu-id="807d4-123">Actualice la conexión 2 de SQL para cambiar el nombre de la base de datos y del servidor en todos los paquetes DTS de análisis de BAM, a los que se agrega el prefijo "BAM_AN_" mediante los pasos que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="807d4-123">Update SQL Connection 2 to change the server and database name in all BAM analysis DTS packages, which are prefixed with "BAM_AN_", by following these steps:</span></span>  
  
    1.  <span data-ttu-id="807d4-124">Abra el servidor que hospeda BAM mediante SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="807d4-124">Using SQL Server Management Studio, open the server hosting BAM.</span></span>  
  
    2.  <span data-ttu-id="807d4-125">Abra el **Data Transformation Services** carpeta.</span><span class="sxs-lookup"><span data-stu-id="807d4-125">Open the **Data Transformation Services** folder.</span></span>  
  
    3.  <span data-ttu-id="807d4-126">Abra el **paquetes locales** carpeta.</span><span class="sxs-lookup"><span data-stu-id="807d4-126">Open the **Local Packages** folder.</span></span>  
  
    4.  <span data-ttu-id="807d4-127">Abra el paquete DTS y, a continuación, haga doble clic en **conexión 2** para abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="807d4-127">Open the DTS package, and then double-click **Connection 2** to open the connection.</span></span>  
  
    5.  <span data-ttu-id="807d4-128">Seleccione el nuevo nombre de base de datos y servidor en el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="807d4-128">Select the new server and database name in the drop-down box.</span></span>  
  
11. <span data-ttu-id="807d4-129">Actualice el origen de datos en la base de datos de análisis de BAM del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="807d4-129">Update the data source in the BAM Analysis database as follows:</span></span>  
  
    1.  <span data-ttu-id="807d4-130">Abra el servidor que aloja la base de datos de análisis de BAM mediante Analysis Manager de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="807d4-130">Using SQL Server Analysis Manager, open the server hosting the BAM Analysis database.</span></span>  
  
    2.  <span data-ttu-id="807d4-131">Abra el **orígenes de datos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="807d4-131">Open the **Data Sources** folder.</span></span>  
  
    3.  <span data-ttu-id="807d4-132">Haga clic en el origen de datos para el cubo y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="807d4-132">Right-click the data source for the cube, and then click **Edit**.</span></span>  
  
    4.  <span data-ttu-id="807d4-133">En el **conexión** pestaña, escriba el nuevo nombre del servidor y el nombre de la base de datos para la base de datos de esquema de estrella de BAM y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="807d4-133">On the **Connection** tab, type the new server name and database name for the BAM Star Schema database, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="807d4-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="807d4-134">See Also</span></span>  
 [<span data-ttu-id="807d4-135">Mover bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="807d4-135">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)