---
title: Desinstalar el Acelerador de BizTalk RosettaNet (BTARN) en BizTalk Server | Documentos de Microsoft"
description: "Anular la implementación de artefactos y quitar la configuración de BTARN para quitar el Acelerador de BizTalk Server"
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
ms.author: mandia
ms.openlocfilehash: 8d289a3705eb0c127dc4d2637c2d6ffd3c122b36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="uninstall-the-rosettanet-accelerator"></a><span data-ttu-id="7018e-103">Desinstale el Acelerador para RosettaNet</span><span class="sxs-lookup"><span data-stu-id="7018e-103">Uninstall the RosettaNet accelerator</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7018e-104">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="7018e-104">Before you begin</span></span>
  
* <span data-ttu-id="7018e-105">Si solo ejecuta **Setup.exe**, el proceso de desinstalación no quita los artefactos de supervisión de la actividad económica (BAM), los artefactos de BizTalk, los directorios virtuales de Internet Information Services (IIS) y grupos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7018e-105">If you only run **Setup.exe**, the uninstall process does not remove the Business Activity Monitoring (BAM) artifacts, the BizTalk artifacts, Internet Information Services (IIS) virtual directories, and application pools.</span></span>  
  
* <span data-ttu-id="7018e-106">Si ha usado la **bucle invertido** utilidad para crear acuerdos espejo para la implementación de un solo equipo, a continuación, ejecutar la herramienta con el **/deshabilitar <** **principal organización**  **>**  opción antes de eliminar los asociados en el **consola de administración de BTARN**.</span><span class="sxs-lookup"><span data-stu-id="7018e-106">If you used the **Loopback** utility to create mirror agreements for a single-computer deployment, then run the tool with the **/disable <** **home organization** **>** option before deleting the partners in the **BTARN Administration Console**.</span></span>  
  
* <span data-ttu-id="7018e-107">Si este servidor forma parte de una implementación de varios equipos, no podrán ejecutarse los **BtarnClean** utilidad o anular la implementación de los ensamblados BTARN manualmente.</span><span class="sxs-lookup"><span data-stu-id="7018e-107">If this server is part of a multi-computer deployment, do not run the **BtarnClean** utility or manually undeploy the BTARN assemblies.</span></span> <span data-ttu-id="7018e-108">Quitar los artefactos en un equipo, interrumpe la funcionalidad de los otros equipos.</span><span class="sxs-lookup"><span data-stu-id="7018e-108">Removing the artifacts on one computer breaks the functionality of the other computers.</span></span>  <span data-ttu-id="7018e-109">Si desea desinstalar BTARN en todos los servidores, a continuación, ejecute el **BtarnClean** utilidad.</span><span class="sxs-lookup"><span data-stu-id="7018e-109">If you want to uninstall BTARN from all the servers, then run the **BtarnClean** utility.</span></span> 

  
## <a name="undeploy-the-artifacts"></a><span data-ttu-id="7018e-110">Anular la implementación de los artefactos</span><span class="sxs-lookup"><span data-stu-id="7018e-110">Undeploy the artifacts</span></span>  

<span data-ttu-id="7018e-111">Se recomienda realizar copias de seguridad los artefactos de BAM antes de anular la implementación.</span><span class="sxs-lookup"><span data-stu-id="7018e-111">We recommend backing up your BAM artifacts before undeploying.</span></span> 

1. <span data-ttu-id="7018e-112">Anular la implementación de todos los artefactos BAM que ha implementado:</span><span class="sxs-lookup"><span data-stu-id="7018e-112">Undeploy all the BAM artifacts that you deployed:</span></span>  
  
    1.  <span data-ttu-id="7018e-113">En el símbolo del sistema, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="7018e-113">At the command prompt, run the following command:</span></span>  
  
         ```cd %ProgramFiles%\\<BizTalk Server installation directory\>\Tracking```
  
    2.  <span data-ttu-id="7018e-114">En el símbolo del sistema donde se instaló la IU de seguimiento, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7018e-114">At the command prompt where the tracking UI was installed, run the following command:</span></span>  
  
         ```bm remove-all DefinitionFile:"%ProgramFiles%\\<installation directory\>\BAMTracking\tracking.xml"```
  
        > [!NOTE]
        >  <span data-ttu-id="7018e-115">Para obtener más información acerca de BAM, consulte [administrar Business Activity Monitoring](../../core/managing-bam.md)</span><span class="sxs-lookup"><span data-stu-id="7018e-115">For more information about BAM, see [Managing Business Activity Monitoring](../../core/managing-bam.md)</span></span> 
  
