---
title: Instalar el FileAct e interactuar adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf387d59-373b-4151-9dfd-30c511978862
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48a3beccd6179bcb4526ba41f4f41a7923f5f966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-fileact-and-interact-adapter"></a><span data-ttu-id="6779a-102">Instalar el FileAct e interactuar adaptador</span><span class="sxs-lookup"><span data-stu-id="6779a-102">Install the FileAct and InterAct Adapter</span></span>
<span data-ttu-id="6779a-103">Esta sección proporciona instrucciones para instalar [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] : para SWIFT.</span><span class="sxs-lookup"><span data-stu-id="6779a-103">This section provides instructions to install [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] – for SWIFT.</span></span> <span data-ttu-id="6779a-104">Antes de instalar a los adaptadores, debe instalar el software necesario.</span><span class="sxs-lookup"><span data-stu-id="6779a-104">Before you install the adapters, you must install the prerequisite software.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6779a-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6779a-105">Prerequisites</span></span>  

* <span data-ttu-id="6779a-106">Inicie sesión con una cuenta que sea miembro del grupo Administradores local y un miembro del grupo Administradores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6779a-106">Sign in with an account that is member of the local administrators group, and a member of the BizTalk Server Administrators group</span></span>
  
## <a name="step-1-install-biztalk-server-and-configure-bam"></a><span data-ttu-id="6779a-107">Paso 1: Instalar BizTalk Server y configurar BAM</span><span class="sxs-lookup"><span data-stu-id="6779a-107">Step 1: Install BizTalk Server and configure BAM</span></span>

1. <span data-ttu-id="6779a-108">Instalar [BizTalk Server 2016](../../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md), o [BizTalk Server 2013 R2 / 2013](../../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md)e instalar la supervisión de la actividad económica (BAM).</span><span class="sxs-lookup"><span data-stu-id="6779a-108">Install [BizTalk Server 2016](../../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md), or [BizTalk Server 2013 R2 / 2013](../../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md), and install Business Activity Monitoring (BAM).</span></span>

2. <span data-ttu-id="6779a-109">Configurar [BizTalk Server](../../install-and-config-guides/configure-biztalk-server.md)y configurar la supervisión de la actividad económica (BAM).</span><span class="sxs-lookup"><span data-stu-id="6779a-109">Configure [BizTalk Server](../../install-and-config-guides/configure-biztalk-server.md), and configure Business Activity Monitoring (BAM).</span></span>
  
3. <span data-ttu-id="6779a-110">Asegúrese de que tiene suficientes privilegios de seguridad para tener acceso a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="6779a-110">Make sure you have enough security privileges to access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="6779a-111">[Derechos de seguridad mínimos para BizTalk Server](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) es un recurso excelente.</span><span class="sxs-lookup"><span data-stu-id="6779a-111">[Minimum Security Rights for BizTalk Server](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) is a great resource.</span></span>
  
## <a name="step-2-install-biztalk-accelerator-for-swift-a4swift"></a><span data-ttu-id="6779a-112">Paso 2: Instalar el Acelerador de BizTalk para SWIFT (A4SWIFT)</span><span class="sxs-lookup"><span data-stu-id="6779a-112">Step 2: Install BizTalk Accelerator for SWIFT (A4SWIFT)</span></span>  

<span data-ttu-id="6779a-113">Instalar y configurar el [Acelerador de BizTalk para SWIFT](../../adapters-and-accelerators/accelerator-swift/install-configure-and-deploy-the-biztalk-accelerator-for-swift.md).</span><span class="sxs-lookup"><span data-stu-id="6779a-113">Install and configure the [BizTalk Accelerator for SWIFT](../../adapters-and-accelerators/accelerator-swift/install-configure-and-deploy-the-biztalk-accelerator-for-swift.md).</span></span>

  
## <a name="step-3-install-swiftalliance-gateway-sag"></a><span data-ttu-id="6779a-114">Paso 3: Instalar la puerta de enlace de SWIFTAlliance (SAG)</span><span class="sxs-lookup"><span data-stu-id="6779a-114">Step 3: Install SWIFTAlliance Gateway (SAG)</span></span>  
 <span data-ttu-id="6779a-115">Antes de instalar a los adaptadores FileAct e InterAct, cree el SAG mensaje socios, dos puntos finales y las reglas de enrutamiento y probar la conectividad SAG en el equipo donde instale los adaptadores FileAct e InterAct.</span><span class="sxs-lookup"><span data-stu-id="6779a-115">Before you install the FileAct and InterAct adapters, create the SAG Message Partners, End Points, and Routing Rules, and test the SAG connectivity on the computer where you install the FileAct and InterAct adapters.</span></span>

