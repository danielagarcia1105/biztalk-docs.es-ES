---
title: Cómo instalar la utilidad de cliente de inicio de sesión único | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, client utility
- client utility [SSO]
- SSO, installing
ms.assetid: e14d257e-2fde-46af-b90c-5dbc0884536b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674ecc3857fe9e5b5cbef2914aec875f350d7de5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003965"
---
# <a name="how-to-install-the-sso-client-utility"></a><span data-ttu-id="1da79-102">Cómo instalar la utilidad de cliente SSO</span><span class="sxs-lookup"><span data-stu-id="1da79-102">How to Install the SSO Client Utility</span></span>
<span data-ttu-id="1da79-103">La utilidad de cliente de SSO independiente (basada en una interfaz de usuario y en una utilidad de línea de comandos) permite a los usuarios finales configurar sus asignaciones cliente en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="1da79-103">The stand-alone SSO client utility (command-line utility and user interface-based) allows end users to configure their client mappings in the SSO database.</span></span> <span data-ttu-id="1da79-104">Puede instalar la utilidad de cliente desde un archivo autoextraíble (SSOClientInstall.exe) instalado con la característica de administración de SSO.</span><span class="sxs-lookup"><span data-stu-id="1da79-104">You can install the client utility from a self-extracting file (SSOClientInstall.exe) which is installed with the SSO administration feature.</span></span> <span data-ttu-id="1da79-105">Los administradores también pueden hacer que el paquete del instalador esté disponible para los usuarios cliente al colocar una copia del paquete del instalador en un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="1da79-105">Administrators can also make the installer package available to client users by placing a copy of the installer package on a network share.</span></span>  
  
 <span data-ttu-id="1da79-106">Para instalar la utilidad de cliente de SSO, debe ejecutar uno de los siguientes sistemas operativos en el equipo cliente:</span><span class="sxs-lookup"><span data-stu-id="1da79-106">To install the SSO client utility, you must be running one of the following operating systems on the client computer:</span></span>  
  
- [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]  
  
- [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)]<span data-ttu-id="1da79-107"> o [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] (solo es necesario si usa la utilidad de cliente de SSO basada en la interfaz de usuario o aprovecha el componente de interoperabilidad administrado de SSO empresarial).</span><span class="sxs-lookup"><span data-stu-id="1da79-107"> or [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] (only necessary if you are using the UI-based SSO Client Utility or for leveraging the managed interoperability component of Enterprise SSO).</span></span>  
  
  <span data-ttu-id="1da79-108">Después de instalar la utilidad de cliente de SSO, puede iniciarla desde el **iniciar** menú haciendo **programas**, **Microsoft Enterprise Single Sign-On**y, a continuación, **Utilidad de cliente SSO**.</span><span class="sxs-lookup"><span data-stu-id="1da79-108">After installing the SSO Client Utility, you can launch it from the **Start** menu by clicking **Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Client Utility**.</span></span>  
  
### <a name="to-install-the-sso-client-utility"></a><span data-ttu-id="1da79-109">Para instalar la utilidad de cliente de SSO</span><span class="sxs-lookup"><span data-stu-id="1da79-109">To install the SSO client utility</span></span>  
  
1.  <span data-ttu-id="1da79-110">Haga doble clic en SSOClientInstall del paquete del instalador.</span><span class="sxs-lookup"><span data-stu-id="1da79-110">Double-click the installer package SSOClientInstall.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1da79-111">Pídale al administrador de inicio de sesión único empresarial que le indique la ubicación de este archivo en su empresa.</span><span class="sxs-lookup"><span data-stu-id="1da79-111">Ask your Enterprise Single Sign-On Administrator for the location of this file in your enterprise.</span></span>  
  
     <span data-ttu-id="1da79-112">El **WinZip Self-Extractor** programa aparece.</span><span class="sxs-lookup"><span data-stu-id="1da79-112">The **WinZip Self-Extractor** program appears.</span></span>  
  
