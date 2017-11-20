---
title: "Cómo mostrar la información de la base de datos SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO], viewing SSO database
- SSO database, viewing
- viewing, SSO database
ms.assetid: 0ebadd2e-6ea5-460c-b0a8-f48589e6bf1c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1328e6066af0d19c68657728f8dc7777ba62f12d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-the-sso-database-information"></a><span data-ttu-id="7ff93-102">Cómo mostrar la información de la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="7ff93-102">How to Display the SSO Database Information</span></span>
<span data-ttu-id="7ff93-103">Es posible ver la información de la base de datos de SSO utilizando el Complemento MMC o la utilidad de línea de comandos (ssomanage).</span><span class="sxs-lookup"><span data-stu-id="7ff93-103">You can view SSO database information by using the MMC Snap-In or the command line (ssomanage) utility.</span></span>  
  
### <a name="to-display-the-sso-database-information-using-the-mmc-snap-in"></a><span data-ttu-id="7ff93-104">Para mostrar la información de la base de datos de SSO utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="7ff93-104">To display the SSO database information using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="7ff93-105">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="7ff93-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="7ff93-106">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="7ff93-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="7ff93-107">Haga clic en **System**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ff93-107">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="7ff93-108">Haga clic en las pestañas en el **propiedades del sistema** cuadro de diálogo para ver la información de la base de datos SSO.</span><span class="sxs-lookup"><span data-stu-id="7ff93-108">Click the tabs on the  **System Properties** dialog box to view SSO database information.</span></span>  
  
### <a name="to-display-the-sso-database-information-using-the-command-line"></a><span data-ttu-id="7ff93-109">Para mostrar la información de la base de datos de SSO utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="7ff93-109">To display the SSO database information using the command line</span></span>  
  
1.  <span data-ttu-id="7ff93-110">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="7ff93-110">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="7ff93-111">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="7ff93-111">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="7ff93-112">El directorio de instalación predeterminado es  **\<unidad >**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="7ff93-112">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="7ff93-113">Tipo de **ssomanage – displaydb**.</span><span class="sxs-lookup"><span data-stu-id="7ff93-113">Type **ssomanage –displaydb**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ff93-114">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="7ff93-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-display-the-sso-database-the-sso-server-is-connected-to-using-the-command-line"></a><span data-ttu-id="7ff93-115">Para mostrar la información de la base de datos de SSO, la conexión con el servidor de SSO se efectúa mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="7ff93-115">To display the SSO database the SSO Server is connected to using the command line</span></span>  
  
1.  <span data-ttu-id="7ff93-116">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="7ff93-116">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="7ff93-117">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="7ff93-117">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="7ff93-118">El directorio de instalación predeterminado es  **\<unidad >**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="7ff93-118">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="7ff93-119">Tipo de **ssomanage – showdb**.</span><span class="sxs-lookup"><span data-stu-id="7ff93-119">Type **ssomanage –showdb**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ff93-120">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="7ff93-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
 <span data-ttu-id="7ff93-121">En la siguiente tabla se describen los valores que estos procedimientos muestran.</span><span class="sxs-lookup"><span data-stu-id="7ff93-121">The following table describes the values displayed by these procedures.</span></span>  
  
