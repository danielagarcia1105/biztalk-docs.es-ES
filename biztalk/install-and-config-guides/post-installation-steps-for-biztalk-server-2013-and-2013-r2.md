---
title: "Pasos posteriores a la instalación de BizTalk Server 2013 y 2013 R2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3b47843-9da5-4144-8b84-135494b8ab43
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b86d8c4c1e1a22dad349c2cc8c2be5ca4b206b2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="post-installation-steps-for-biztalk-server-2013-and-2013-r2"></a><span data-ttu-id="20d23-102">Pasos posteriores a la instalación de BizTalk Server 2013 y 2013 R2</span><span class="sxs-lookup"><span data-stu-id="20d23-102">Post-installation Steps for BizTalk Server 2013 and 2013 R2</span></span>
  
##  <a name="BKMK_NamedPipes"></a> <span data-ttu-id="20d23-103">Habilitar TCP/IP y canalizaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="20d23-103">Enable TCP/IP and Named Pipes</span></span>  
  
1.  <span data-ttu-id="20d23-104">Abra el **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="20d23-104">Open **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="20d23-105">Expanda **Configuración de red de SQL Server** y seleccione **Protocolos para MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="20d23-105">Expand **SQL Server Network Configuration**, and select **Protocols for MSSQLSERVER**.</span></span>  
  
4.  <span data-ttu-id="20d23-106">Compruebe que están habilitadas las opciones **TCP/IP** y **Canalizaciones con nombre**.</span><span class="sxs-lookup"><span data-stu-id="20d23-106">Verify that both **TCP/IP** and **Named Pipes** are enabled.</span></span> <span data-ttu-id="20d23-107">Si están habilitadas, continúe en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="20d23-107">If enabled, proceed to the next step.</span></span>  
  
     <span data-ttu-id="20d23-108">Si no están habilitadas:</span><span class="sxs-lookup"><span data-stu-id="20d23-108">If not enabled:</span></span>  
  
    -   <span data-ttu-id="20d23-109">Haga clic con el botón derecho en el protocolo y, después, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="20d23-109">Right-click the protocol, and then click **Enable**.</span></span>  
  
    -   <span data-ttu-id="20d23-110">Repita los pasos para habilitar el otro protocolo, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="20d23-110">Repeat to enable the other protocol if necessary.</span></span>  
  
    -   <span data-ttu-id="20d23-111">En el panel izquierdo, haga clic en **Servicios de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="20d23-111">In the left-hand pane, click **SQL Server Services**.</span></span>  
  
    -   <span data-ttu-id="20d23-112">En el panel derecho, haga clic con el botón derecho en **SQL Server (MSSQLSERVER)** y, después, haga clic en **Detener**.</span><span class="sxs-lookup"><span data-stu-id="20d23-112">In the right-hand pane, right-click **SQL Server (MSSQLSERVER)**, and click **Stop**.</span></span>  
  
    -   <span data-ttu-id="20d23-113">Después de detener el servicio, haga clic con el botón derecho en **SQL Server (MSSQLSERVER)** y haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="20d23-113">When the service has stopped, right-click **SQL Server (MSSQLSERVER)**, and click **Start**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="20d23-114">Si usa [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)], puede que el servicio **NS$BAMAlerts** se detenga.</span><span class="sxs-lookup"><span data-stu-id="20d23-114">If you are using [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)], the **NS$BAMAlerts** service may be stopped.</span></span> <span data-ttu-id="20d23-115">Reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="20d23-115">Restart the service.</span></span>  
  
5.  <span data-ttu-id="20d23-116">Cierre el **Administrador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="20d23-116">Close the **Configuration Manager**.</span></span>  
  
##  <a name="BKMK_DTC"></a> <span data-ttu-id="20d23-117">Habilitar el DTC en el servidor de host local</span><span class="sxs-lookup"><span data-stu-id="20d23-117">Enable DTC on the Local Host Server</span></span>  
  
