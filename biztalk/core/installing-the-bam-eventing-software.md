---
title: Instalar el Software eventos BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3638d34-f5a8-4ffd-99eb-d38aed4c0732
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5c41606f6056dcc4edb90b4db5ef6a41901835b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-bam-eventing-software"></a><span data-ttu-id="93d76-102">Instalar el software de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="93d76-102">Installing the BAM-Eventing Software</span></span>
<span data-ttu-id="93d76-103">Para implementar soluciones de BAM mediante la API de eventos BAM o configurar la aplicación de Windows Workflow Foundation o Windows Communication Foundation para utilizar el interceptor de BAM para Windows Workflow Foundation, debe instalar el software eventos BAM mediante el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="93d76-103">To implement BAM solutions using the BAM eventing APIs or configure your Windows Workflow Foundation or Windows Communication Foundation application to use the BAM interceptor for Windows Workflow Foundation, you must install the BAM-Eventing software by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Setup program.</span></span> <span data-ttu-id="93d76-104">Este software puede instalarse como parte de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en tiempo de ejecución o por separado seleccionando compatibilidad de eventos de BAM en Software adicional en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] la instalación de aplicación.</span><span class="sxs-lookup"><span data-stu-id="93d76-104">This software can be installed as part of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime or separately by selecting BAM Eventing Support under Additional Software in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup application.</span></span>  
  
### <a name="to-install-the-bam-eventing-software"></a><span data-ttu-id="93d76-105">Para instalar el software de eventos BAM</span><span class="sxs-lookup"><span data-stu-id="93d76-105">To install the BAM-Eventing software</span></span>  
  
1.  <span data-ttu-id="93d76-106">Inicie sesión en el equipo que alojará la aplicación WF usando una cuenta con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="93d76-106">Log on to the computer that will host the WF application using an account that has Administrator privileges.</span></span>  
  
2.  <span data-ttu-id="93d76-107">Ejecutar el programa de instalación en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] CD de instalación.</span><span class="sxs-lookup"><span data-stu-id="93d76-107">Run the Setup program on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Installation CD.</span></span>  
  
3.  <span data-ttu-id="93d76-108">Borre todas las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="93d76-108">Clear all selected options.</span></span> <span data-ttu-id="93d76-109">Si no lleva a cabo este paso, es posible que instale software que no necesita.</span><span class="sxs-lookup"><span data-stu-id="93d76-109">If you do not perform this step, you may install software you do not need.</span></span>  
  
4.  <span data-ttu-id="93d76-110">Expanda **Software adicional**y, a continuación, seleccione la **eventos BAM** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="93d76-110">Expand **Additional Software**, and then select the **BAM-Eventing** check box.</span></span>  
  
5.  <span data-ttu-id="93d76-111">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93d76-111">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="93d76-112">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="93d76-112">Click **Install**.</span></span>  
  
7.  <span data-ttu-id="93d76-113">Una vez completado el procedimiento de instalación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="93d76-113">When the installation procedure is complete, click **OK**.</span></span>  
  
     <span data-ttu-id="93d76-114">Así habrá instalado el software de eventos BAM.</span><span class="sxs-lookup"><span data-stu-id="93d76-114">The BAM-Eventing software is now installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93d76-115">La instalación de la biblioteca de interceptores de BAM mediante este método no requiere la adquisición de licencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="93d76-115">Installing the BAM interceptor library using this method does not require the purchase of additional licenses.</span></span>  
  
 <span data-ttu-id="93d76-116">Si está interesado en supervisar los datos del contador de rendimiento de los interceptores de BAM, en primer lugar deberá registrarlos mediante InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="93d76-116">If you are interested in monitoring performance counter data for the BAM interceptors, you must first register them by using InstallUtil.exe.</span></span>  
  
### <a name="to-register-bam-interceptor-performance-counters-by-using-installutilexe"></a><span data-ttu-id="93d76-117">Para registrar los contadores de rendimiento del interceptor de BAM mediante InstallUtil.exe</span><span class="sxs-lookup"><span data-stu-id="93d76-117">To register BAM interceptor performance counters by using InstallUtil.exe</span></span>  
  
1.  <span data-ttu-id="93d76-118">Iniciar  **[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo** como administrador.</span><span class="sxs-lookup"><span data-stu-id="93d76-118">Start **[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt** as an administrator.</span></span>  
  
2.  <span data-ttu-id="93d76-119">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="93d76-119">At the command prompt, enter the following command:</span></span>  
  
     <span data-ttu-id="93d76-120">InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll</span><span class="sxs-lookup"><span data-stu-id="93d76-120">InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll</span></span>  
  
3.  <span data-ttu-id="93d76-121">Tipo de **Exit**, y, a continuación, presione ENTRAR para cerrar el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="93d76-121">Type **Exit**, and then press ENTER to close the command prompt.</span></span>  
  
     <span data-ttu-id="93d76-122">A partir de entonces estarán disponibles los contadores de rendimiento del interceptor de BAM.</span><span class="sxs-lookup"><span data-stu-id="93d76-122">The BAM interceptor performance counters are now available.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93d76-123">De manera predeterminada, sólo los administradores y algunas cuentas del sistema tienen permiso para registrar datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="93d76-123">By default, only Administrators and some system accounts have permission to log performance data.</span></span> <span data-ttu-id="93d76-124">Para habilitar el acceso a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], agregue la cuenta usada para ejecutar aplicaciones de flujo de trabajo al grupo usuarios del registro de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="93d76-124">To enable access on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], add the account used for running workflow applications to the Performance Log Users group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d76-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="93d76-125">See Also</span></span>  
 <span data-ttu-id="93d76-126">[Implementar soluciones de BAM](../core/implementing-bam-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="93d76-126">[Implementing BAM Solutions](../core/implementing-bam-solutions.md) </span></span>  
 [<span data-ttu-id="93d76-127">Información general sobre la instalación de BizTalk Server 2013 y 2013 R2</span><span class="sxs-lookup"><span data-stu-id="93d76-127">Installation Overview for BizTalk Server 2013 and 2013 R2</span></span>](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)