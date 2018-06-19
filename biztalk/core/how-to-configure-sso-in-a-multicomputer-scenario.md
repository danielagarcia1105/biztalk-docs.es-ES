---
title: Cómo configurar SSO en un escenario de varios equipos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, SSO
- SSO database, clustering
- clustering, Master Secret server
- SSO, configuring
- configuring, Master Secret server
- Master Secret server, clustering
- clustering, SSO database
- Master Secret server, configuring
- SSO, multiple computers
ms.assetid: 4511a03d-96f2-45f0-9891-e8b3e253499c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45bfa58c1fc11a76109f56938b8e1b43790935f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248756"
---
# <a name="how-to-configure-sso-in-a-multicomputer-scenario"></a><span data-ttu-id="4fb95-102">Cómo configurar SSO en un escenario de varios equipos</span><span class="sxs-lookup"><span data-stu-id="4fb95-102">How to Configure SSO in a Multicomputer Scenario</span></span>
<span data-ttu-id="4fb95-103">Esta sección contiene instrucciones para configurar el inicio de sesión único (SSO) empresarial en un escenario de tres equipos.</span><span class="sxs-lookup"><span data-stu-id="4fb95-103">This section contains instructions for configuring Enterprise Single Sign-On (SSO) in a three-computer scenario.</span></span>  
  
 <span data-ttu-id="4fb95-104">En el caso siguiente, el equipo A es el servidor secreto principal, el equipo B es el servidor de inicio de sesión único y el equipo C contiene la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="4fb95-104">In the following scenario, computer A is the master secret server, computer B is the Single Sign-On server, and computer C holds the SSO database.</span></span> <span data-ttu-id="4fb95-105">El equipo B puede actuar como un servidor en tiempo de ejecución, como un servidor de administración (los subservicios administrativos de SSO utilizan este servidor para administrar la base de datos de SSO) o como un servidor de asignación (los subservicios administrativos y de cliente de SSO utilizan este servidor para administrar asignaciones).</span><span class="sxs-lookup"><span data-stu-id="4fb95-105">Computer B can act as a runtime server, as an administration server (administration sub services of SSO use this server for managing the SSO database), or as a mapping server (administration and client sub services of SSO use this server to manage mappings).</span></span>  
  
 <span data-ttu-id="4fb95-106">Si desea agregar más servidores de SSO a su entorno, siga los pasos para configurar el equipo B. Todos los servidores nuevos de SSO señalarán a la base de datos de SSO existente y no pueden ser el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="4fb95-106">If you want to add more SSO servers to your environment, follow the steps for configuring computer B. Any new SSO servers will point to the existing SSO database, and cannot be the master secret server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4fb95-107">Se recomienda configurar el servidor secreto principal en un equipo diferente del servidor de inicio de sesión único y de la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="4fb95-107">It is recommended that you configure the master secret server on a different computer from the Single Sign-On server and the SSO database.</span></span>  
  
### <a name="to-configure-the-master-secret-server-and-create-the-sso-database-on-computer-a"></a><span data-ttu-id="4fb95-108">Para configurar el servidor secreto principal y crear la base de datos de SSO en el equipo A</span><span class="sxs-lookup"><span data-stu-id="4fb95-108">To configure the master secret server and create the SSO database on Computer A</span></span>  
  
1.  <span data-ttu-id="4fb95-109">Lleve a cabo una instalación personalizada de BizTalk Server e instale únicamente el componente del servidor secreto principal de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="4fb95-109">Perform a custom installation of BizTalk Server, and install only the Enterprise Single Sign-On Master Secret Server component.</span></span>  
  
2.  <span data-ttu-id="4fb95-110">Ejecute el Asistente para configuración para configurar SSO en el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="4fb95-110">Run the Configuration Wizard to configure SSO on the master secret server.</span></span> <span data-ttu-id="4fb95-111">En el **pregunta** , seleccione la opción de **crear un nuevo sistema SSO**.</span><span class="sxs-lookup"><span data-stu-id="4fb95-111">On the **Configuration Questions** page, select the option to **Create a new SSO system**.</span></span>  
  