<span data-ttu-id="6779a-116">Vea [https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway](https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway) para obtener detalles específicos sobre la puerta de enlace de SWIFTAlliance.</span><span class="sxs-lookup"><span data-stu-id="6779a-116">See [https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway](https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway) for specific details on the SWIFTAlliance Gateway.</span></span>  

## <a name="step-4-install-the-biztalk-fileact-and-interact-adapters"></a><span data-ttu-id="6779a-117">Paso 4: Instalar a los adaptadores de BizTalk FileAct e InterAct</span><span class="sxs-lookup"><span data-stu-id="6779a-117">Step 4: Install the BizTalk FileAct and InterAct adapters</span></span>  
  
1. <span data-ttu-id="6779a-118">Ejecute el **Setup.exe** como administrador para iniciar la instalación.</span><span class="sxs-lookup"><span data-stu-id="6779a-118">Run the **Setup.exe** as administrator to start the installation.</span></span>  
  
2.  <span data-ttu-id="6779a-119">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="6779a-119">Select **Install**.</span></span>  
  
3.  <span data-ttu-id="6779a-120">Escriba el nombre de usuario y el nombre de la organización y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6779a-120">Enter your user name and organization name, and then select **Next**.</span></span>  
  
4.  <span data-ttu-id="6779a-121">**Aceptar** el contrato de licencia.</span><span class="sxs-lookup"><span data-stu-id="6779a-121">**Accept** the license agreement.</span></span>
  
5.  <span data-ttu-id="6779a-122">En el **opciones de instalación** página, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="6779a-122">On the **Installation Options** page, do one of the following:</span></span>  
  
    -   <span data-ttu-id="6779a-123">Seleccione el **completar** opción para instalar todos los componentes de la FileAct e interactuar adaptadores.</span><span class="sxs-lookup"><span data-stu-id="6779a-123">Select the **Complete** option to install all components of the FileAct and InterAct adapters.</span></span>  
  
    -   <span data-ttu-id="6779a-124">Seleccione el **personalizado** opción para elegir qué componentes va a instalar.</span><span class="sxs-lookup"><span data-stu-id="6779a-124">Select the **Custom** option to choose which components to install.</span></span>  
  
     <span data-ttu-id="6779a-125">Compruebe la ubicación de instalación, o seleccione **examinar** para seleccionar una ubicación de instalación diferente.</span><span class="sxs-lookup"><span data-stu-id="6779a-125">Verify the installation location, or select **Browse** to select a different installation location.</span></span> <span data-ttu-id="6779a-126">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6779a-126">Select **Next**.</span></span>  
  
6.  <span data-ttu-id="6779a-127">En el **resumen** página, seleccione **instalar** para instalar los componentes de la lista.</span><span class="sxs-lookup"><span data-stu-id="6779a-127">On the **Summary** page, select **Install** to install the listed components.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6779a-128">Cuando **ejecutar el Asistente para configuración** está activada (valor predeterminado), el **FileAct de BizTalk de Microsoft e interactuar configuración del adaptador** asistente se ejecuta automáticamente cuando se selecciona **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6779a-128">When **Run Configuration Wizard** is selected (the default), the **Microsoft BizTalk FileAct and InterAct Adapter Configuration** wizard runs automatically when you select **Finish**.</span></span>  
  
7. <span data-ttu-id="6779a-129">Cuando se complete la instalación, seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6779a-129">When the installation completes, select **Finish**.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="6779a-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6779a-130">Next steps</span></span>

[<span data-ttu-id="6779a-131">Configure el adaptador de FileAct e InterAct</span><span class="sxs-lookup"><span data-stu-id="6779a-131">Configure the FileAct and InterAct adapter</span></span>](../../adapters-and-accelerators/fileact-interact/configure-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="6779a-132">Mensajes de ejemplo interactuar y FileAct</span><span class="sxs-lookup"><span data-stu-id="6779a-132">Sample InterAct and FileAct messages</span></span>](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md)  
[<span data-ttu-id="6779a-133">Desinstalar o reparar el adaptador de FileAct e InterAct</span><span class="sxs-lookup"><span data-stu-id="6779a-133">Uninstall or repair the FileAct and InterAct adapter</span></span>](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="6779a-134">Lea la problemas conocidos de instalación</span><span class="sxs-lookup"><span data-stu-id="6779a-134">Read the installation known issues</span></span>](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)
  
## <a name="see-also"></a><span data-ttu-id="6779a-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="6779a-135">See Also</span></span>  
[<span data-ttu-id="6779a-136">Introducción a los adaptadores FileAct e InterAct</span><span class="sxs-lookup"><span data-stu-id="6779a-136">Getting started with the FileAct and InterAct adapters</span></span>](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)  
[<span data-ttu-id="6779a-137">Descripción de la arquitectura de adaptador FileAct e InterAct</span><span class="sxs-lookup"><span data-stu-id="6779a-137">Understanding FileAct and InterAct adapter architecture</span></span>](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)