2.  <span data-ttu-id="7018e-116">Copia de seguridad y eliminar todos los acuerdos, socios y organizaciones internas desde la consola de administración de BTARN.</span><span class="sxs-lookup"><span data-stu-id="7018e-116">Backup and delete all the agreements, partners, and home organizations from the BTARN Management Console.</span></span> <span data-ttu-id="7018e-117">Vea el tema "Administrar la configuración de BTARN" (en el nodo de operaciones de Ayuda de BTARN) para obtener información sobre el uso de la **BtarnConfig** utilidad para hacer copia de seguridad de los acuerdos y socios.</span><span class="sxs-lookup"><span data-stu-id="7018e-117">See the "Administering the BTARN Configuration" topic (in the Operations node of BTARN Help) for information about using the **BtarnConfig** utility to back up the agreements and partners.</span></span>  
  
    > [!NOTE]
    >  * <span data-ttu-id="7018e-118">Detener y anular la implementación de los artefactos de BizTalk creados por BTARN usando la [BtarnClean](btarnclean.md) utilidad.</span><span class="sxs-lookup"><span data-stu-id="7018e-118">Stop and undeploy the BizTalk artifacts created by BTARN by using the [BtarnClean](btarnclean.md) utility.</span></span>
    >  * <span data-ttu-id="7018e-119">Quitar otros artefactos que ha implementado.</span><span class="sxs-lookup"><span data-stu-id="7018e-119">Remove any additional artifacts that you deployed.</span></span> <span data-ttu-id="7018e-120">Vea [anular la implementación de aplicaciones de BizTalk](../../core/undeploying-biztalk-applications.md) .</span><span class="sxs-lookup"><span data-stu-id="7018e-120">See [Undeploying BizTalk Applications](../../core/undeploying-biztalk-applications.md) .</span></span>
  
3.  <span data-ttu-id="7018e-121">El programa de instalación de BTARN, busque el Acelerador de BizTalk de carpeta msi\archivos de programa\Microsoft RosettaNet\SDK carpeta.</span><span class="sxs-lookup"><span data-stu-id="7018e-121">From the BTARN Setup, locate the MSI\Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK folder.</span></span> <span data-ttu-id="7018e-122">En la carpeta del SDK, haga doble clic en **BTARNClean.exe**y, a continuación, seleccione **Y** para continuar, o **N** para cancelar la ejecución de la utilidad.</span><span class="sxs-lookup"><span data-stu-id="7018e-122">In the SDK folder, double-click **BTARNClean.exe**, and then select **Y** to continue, or **N** to cancel running the utility.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7018e-123">Si el servidor forma parte de un escenario de implementación de varios equipos, puede omitir el paso 3.</span><span class="sxs-lookup"><span data-stu-id="7018e-123">If your server is part of a multi-computer deployment scenario, you can skip step 3.</span></span> <span data-ttu-id="7018e-124">Anular la implementación de recursos compartidos, interrumpe la funcionalidad de los demás servidores de la implementación.</span><span class="sxs-lookup"><span data-stu-id="7018e-124">Undeploying any shared resources breaks the functionality on the other servers in the deployment.</span></span>  
  
4.  <span data-ttu-id="7018e-125">Anule la implementación de los ensamblados personalizados que haya creado e implementado.</span><span class="sxs-lookup"><span data-stu-id="7018e-125">Undeploy any custom assemblies that you created and deployed.</span></span>  
  
