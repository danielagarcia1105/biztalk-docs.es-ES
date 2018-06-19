---
title: 'Paso 1: Instalar la plataforma Base | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- platforms
- installing, base platform
- base platform
ms.assetid: 27da386f-90c7-414f-a4e3-e909f0c18371
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e0884ff97e9981129f63c9bc425e86dfeaafc9a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005149"
---
# <a name="step-1-installing-the-base-platform"></a><span data-ttu-id="c4480-102">Paso 1: Instalar la plataforma Base</span><span class="sxs-lookup"><span data-stu-id="c4480-102">Step 1: Installing the Base Platform</span></span>
<span data-ttu-id="c4480-103">Para la plataforma base, instalar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] y [!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] Service Pack 2 en cada servidor mediante las opciones de instalación predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="c4480-103">For the base platform, install [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] and [!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] Service Pack 2 on each server using the default installation options.</span></span> <span data-ttu-id="c4480-104">Siga estas recomendaciones:</span><span class="sxs-lookup"><span data-stu-id="c4480-104">Follow these recommendations:</span></span>  
  
## <a name="pre-installation"></a><span data-ttu-id="c4480-105">Antes de la instalación</span><span class="sxs-lookup"><span data-stu-id="c4480-105">Pre-Installation</span></span>  
  
-   <span data-ttu-id="c4480-106">Deshabilite todos los programas antivirus durante la instalación de software.</span><span class="sxs-lookup"><span data-stu-id="c4480-106">Disable all antivirus software during software installation.</span></span> <span data-ttu-id="c4480-107">Algunos programas de software antivirus pueden impedir que se instale correctamente los componentes de software necesarios.</span><span class="sxs-lookup"><span data-stu-id="c4480-107">Some antivirus software programs might prevent required software components from installing properly.</span></span>  
  
-   <span data-ttu-id="c4480-108">Asegúrese de que se escriba la información de licencia correspondiente (número máximo de conexiones que han comprado por servidor).</span><span class="sxs-lookup"><span data-stu-id="c4480-108">Make sure that you enter the appropriate licensing information (maximum number of connections you have purchased per server).</span></span> <span data-ttu-id="c4480-109">Rendimiento del sistema puede verse afectado por el número de conexiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="c4480-109">System performance can be affected by the number of available connections.</span></span>  
  
-   <span data-ttu-id="c4480-110">Asegúrese de que ha instalado todos los requisitos previos de software necesarios para una instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c4480-110">Make sure that you have installed all the software prerequisites required for a BizTalk Server installation.</span></span> <span data-ttu-id="c4480-111">Para obtener más información, consulte las instrucciones de instalación de BizTalk Server en [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span><span class="sxs-lookup"><span data-stu-id="c4480-111">For more information, see the BizTalk Server Installation Instructions at [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span></span> <span data-ttu-id="c4480-112">[Guía de instalación de BizTalk 2013 R2 Accelerator for SWIFT](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1).</span><span class="sxs-lookup"><span data-stu-id="c4480-112">[Installation Guide for BizTalk 2013 R2 Accelerator for SWIFT](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1).</span></span>  
  
-   <span data-ttu-id="c4480-113">Probar todas las actualizaciones críticas en un entorno sin conexión antes de instalarlos en los servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="c4480-113">Test all critical updates in an offline environment before installing them on your production servers.</span></span>  
  