1.  <span data-ttu-id="20d23-118">Abra Servicios de componentes:</span><span class="sxs-lookup"><span data-stu-id="20d23-118">Open Component Services:</span></span>  
  
     <span data-ttu-id="20d23-119">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**: pulse la tecla Windows y escriba **Servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="20d23-119">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : Select the Windows button, and type **Component Services**.</span></span> <span data-ttu-id="20d23-120">En la ventana Resultados, seleccione **Servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="20d23-120">In the Results window, select **Component Services**.</span></span>  
  
     <span data-ttu-id="20d23-121">**Windows 8.1**: pulse la tecla Windows y escriba **Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="20d23-121">**Windows 8.1**: Select the Windows button, and type **Administrative Tools**.</span></span> <span data-ttu-id="20d23-122">En la ventana Buscar, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="20d23-122">In the Search window, select **Settings**.</span></span> <span data-ttu-id="20d23-123">En la ventana Resultados, haga clic en **Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="20d23-123">In the Results window, click **Administrative Tools**.</span></span> <span data-ttu-id="20d23-124">Haga doble clic en **Servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="20d23-124">Double-click **Component Services**.</span></span>  
  
     <span data-ttu-id="20d23-125">**Windows 7 SP1**: seleccione **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="20d23-125">**Windows 7 SP1**: Select **Start**.</span></span> <span data-ttu-id="20d23-126">En el cuadro de texto **Buscar**, escriba **Servicios de componentes** y haga clic en él para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="20d23-126">In the **Search** text box, type **Component Services**, and click it to open.</span></span>  
  
2.  <span data-ttu-id="20d23-127">En el árbol de consola, expanda **Servicios de componentes**, **Equipos**, **Mi PC**, **Coordinador de transacciones distribuidas** y, después, haga clic en **DTC local**.</span><span class="sxs-lookup"><span data-stu-id="20d23-127">In the console tree, expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, and then click **Local DTC**.</span></span>  
  
3.  <span data-ttu-id="20d23-128">Haga clic con el botón derecho en **DTC local** y seleccione **Propiedades** para abrir el cuadro de diálogo **Propiedades: DTC local**.</span><span class="sxs-lookup"><span data-stu-id="20d23-128">Right-click **Local DTC** and select **Properties** to open the **Local DTC Properties**.</span></span>  
  
4.  <span data-ttu-id="20d23-129">Seleccione la pestaña **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="20d23-129">Select the **Security** tab.</span></span>  
  