|<span data-ttu-id="7ff93-122">Propiedad</span><span class="sxs-lookup"><span data-stu-id="7ff93-122">Property</span></span>|<span data-ttu-id="7ff93-123">Valor</span><span class="sxs-lookup"><span data-stu-id="7ff93-123">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="7ff93-124">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ff93-124">SQL Server</span></span>|<span data-ttu-id="7ff93-125">**\<Nombre de SQL Server >**</span><span class="sxs-lookup"><span data-stu-id="7ff93-125">**\<SQL Server name>**</span></span>|  
|<span data-ttu-id="7ff93-126">Single Sign-On base de datos</span><span class="sxs-lookup"><span data-stu-id="7ff93-126">Single Sign-On database</span></span>|<span data-ttu-id="7ff93-127">**\<Nombre de la base de datos de SQL Server >**</span><span class="sxs-lookup"><span data-stu-id="7ff93-127">**\<SQL Server database name>**</span></span>|  
|<span data-ttu-id="7ff93-128">Nombre del servidor secreto de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="7ff93-128">Single Sign-On Secret Server name</span></span>|<span data-ttu-id="7ff93-129">**\<Nombre del servidor de inicio de sesión único >**</span><span class="sxs-lookup"><span data-stu-id="7ff93-129">**\<Single Sign-On Server name>**</span></span>|  
|<span data-ttu-id="7ff93-130">Cuenta de administradores de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="7ff93-130">Single Sign-On Administrators account</span></span>|<span data-ttu-id="7ff93-131">Dominio\nombre de cuenta</span><span class="sxs-lookup"><span data-stu-id="7ff93-131">Domain\account name</span></span>|  
|<span data-ttu-id="7ff93-132">Cuenta de administradores afiliados de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="7ff93-132">Single Sign-On Affiliate Administrators account</span></span>|<span data-ttu-id="7ff93-133">Dominio\nombre de cuenta</span><span class="sxs-lookup"><span data-stu-id="7ff93-133">Domain\account name</span></span>|  
|<span data-ttu-id="7ff93-134">Tamaño de la tabla de auditoría para las aplicaciones eliminadas (número de entradas de auditoría)</span><span class="sxs-lookup"><span data-stu-id="7ff93-134">Size of audit table for deleted applications (number of audit entries)</span></span>|<span data-ttu-id="7ff93-135">1.000 (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="7ff93-135">1,000 (default)</span></span>|  
|<span data-ttu-id="7ff93-136">Tamaño de la tabla de auditoría para las asignaciones de usuario eliminadas (número de entradas de auditoría)</span><span class="sxs-lookup"><span data-stu-id="7ff93-136">Size of audit table for deleted user mappings (number of audit entries)</span></span>|<span data-ttu-id="7ff93-137">1.000 (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="7ff93-137">1,000 (default)</span></span>|  
|<span data-ttu-id="7ff93-138">Tamaño de la tabla de auditoría para búsquedas de credenciales externas (número de entradas de auditoría)</span><span class="sxs-lookup"><span data-stu-id="7ff93-138">Size of audit table for external credential lookups (number of audit entries)</span></span>|<span data-ttu-id="7ff93-139">1.000 (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="7ff93-139">1,000 (default)</span></span>|  
|<span data-ttu-id="7ff93-140">Tiempo de espera de vales (en minutos)</span><span class="sxs-lookup"><span data-stu-id="7ff93-140">Ticket timeout (in minutes)</span></span>|<span data-ttu-id="7ff93-141">2 (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="7ff93-141">2 (default)</span></span><br /><br /> <span data-ttu-id="7ff93-142">Este valor puede ser un entero comprendido entre 1 y 525.600</span><span class="sxs-lookup"><span data-stu-id="7ff93-142">This value can be an integer from1 through 525,600</span></span>|  
|<span data-ttu-id="7ff93-143">Tiempo de espera de caché de credenciales (en minutos)</span><span class="sxs-lookup"><span data-stu-id="7ff93-143">Credential cache timeout (in minutes)</span></span>|<span data-ttu-id="7ff93-144">60 (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="7ff93-144">60 (default)</span></span>|  
|<span data-ttu-id="7ff93-145">Estado de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="7ff93-145">Single Sign-On Status</span></span>|<span data-ttu-id="7ff93-146">Habilitado o deshabilitado</span><span class="sxs-lookup"><span data-stu-id="7ff93-146">Enabled/disabled</span></span>|  
|<span data-ttu-id="7ff93-147">Vales permitidos</span><span class="sxs-lookup"><span data-stu-id="7ff93-147">Tickets allowed</span></span>|<span data-ttu-id="7ff93-148">Sí o no (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="7ff93-148">Yes/no (default)</span></span>|  
|<span data-ttu-id="7ff93-149">Validar vales</span><span class="sxs-lookup"><span data-stu-id="7ff93-149">Validate tickets</span></span>|<span data-ttu-id="7ff93-150">Sí (predeterminado) o no</span><span class="sxs-lookup"><span data-stu-id="7ff93-150">Yes (default)/no</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ff93-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ff93-151">See Also</span></span>  
 <span data-ttu-id="7ff93-152">[Cómo configurar los vales de SSO](../core/how-to-configure-the-sso-tickets.md) </span><span class="sxs-lookup"><span data-stu-id="7ff93-152">[How to Configure the SSO Tickets](../core/how-to-configure-the-sso-tickets.md) </span></span>  
 [<span data-ttu-id="7ff93-153">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="7ff93-153">Using SSO</span></span>](../core/using-sso.md)