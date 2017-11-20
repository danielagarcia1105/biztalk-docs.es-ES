---
title: "Instalar el componente de administración de SSO | Documentos de Microsoft"
description: "Realice una instalación personalizada para obtener la administración de SSO y use ssomanage o administración de SSO para especificar el nombre del servidor de BizTalk Server"
ms.custom: 
ms.date: 09/27/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 096839e2-7129-498d-92ee-5afeea8dbe0d
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab2bb01defe700408a551a144eae67d0405565f4
ms.sourcegitcommit: 5355a25d120d094778fb8f68ea14cab55c68d292
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2017
---
# <a name="how-to-install-the-sso-administration-component"></a><span data-ttu-id="43dc4-103">Cómo instalar el componente de administración de SSO</span><span class="sxs-lookup"><span data-stu-id="43dc4-103">How to Install the SSO Administration Component</span></span>

## <a name="overview"></a><span data-ttu-id="43dc4-104">Información general</span><span class="sxs-lookup"><span data-stu-id="43dc4-104">Overview</span></span>
<span data-ttu-id="43dc4-105">Puede instalar el componente de administración de inicio de sesión único de empresa como una característica independiente.</span><span class="sxs-lookup"><span data-stu-id="43dc4-105">You can install the Enterprise Single Sign-On Administration component as a stand-alone feature.</span></span> <span data-ttu-id="43dc4-106">Esto resulta de utilidad si se necesita administrar el sistema SSO de forma remota.</span><span class="sxs-lookup"><span data-stu-id="43dc4-106">This is useful if you need to administer the SSO system remotely.</span></span> <span data-ttu-id="43dc4-107">Los requisitos de hardware y software son los mismos que los de una instalación típica de los servicios de tiempo de ejecución de SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="43dc4-107">The hardware and software requirements are the same as for a typical Enterprise SSO Runtime Services installation.</span></span>  
  
 <span data-ttu-id="43dc4-108">Después de instalar el componente de administración, especifique el servidor de SSO que se usará para administración.</span><span class="sxs-lookup"><span data-stu-id="43dc4-108">After installing the administration component, you enter the SSO Server to be used for management.</span></span> <span data-ttu-id="43dc4-109">Puede hacerlo con la herramienta de línea de comandos (ssomanage.exe), o el complemento de MMC de administración de SSO.</span><span class="sxs-lookup"><span data-stu-id="43dc4-109">You can do this with either the command line tool (ssomanage.exe), or the SSO Administration MMC Snap-In.</span></span> <span data-ttu-id="43dc4-110">Ambos procedimientos se muestran en este tema.</span><span class="sxs-lookup"><span data-stu-id="43dc4-110">Both procedures are listed in this topic.</span></span>  
  
 <span data-ttu-id="43dc4-111">Con la instalación de la utilidad administrativa de SSO (ssomanage.exe), no se crean accesos directos en el menú Inicio para obtener acceso a las utilidades de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="43dc4-111">Installing the SSO administrative utility (ssomanage.exe) does not create shortcuts on the Start menu to access the command line utilities.</span></span> <span data-ttu-id="43dc4-112">Para ejecutar las utilidades administrativas de SSO después de la instalación, debe abrir un símbolo del sistema y navegue hasta el directorio SSO en `Program Files\Common Files\Enterprise Single Sign-On`.</span><span class="sxs-lookup"><span data-stu-id="43dc4-112">To run the SSO administrative utilities after installation, you must open a command prompt, and navigate to the SSO directory at `Program Files\Common Files\Enterprise Single Sign-On`.</span></span>  
  
 <span data-ttu-id="43dc4-113">La característica de administración de SSO empresarial también incluye un complemento de MMC.</span><span class="sxs-lookup"><span data-stu-id="43dc4-113">The Enterprise SSO Administration feature also includes an MMC Snap-in.</span></span> <span data-ttu-id="43dc4-114">MMC 3.0 debe instalarse en el equipo para el complemento de función.</span><span class="sxs-lookup"><span data-stu-id="43dc4-114">MMC 3.0 must be installed on your computer for the Snap-in to function.</span></span>  
  
 <span data-ttu-id="43dc4-115">Para abrir el complemento de MMC de SSO empresarial de la **iniciar** menú, seleccione **todos los programas**, seleccione **Microsoft Enterprise Single Sign-On**y, a continuación, **SSO Administración**.</span><span class="sxs-lookup"><span data-stu-id="43dc4-115">To open the Enterprise SSO MMC Snap-in from the **Start** menu, select **All Programs**, select **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
## <a name="install-the-enterprise-single-sign-on-administrative-component"></a><span data-ttu-id="43dc4-116">Instalar el componente administrativo de Enterprise Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="43dc4-116">Install the Enterprise Single Sign-On administrative component</span></span>  
  