5.  <span data-ttu-id="20d23-130">Compruebe que están seleccionadas las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="20d23-130">Confirm the following options are checked:</span></span>  
  
    -   <span data-ttu-id="20d23-131">**Acceso a DTC desde la red**</span><span class="sxs-lookup"><span data-stu-id="20d23-131">**Network DTC Access**</span></span>  
  
    -   <span data-ttu-id="20d23-132">**Permitir entrantes**</span><span class="sxs-lookup"><span data-stu-id="20d23-132">**Allow Inbound**</span></span>  
  
    -   <span data-ttu-id="20d23-133">**Permitir salientes**</span><span class="sxs-lookup"><span data-stu-id="20d23-133">**Allow Outbound**</span></span>  
  
    -   <span data-ttu-id="20d23-134">**No se requiere autenticación**</span><span class="sxs-lookup"><span data-stu-id="20d23-134">**No Authentication Required**</span></span>  
  
     <span data-ttu-id="20d23-135">Para conocer otras opciones necesarias, consulte [Solucionar problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span><span class="sxs-lookup"><span data-stu-id="20d23-135">For additional settings that may be needed, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>  
  
6.  <span data-ttu-id="20d23-136">Seleccione **Aceptar** para cerrar el cuadro de diálogo **Propiedades: DTC local**.</span><span class="sxs-lookup"><span data-stu-id="20d23-136">Select **OK** to close the **Local DTC Properties** dialog box.</span></span> <span data-ttu-id="20d23-137">Reinicie el servicio MSDTC si se le pide.</span><span class="sxs-lookup"><span data-stu-id="20d23-137">Restart the MSDTC service if prompted.</span></span>  
  
7.  <span data-ttu-id="20d23-138">Cierre **Servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="20d23-138">Close **Component Services**.</span></span>  
  
##  <a name="BKMK_Firewall"></a> <span data-ttu-id="20d23-139">Configurar el Firewall de Windows para habilitar DTC</span><span class="sxs-lookup"><span data-stu-id="20d23-139">Configure Windows Firewall to Enable DTC</span></span>  
  
1.  <span data-ttu-id="20d23-140">Abra el **Firewall de Windows**:</span><span class="sxs-lookup"><span data-stu-id="20d23-140">Open **Windows Firewall**:</span></span>  
  
     <span data-ttu-id="20d23-141">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**: pulse la tecla Windows y escriba **Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="20d23-141">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : Click the Windows button, and type **Windows Firewall**.</span></span> <span data-ttu-id="20d23-142">En la ventana Resultados, haga clic en **Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="20d23-142">In the Results window, click **Windows Firewall**.</span></span>  
  
     <span data-ttu-id="20d23-143">**Windows 8.1**: pulse la tecla Windows y escriba **Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="20d23-143">**Windows 8.1**: Click the Windows button, and type **Windows Firewall**.</span></span> <span data-ttu-id="20d23-144">En la ventana Buscar, haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="20d23-144">In the Search window, click **Settings**.</span></span> <span data-ttu-id="20d23-145">En la ventana Resultados, haga clic en **Firewall de Windows**.</span><span class="sxs-lookup"><span data-stu-id="20d23-145">In the Results window, click **Windows Firewall**.</span></span>  
  
     <span data-ttu-id="20d23-146">**Windows 7 SP1**: haga clic en **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="20d23-146">**Windows 7 SP1**: Click **Start**.</span></span> <span data-ttu-id="20d23-147">En el cuadro de texto **Buscar**, escriba **Firewall de Windows** y haga clic en él para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="20d23-147">In the **Search** text box, type **Windows Firewall**, and click it to open.</span></span>  
  
2.  <span data-ttu-id="20d23-148">Haga clic en **Configuración avanzada** y, después, en **Reglas de entrada**.</span><span class="sxs-lookup"><span data-stu-id="20d23-148">Click **Advanced Settings** and click **Inbound Rules**.</span></span>  
  
3.  <span data-ttu-id="20d23-149">En el panel **Reglas de entrada**, haga clic con el botón derecho en **Coordinador de transacciones distribuidas** \* (según corresponda) y, después, haga clic en **Habilitar regla**.</span><span class="sxs-lookup"><span data-stu-id="20d23-149">In the **Inbound Rules** pane, right-click **Distributed Transaction Coordinator** \* (as appropriate), and then click **Enable Rule**.</span></span>  
  
4.  <span data-ttu-id="20d23-150">Haga clic en **Reglas de salida**.</span><span class="sxs-lookup"><span data-stu-id="20d23-150">Click **Outbound Rules**.</span></span>  
  
5.  <span data-ttu-id="20d23-151">En el panel **Reglas de salida**, haga clic con el botón derecho en **Coordinador de transacciones distribuidas** \* (según corresponda) y, después, haga clic en **Habilitar regla**.</span><span class="sxs-lookup"><span data-stu-id="20d23-151">In the **Outbound Rules** pane, right-click **Distributed Transaction Coordinator** \* (as appropriate), and then click **Enable Rule**.</span></span>  
  
6.  <span data-ttu-id="20d23-152">En el **Panel de control**, cambie la vista para que se muestre una lista de iconos y, después, haga doble clic en **Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="20d23-152">On the **Control Panel**, change the view to list by icons, and then double-click **Administrative Tools**.</span></span>  
  
7.  <span data-ttu-id="20d23-153">Haga doble clic en **Servicios**.</span><span class="sxs-lookup"><span data-stu-id="20d23-153">Double-click **Services**.</span></span>  
  
8.  <span data-ttu-id="20d23-154">Haga clic con el botón derecho en **Aplicación del sistema COM+**, elija **Reiniciar** y espere hasta que se reinicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="20d23-154">Right-click **COM+ System Application**, click **Restart**, and wait for the service to restart.</span></span>  
  
9. <span data-ttu-id="20d23-155">Haga clic con el botón derecho y reinicie el servicio **Coordinador de transacciones distribuidas**.</span><span class="sxs-lookup"><span data-stu-id="20d23-155">Right-click and restart the **Distributed Transaction Coordinator** service.</span></span>  
  
10. <span data-ttu-id="20d23-156">Haga clic con el botón derecho y reinicie el servicio **SQL Server (MSSQLSERVER)**.</span><span class="sxs-lookup"><span data-stu-id="20d23-156">Right-click and restart the **SQL Server (MSSQLSERVER)** service.</span></span>  
  
11. <span data-ttu-id="20d23-157">Cierre **Servicios (locales)** y, después, cierre **Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="20d23-157">Close **Services (Local)**, and then close **Administrative Tools**.</span></span>  
  
##  <a name="BKMK_SQLAgent"></a> <span data-ttu-id="20d23-158">Configurar trabajos del Agente SQL</span><span class="sxs-lookup"><span data-stu-id="20d23-158">Configure SQL Agent Jobs</span></span>  
  
|<span data-ttu-id="20d23-159">Trabajo</span><span class="sxs-lookup"><span data-stu-id="20d23-159">Job</span></span>|<span data-ttu-id="20d23-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="20d23-160">Description</span></span>|<span data-ttu-id="20d23-161">Motivos para la configuración</span><span class="sxs-lookup"><span data-stu-id="20d23-161">Why configure</span></span>|  
|---------|-----------------|-------------------|  
|<span data-ttu-id="20d23-162">**Copia de seguridad de BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="20d23-162">**Backup BizTalk Server**</span></span>|<span data-ttu-id="20d23-163">Este trabajo de agente SQL realiza una copia de seguridad de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y de los archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="20d23-163">This SQL Agent job backs up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and the log files.</span></span> <span data-ttu-id="20d23-164">Al configurar el trabajo, es necesario determinar parámetros como, por ejemplo, la frecuencia y la ubicación de archivos.</span><span class="sxs-lookup"><span data-stu-id="20d23-164">When configuring the job, you determine parameters like frequency and file location.</span></span><br /><br /> <span data-ttu-id="20d23-165">Los vínculos siguientes describen el trabajo de agente SQL y sus parámetros:</span><span class="sxs-lookup"><span data-stu-id="20d23-165">The following links describe the SQL Agent job and its parameters:</span></span><br /><br /> <span data-ttu-id="20d23-166">[Realizar una copia de seguridad y una restauración de las bases de datos de BizTalk Server](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="20d23-166">[Backing Up and Restoring BizTalk Server Databases](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)</span></span><br /><br /> <span data-ttu-id="20d23-167">[Cómo configurar el trabajo de copia de seguridad de BizTalk Server](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="20d23-167">[How to Configure the Backup BizTalk Server Job](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)</span></span>|<span data-ttu-id="20d23-168">Este trabajo del agente SQL también trunca los registros de transacción, lo que ayuda a mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="20d23-168">This SQL Agent job also truncates the transaction logs, which helps improve performance.</span></span><br /><br /> <span data-ttu-id="20d23-169">El trabajo **Copia de seguridad de BizTalk Server** no quita ni elimina ningún archivo de copia de seguridad, incluidos los archivos más antiguos.</span><span class="sxs-lookup"><span data-stu-id="20d23-169">The **Backup BizTalk Server** job does not remove or delete backup files, including older files.</span></span> <span data-ttu-id="20d23-170">Para eliminar archivos de copia de seguridad, consulte [Se produce un error en el trabajo "Backup BizTalk Server" cuando los archivos de copia de seguridad se acumulan con el tiempo en el servidor de base de datos de Microsoft BizTalk Server](http://support.microsoft.com/kb/982546).</span><span class="sxs-lookup"><span data-stu-id="20d23-170">To delete backup files, refer to [The "Backup BizTalk Server" job fails when backup files accumulate over time in the Microsoft BizTalk Server database server](http://support.microsoft.com/kb/982546).</span></span>|  
|<span data-ttu-id="20d23-171">**Archivo y purga DTA**</span><span class="sxs-lookup"><span data-stu-id="20d23-171">**DTA Purge and Archive**</span></span>|<span data-ttu-id="20d23-172">Este trabajo de agente SQL trunca y archiva la base de datos de seguimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="20d23-172">This SQL Agent job truncates and archives the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Tracking database (BizTalkDTADb).</span></span> <span data-ttu-id="20d23-173">Al configurar el trabajo, es necesario determinar parámetros como, por ejemplo, el número de días que se deben conservar las instancias completadas o el número de días que se deben conservar todos los datos.</span><span class="sxs-lookup"><span data-stu-id="20d23-173">When configuring the job, you determine parameters like how many days to keep completed instances and how many to days to keep all data.</span></span><br /><br /> <span data-ttu-id="20d23-174">Los vínculos siguientes describen el trabajo de agente SQL y sus parámetros:</span><span class="sxs-lookup"><span data-stu-id="20d23-174">The following links describe the SQL Agent job and its parameters:</span></span><br /><br /> <span data-ttu-id="20d23-175">[Archivar y purgar la base de datos de seguimiento de BizTalk](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="20d23-175">[Archiving and Purging the BizTalk Tracking Database](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)</span></span><br /><br /> <span data-ttu-id="20d23-176">[Cómo configurar el trabajo DTA Purge and Archive](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="20d23-176">[How to Configure the DTA Purge and Archive Job](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx)</span></span>|<span data-ttu-id="20d23-177">Este trabajo de agente SQL repercute directamente en el rendimiento, ya que mantiene el host de seguimiento y purga los eventos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="20d23-177">This SQL Agent job directly impacts performance by maintaining the Tracking host and purging tracking events.</span></span><br /><br /> <span data-ttu-id="20d23-178">Entre los temas de rendimiento se incluyen:</span><span class="sxs-lookup"><span data-stu-id="20d23-178">Performance topics include:</span></span><br /><br /> [<span data-ttu-id="20d23-179">Cómo mantener y solucionar problemas de bases de datos de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="20d23-179">How to maintain and troubleshoot BizTalk Server databases</span></span>](http://support.microsoft.com/kb/952555)<br /><br /> <span data-ttu-id="20d23-180">[Instrucciones para ajustar el tamaño de la base de datos de seguimiento](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="20d23-180">[Tracking Database Sizing Guidelines](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)</span></span>|  
  
 <span data-ttu-id="20d23-181">**Notas**</span><span class="sxs-lookup"><span data-stu-id="20d23-181">**Additional**</span></span>  
  
-   <span data-ttu-id="20d23-182">Una vez instalado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se crearán varios trabajos del agente SQL, tal como se describe en los vínculos siguientes:</span><span class="sxs-lookup"><span data-stu-id="20d23-182">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed, several SQL Agent jobs are automatically created, as described in the following links:</span></span>  
  
     [<span data-ttu-id="20d23-183">Descripción de los trabajos del agente de SQL en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="20d23-183">Description of the SQL Server Agent jobs in BizTalk Server</span></span>](http://support.microsoft.com/kb/919776)  
  
     <span data-ttu-id="20d23-184">[Estructura de base de datos y trabajos](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="20d23-184">[Database Structure and Jobs](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)</span></span>  
  
##  <a name="BKMK_InstallCU"></a> <span data-ttu-id="20d23-185">Instalar actualizaciones acumulativas</span><span class="sxs-lookup"><span data-stu-id="20d23-185">Install Cumulative Updates</span></span>  
 <span data-ttu-id="20d23-186">Después de instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], instale las actualizaciones acumulativas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que haya disponibles en Windows Update.</span><span class="sxs-lookup"><span data-stu-id="20d23-186">After you install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], install any [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cumulative updates listed in Windows Update.</span></span> <span data-ttu-id="20d23-187">En el [artículo 2555976 de Knowledge Base](http://support.microsoft.com/kb/2555976) se enumeran los Service Pack y las actualizaciones acumulativas disponibles.</span><span class="sxs-lookup"><span data-stu-id="20d23-187">[KB article 2555976](http://support.microsoft.com/kb/2555976) lists available service packs and cumulative updates.</span></span>  
  
## <a name="next"></a><span data-ttu-id="20d23-188">Siguiente</span><span class="sxs-lookup"><span data-stu-id="20d23-188">Next</span></span>  
[<span data-ttu-id="20d23-189">Configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="20d23-189">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)
  
## <a name="see-also"></a><span data-ttu-id="20d23-190">Ver también</span><span class="sxs-lookup"><span data-stu-id="20d23-190">See Also</span></span>  
 [<span data-ttu-id="20d23-191">Apéndice A: Instalación silenciosa</span><span class="sxs-lookup"><span data-stu-id="20d23-191">Appendix A: Silent Installation</span></span>](../install-and-config-guides/appendix-a-silent-installation.md) 
 
[<span data-ttu-id="20d23-192">Apéndice B: Instalar el adaptador de Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="20d23-192">Appendix B: Install the Microsoft SharePoint Adapter</span></span>](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)  

[<span data-ttu-id="20d23-193">Apéndice C: Archivos CAB redistribuibles</span><span class="sxs-lookup"><span data-stu-id="20d23-193">Appendix C: Redistributable CAB Files</span></span>](../install-and-config-guides/appendix-c-redistributable-cab-files.md)  

[<span data-ttu-id="20d23-194">Apéndice D: Crear el servidor SMTP</span><span class="sxs-lookup"><span data-stu-id="20d23-194">Appendix D: Create the SMTP Server</span></span>](../install-and-config-guides/appendix-d-create-the-smtp-server.md)

[<span data-ttu-id="20d23-195">Desinstalar y quitar la configuración de BizTalk Server para quitarlo</span><span class="sxs-lookup"><span data-stu-id="20d23-195">Uninstall and unconfigure BizTalk Server to remove it</span></span>](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)