5.  <span data-ttu-id="7018e-126">En el símbolo del sistema, vaya a BizTalk Server \Program <your version>\Tracking.</span><span class="sxs-lookup"><span data-stu-id="7018e-126">At the command prompt, go to \Program Files\Microsoft BizTalk Server <your version>\Tracking.</span></span> <span data-ttu-id="7018e-127">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7018e-127">Run the following command:</span></span> 

    ```BM UNDEPLOY ALL <drive\>:\Program Files\\<installation directory\>\BAMTracking\tracking.xml```
  
## <a name="unconfigure-btarn"></a><span data-ttu-id="7018e-128">Quitar la configuración de BTARN</span><span class="sxs-lookup"><span data-stu-id="7018e-128">Unconfigure BTARN</span></span>
  
1.  <span data-ttu-id="7018e-129">Busque y ejecute lo siguiente para quitar la configuración de BTARN:</span><span class="sxs-lookup"><span data-stu-id="7018e-129">Locate and run the following to unconfigure BTARN:</span></span>  
  
     <span data-ttu-id="7018e-130">***< unidad\>*****: \Program archivos\\< directorio de instalación\>\Configuration.exe /u** </span><span class="sxs-lookup"><span data-stu-id="7018e-130">***<drive\>***  **:\Program Files\\<installation directory\>\Configuration.exe /u**</span></span>  
  
2.  <span data-ttu-id="7018e-131">En el Panel de Control, haga doble clic en **agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="7018e-131">In Control Panel, double-click **Add or Remove Programs**.</span></span>  
  
3.  <span data-ttu-id="7018e-132">En el **programas actualmente instalados** lista, haga clic en **Acelerador de Microsoft BizTalk para RosettaNet**y, a continuación, haga clic en **cambiar o quitar**.</span><span class="sxs-lookup"><span data-stu-id="7018e-132">In the **Currently installed programs** list, click **Microsoft BizTalk Accelerator for RosettaNet**, and then click **Change/Remove**.</span></span>  
  
4.  <span data-ttu-id="7018e-133">En el **mantenimiento del programa** cuadro de diálogo, seleccione **quitar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7018e-133">In the **Program Maintenance** dialog box, select **Remove**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="7018e-134">En el **resumen** cuadro de diálogo, haga clic en **desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="7018e-134">In the **Summary** dialog box, click **Uninstall**.</span></span>  
  
6.  <span data-ttu-id="7018e-135">En el **ha completado la desinstalación** cuadro de diálogo, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7018e-135">In the **Uninstall Completed** dialog box, click **Finish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7018e-136">El proceso de desinstalación no quita las bases de datos BTARN (BTARNARCHIVE, BTARNCONFIG y BTARNDATA).</span><span class="sxs-lookup"><span data-stu-id="7018e-136">The uninstallation process does not remove the BTARN databases (BTARNARCHIVE, BTARNCONFIG, and BTARNDATA).</span></span> <span data-ttu-id="7018e-137">Debe quitarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="7018e-137">You must manually remove them.</span></span>  
  
7.  <span data-ttu-id="7018e-138">Abra **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="7018e-138">Open **SQL Server Management Studio**.</span></span>  
  
8.  <span data-ttu-id="7018e-139">En el **conectar al servidor** cuadro de diálogo, haga clic en **conectar**.</span><span class="sxs-lookup"><span data-stu-id="7018e-139">In the **Connect to Server** dialog box, click **Connect**.</span></span>  
  
9. <span data-ttu-id="7018e-140">Expanda el **bases de datos** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="7018e-140">Expand the **Databases** node in the left pane.</span></span> <span data-ttu-id="7018e-141">Haga clic en uno de las bases de datos BTARN y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="7018e-141">Right-click one of the BTARN databases, and then click **Delete**.</span></span>  
  
10. <span data-ttu-id="7018e-142">En el **Eliminar objeto** cuadro de diálogo, seleccione **cerrar conexiones existentes**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7018e-142">In the **Delete Object** dialog box, select **Close Existing Connections**, and then click **OK**.</span></span>  
  