-   <span data-ttu-id="43dc4-117">Realizar una instalación personalizada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y seleccione únicamente la característica de administración de inicio de sesión único de empresa.</span><span class="sxs-lookup"><span data-stu-id="43dc4-117">Do a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and select only the Enterprise Single Sign-On Administration feature.</span></span> <span data-ttu-id="43dc4-118">Para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], este aparece en **Software adicional**.</span><span class="sxs-lookup"><span data-stu-id="43dc4-118">For [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], this is listed under **Additional Software**.</span></span>  
  
## <a name="enter-the-server-using-the-mmc-snap-in"></a><span data-ttu-id="43dc4-119">Especifique el servidor mediante el complemento de MMC</span><span class="sxs-lookup"><span data-stu-id="43dc4-119">Enter the server using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="43dc4-120">Tras instalar el componente administrativo en un equipo en el que no se encuentre instalado aún, abra el complemento de administración de SSO.</span><span class="sxs-lookup"><span data-stu-id="43dc4-120">After installing the administrative component on a computer where it is not currently installed, open the SSO Administration Snap-In.</span></span>  
  
     <span data-ttu-id="43dc4-121">En el **iniciar** menú, seleccione **todos los programas**, seleccione **Microsoft Enterprise Single Sign-On**y, a continuación, seleccione **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="43dc4-121">In the **Start** menu, select **All Programs**, select **Microsoft Enterprise Single Sign-On**, and then select **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="43dc4-122">En el complemento MMC en el **raíz de consola**, haga clic en **Enterprise Single Sign-On**y haga clic en **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="43dc4-122">In the MMC Snap-In under the **Console Root**, right-click **Enterprise Single Sign-On**, and click **Select**.</span></span>  
  
     <span data-ttu-id="43dc4-123">El **Seleccionar servidor de SSO** aparecerá el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="43dc4-123">The **Select SSO Server** dialog box will appear.</span></span>  
  
3.  <span data-ttu-id="43dc4-124">Especifique el nombre del servidor de SSO o desplácese hasta el que desee.</span><span class="sxs-lookup"><span data-stu-id="43dc4-124">Enter or browse to the SSO server name you want to specify.</span></span> <span data-ttu-id="43dc4-125">Para especificar el servidor de SSO para todos los usuarios en el equipo, seleccione **establecer servidor de SSO para todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="43dc4-125">To specify the SSO server for all users on the computer, select **Set SSO Server for all users**.</span></span>  
  
4.  <span data-ttu-id="43dc4-126">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="43dc4-126">Click **OK**.</span></span>  
  
## <a name="enter-the-server-using-the-command-line-tool"></a><span data-ttu-id="43dc4-127">Especifique el servidor mediante la herramienta de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="43dc4-127">Enter the server using the command line tool</span></span>  
  
1.  <span data-ttu-id="43dc4-128">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="43dc4-128">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="43dc4-129">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="43dc4-129">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="43dc4-130">El directorio de instalación predeterminado es `\Program Files\Common Files\Enterprise Single Sign-On`.</span><span class="sxs-lookup"><span data-stu-id="43dc4-130">The default installation directory is `\Program Files\Common Files\Enterprise Single Sign-On`.</span></span>  
  
3.  <span data-ttu-id="43dc4-131">Especifique el servidor de SSO seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="43dc4-131">Enter the SSO Server by selecting one of the following options:</span></span>  
  
    1.  <span data-ttu-id="43dc4-132">Tipo de **ssomanage – server** para especificar el servidor de SSO al que desea conectarse a cuando se realizan operaciones de administración.</span><span class="sxs-lookup"><span data-stu-id="43dc4-132">Type **ssomanage –server** to enter the SSO Server you want to connect to when performing administration operations.</span></span>  
  
         <span data-ttu-id="43dc4-133">\- O BIEN</span><span class="sxs-lookup"><span data-stu-id="43dc4-133">\- OR -</span></span>  
  
    2.  <span data-ttu-id="43dc4-134">Tipo de **ssomanage - serverall** para especificar el servidor de SSO todos los usuarios de este equipo se conectará al realizar operaciones de administración.</span><span class="sxs-lookup"><span data-stu-id="43dc4-134">Type **ssomanage -serverall** to enter the SSO Server all users of this computer will connect to when performing administration operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43dc4-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="43dc4-135">See Also</span></span>  
 <span data-ttu-id="43dc4-136">[Cómo instalar la utilidad de cliente SSO](../core/how-to-install-the-sso-client-utility.md) </span><span class="sxs-lookup"><span data-stu-id="43dc4-136">[How to Install the SSO Client Utility](../core/how-to-install-the-sso-client-utility.md) </span></span>  
 <span data-ttu-id="43dc4-137">[Configuración de SSO](../core/configuring-sso.md) </span><span class="sxs-lookup"><span data-stu-id="43dc4-137">[Configuring SSO](../core/configuring-sso.md) </span></span>  
 [<span data-ttu-id="43dc4-138">Instalación de SSO</span><span class="sxs-lookup"><span data-stu-id="43dc4-138">Installing SSO</span></span>](../core/installing-sso.md)