-   <span data-ttu-id="c4480-114">Asegúrese de que instale todas las revisiones aplicables para todos los productos que se instalación como parte de la implementación.</span><span class="sxs-lookup"><span data-stu-id="c4480-114">Make sure that you install all the applicable hotfixes for all the products that you install as part of your deployment.</span></span> <span data-ttu-id="c4480-115">Para obtener más información, vea los siguientes orígenes:</span><span class="sxs-lookup"><span data-stu-id="c4480-115">For more information, see the following sources:</span></span>  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="c4480-116">Ayuda en pantalla de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c4480-116"> BizTalk Server Online Help</span></span>  
  
    -   <span data-ttu-id="c4480-117">Instrucciones de instalación de BizTalk Server en [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span><span class="sxs-lookup"><span data-stu-id="c4480-117">BizTalk Server Installation Instructions at [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span></span>  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="c4480-118">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Sitio Web en [http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685).</span><span class="sxs-lookup"><span data-stu-id="c4480-118"> [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Web site at [http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685).</span></span>  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="c4480-119">Sitio Web de centro de descarga en [http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686).</span><span class="sxs-lookup"><span data-stu-id="c4480-119"> Download Center Web site at [http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686).</span></span>  
  
    -   [!INCLUDE[btsWinUpdate](../../includes/btswinupdate-md.md)]<span data-ttu-id="c4480-120">Sitio Web en [http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687).</span><span class="sxs-lookup"><span data-stu-id="c4480-120"> Web site at [http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687).</span></span>  
  
-   <span data-ttu-id="c4480-121">Para evitar los ataques de virus, instale la plataforma desde un CD y desconecte todos los servidores de Internet, desenchufe los cables y deshabilitar a los adaptadores de red.</span><span class="sxs-lookup"><span data-stu-id="c4480-121">To avoid virus attacks, install the platform from a CD and disconnect each server from the Internet by unplugging any cables and disabling any network adapters.</span></span>  
  
-   <span data-ttu-id="c4480-122">Dar formato a una partición limpia mediante el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] sistema de archivos NTFS.</span><span class="sxs-lookup"><span data-stu-id="c4480-122">Format a clean partition using the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] NTFS file system.</span></span>  
  
## <a name="active-directory"></a><span data-ttu-id="c4480-123">Active Directory</span><span class="sxs-lookup"><span data-stu-id="c4480-123">Active Directory</span></span>  
  
-   <span data-ttu-id="c4480-124">Cree un usuario de dominio llamado **administración** y lo agrega a la variable local **administradores** grupo en todos los equipos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="c4480-124">Create a domain user called **Admin** and add it to the local **Administrators** group on every computer in your deployment.</span></span> <span data-ttu-id="c4480-125">Durante la instalación, inicie sesión en los servidores de implementación usa esta cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="c4480-125">At installation time, log on to the deployment servers using this domain account.</span></span>  
  
-   <span data-ttu-id="c4480-126">No configure los adaptadores de red o unirse a los dominios en este momento.</span><span class="sxs-lookup"><span data-stu-id="c4480-126">Do not configure any network adapters or join any domains at this time.</span></span> <span data-ttu-id="c4480-127">Esta guía describe cómo configurar estas opciones más adelante al comenzar el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="c4480-127">This guide describes how to configure these settings later when you begin the deployment process.</span></span>  
  
## <a name="internal-web-servers-mrsr-site"></a><span data-ttu-id="c4480-128">Servidores Web internos (sitio MRSR)</span><span class="sxs-lookup"><span data-stu-id="c4480-128">Internal Web Servers (MRSR site)</span></span>  
  
-   <span data-ttu-id="c4480-129">Asegúrese de que Internet Information Services (IIS) está instalado solo en lo servidores de sitio MRSR.</span><span class="sxs-lookup"><span data-stu-id="c4480-129">Make sure that Internet Information Services (IIS) is installed only on the MRSR site Servers.</span></span>  
  
-   <span data-ttu-id="c4480-130">Asegúrese de que Internet Information Services (IIS) no está instalado en el Internet Security and Acceleration (ISA) Server.</span><span class="sxs-lookup"><span data-stu-id="c4480-130">Make sure that Internet Information Services (IIS) is not installed on the Internet Security and Acceleration (ISA) Server.</span></span>  
  
-   <span data-ttu-id="c4480-131">Asegúrese de que el servicio de Message Queuing (MSMQ) está instalado solo en los servidores de sitio MRSR.</span><span class="sxs-lookup"><span data-stu-id="c4480-131">Make sure that the Message Queuing (MSMQ) service is installed only on the MRSR site Servers.</span></span> <span data-ttu-id="c4480-132">Si los servidores de mensajería de BizTalk también se utilizará como el sitio MRSR servidores, no instale MSMQ en esos servidores.</span><span class="sxs-lookup"><span data-stu-id="c4480-132">If the BizTalk Messaging servers will also be used as the MRSR site Servers, do not install MSMQ on those servers.</span></span>