2.  <span data-ttu-id="1da79-113">Seleccione la carpeta donde desee descomprimir los archivos y haga clic en **Unzip**.</span><span class="sxs-lookup"><span data-stu-id="1da79-113">Select the folder where you want to unzip the files, and click **Unzip**.</span></span>  
  
     <span data-ttu-id="1da79-114">Se recomienda descomprimir los archivos en una carpeta temporal.</span><span class="sxs-lookup"><span data-stu-id="1da79-114">It is recommended to unzip the files in a temporary folder.</span></span>  
  
     <span data-ttu-id="1da79-115">El **Enterprise Single Sign-On instalación del cliente** programa aparece.</span><span class="sxs-lookup"><span data-stu-id="1da79-115">The **Enterprise Single Sign-On Client Setup** program appears.</span></span>  
  
3.  <span data-ttu-id="1da79-116">En **la bienvenida al cliente Enterprise Single Sign-On** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1da79-116">On **the Welcome to the Enterprise Single Sign-On Client** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="1da79-117">En la página Contrato de licencia, haga clic en **acepto los términos de este contrato de licencia**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1da79-117">On the License Agreement page, click **I accept the terms of this license agreement**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="1da79-118">En el **información del usuario** página, escriba el nombre de usuario, el nombre de la organización y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1da79-118">On the **User Information** page, type your user name, organization name, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="1da79-119">En el **Iniciar instalación** página, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="1da79-119">On the **Start Installation** page, click **Install**.</span></span>  
  
7.  <span data-ttu-id="1da79-120">En el **finalización del Enterprise Single Sign-On cliente asistente** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1da79-120">On the **Completing the Enterprise Single Sign-On Client Wizard** page, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="1da79-121">Especifique el servidor de SSO mediante una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1da79-121">Specify the SSO server by doing either of the following:</span></span>  
  
    -   <span data-ttu-id="1da79-122">Abra el complemento MMC de administración de ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="1da79-122">Open the ENTSSO Administration MMC Snap-In.</span></span> <span data-ttu-id="1da79-123">El **Seleccionar servidor de SSO** aparecerá el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1da79-123">The **Select SSO Server** dialog will appear.</span></span> <span data-ttu-id="1da79-124">Escriba o busque el servidor de SSO con el que se desea efectuar la conexión al llevar a cabo las operaciones de administración.</span><span class="sxs-lookup"><span data-stu-id="1da79-124">Enter or browse to the SSO Server that you want to connect to when you perform administration operations.</span></span> <span data-ttu-id="1da79-125">Para especificar el servidor de SSO para todos los usuarios en el equipo, seleccione **establecer servidor de SSO para todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="1da79-125">To specify the SSO Server for all users on the machine, select **Set SSO Server for all users**.</span></span>  
  
         <span data-ttu-id="1da79-126">O BIEN</span><span class="sxs-lookup"><span data-stu-id="1da79-126">OR</span></span>  
  
    -   <span data-ttu-id="1da79-127">En un símbolo del sistema, escriba `ssomanage –server` para especificar el servidor de SSO que desee.</span><span class="sxs-lookup"><span data-stu-id="1da79-127">At a command prompt, type `ssomanage –server` to specify the SSO server desired.</span></span> <span data-ttu-id="1da79-128">También puede escribir `ssomanage -serverall` para especificar el servidor SSO que todos los usuarios de este equipo se conectará al realizar operaciones de administración.</span><span class="sxs-lookup"><span data-stu-id="1da79-128">You can also type `ssomanage -serverall` to specify the SSO server that all users of this computer will connect to when performing administration operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da79-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="1da79-129">See Also</span></span>  
 <span data-ttu-id="1da79-130">[Cómo instalar el componente de administración de SSO](../core/how-to-install-the-sso-administration-component.md) </span><span class="sxs-lookup"><span data-stu-id="1da79-130">[How to Install the SSO Administration Component](../core/how-to-install-the-sso-administration-component.md) </span></span>  
 <span data-ttu-id="1da79-131">[Configuración de SSO](../core/configuring-sso.md) </span><span class="sxs-lookup"><span data-stu-id="1da79-131">[Configuring SSO](../core/configuring-sso.md) </span></span>  
 [<span data-ttu-id="1da79-132">Instalación de SSO</span><span class="sxs-lookup"><span data-stu-id="1da79-132">Installing SSO</span></span>](../core/installing-sso.md)