3.  <span data-ttu-id="4fb95-112">En el **las cuentas de Windows** página, especifique las credenciales de cuenta de servicio para el servicio SSO.</span><span class="sxs-lookup"><span data-stu-id="4fb95-112">On the **Windows Accounts** page, specify the service account credentials for the SSO service.</span></span> <span data-ttu-id="4fb95-113">Esta cuenta debe pertenecer a la cuenta de grupo de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="4fb95-113">This must be a member of the SSO Administrators group.</span></span>  
  
4.  <span data-ttu-id="4fb95-114">En el **las configuraciones de base de datos** página, especifique la ubicación de SQL Server (equipo C) y el nombre de la base de datos SSO (SSODB).</span><span class="sxs-lookup"><span data-stu-id="4fb95-114">On the **Database Configurations** page, specify the location of the SQL Server (computer C) and the name of the SSO database (SSODB).</span></span>  
  
5.  <span data-ttu-id="4fb95-115">Especifique las opciones para hacer una copia de seguridad del secreto principal.</span><span class="sxs-lookup"><span data-stu-id="4fb95-115">Specify the options to back up the Master Secret.</span></span>  
  
6.  <span data-ttu-id="4fb95-116">Complete la configuración.</span><span class="sxs-lookup"><span data-stu-id="4fb95-116">Complete the configuration.</span></span>  
  
### <a name="to-configure-the-sso-server-on-computer-b"></a><span data-ttu-id="4fb95-117">Para configurar el servidor de SSO en el equipo B</span><span class="sxs-lookup"><span data-stu-id="4fb95-117">To configure the SSO server on Computer B</span></span>  
  
1.  <span data-ttu-id="4fb95-118">Instale el inicio de sesión único empresarial en el equipo B.</span><span class="sxs-lookup"><span data-stu-id="4fb95-118">Install Enterprise Single Sign-On on Computer B.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4fb95-119">Puede ser un equipo de BizTalk Server o de Host Integration Server, un servidor Web o un servidor de SSO (componentes de tiempo de ejecución de SSO).</span><span class="sxs-lookup"><span data-stu-id="4fb95-119">This can be a BizTalk Server or Host Integration Server computer, a Web server, or an SSO-only server (SSO runtime components).</span></span>  
  
2.  <span data-ttu-id="4fb95-120">Ejecute el Asistente para configuración para configurar SSO.</span><span class="sxs-lookup"><span data-stu-id="4fb95-120">Run the Configuration Wizard to configure SSO.</span></span> <span data-ttu-id="4fb95-121">En el **pregunta** , seleccione la opción de **unir un sistema SSO existente**.</span><span class="sxs-lookup"><span data-stu-id="4fb95-121">On the **Configuration Questions** page, select the option to **Join an existing SSO system**.</span></span>  
  
3.  <span data-ttu-id="4fb95-122">En el **las cuentas de Windows** página, especifique las credenciales de cuenta de servicio para el servicio SSO.</span><span class="sxs-lookup"><span data-stu-id="4fb95-122">On the **Windows Accounts** page, specify the service account credentials for the SSO service.</span></span> <span data-ttu-id="4fb95-123">Esta cuenta debe pertenecer a la cuenta de grupo de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="4fb95-123">This must be a member of the SSO Administrators group.</span></span>  
  
4.  <span data-ttu-id="4fb95-124">En el **las configuraciones de base de datos** página, seleccione la ubicación de SQL Server (equipo C) y el nombre de la base de datos SSO (SSODB).</span><span class="sxs-lookup"><span data-stu-id="4fb95-124">On the **Database Configurations** page, point to the location of the SQL Server (computer C) and the name of the SSO database (SSODB).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fb95-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fb95-125">See Also</span></span>  
 <span data-ttu-id="4fb95-126">[Cómo agrupar el servidor secreto principal](../core/how-to-cluster-the-master-secret-server1.md) </span><span class="sxs-lookup"><span data-stu-id="4fb95-126">[How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md) </span></span>  
 [<span data-ttu-id="4fb95-127">Instalación de SSO</span><span class="sxs-lookup"><span data-stu-id="4fb95-127">Installing SSO</span></span>](../core/installing-sso.md)