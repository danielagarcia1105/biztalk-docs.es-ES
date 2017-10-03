---
title: "Cómo configurar MIIS para ENTSSO MA | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7820384-ff64-4628-9e35-02b13803928f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 969a52beb02c3d2ba237369c16efec9ee84e2ef1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-miis-for-entsso-ma"></a><span data-ttu-id="b117b-102">Cómo configurar MIIS para el agente de administración de ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b117b-102">How to Configure MIIS for ENTSSO MA</span></span>
<span data-ttu-id="b117b-103">Al instalar la característica de administración de inicio de sesión único (SSO) empresarial (ya sea la versión completa o la de administración) en un equipo que ejecute Microsoft Identity Integration Server (MIIS), el agente de administración de ENTSSO se instala de forma automática.</span><span class="sxs-lookup"><span data-stu-id="b117b-103">When you install the Enterprise Single Sign-On (SSO) Administration feature (either the full version or the Admin-only version) on a computer running Microsoft Identity Integration Server (MIIS), the ENTSSO Management Agent is automatically installed.</span></span> <span data-ttu-id="b117b-104">Esto implica que, al abrir MIIS, ya se han establecido casi todos los parámetros de configuración.</span><span class="sxs-lookup"><span data-stu-id="b117b-104">This means that when you open MIIS, nearly all of the configuration has already been done.</span></span> <span data-ttu-id="b117b-105">La única parte que falta es la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="b117b-105">The only part missing is the connection information.</span></span>  
  
 <span data-ttu-id="b117b-106">Antes de comenzar el procedimiento, asegúrese de que la siguiente información está disponible:</span><span class="sxs-lookup"><span data-stu-id="b117b-106">Before starting this procedure, make sure you have the following information available:</span></span>  
  
-   <span data-ttu-id="b117b-107">Nombre del servidor de ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="b117b-107">ENTSSO Server name.</span></span>  
  
-   <span data-ttu-id="b117b-108">El Id. de usuario y la contraseña de la cuenta de Windows que utilizará el agente de administración de ENTSSO para comunicarse con el servidor de SSO.</span><span class="sxs-lookup"><span data-stu-id="b117b-108">UserId and password of the Windows account under which the ENTSSO Management Agent will communicate with the SSO Server.</span></span>  
  
### <a name="to-configure-the-management-agent-within-miis"></a><span data-ttu-id="b117b-109">Para configurar el agente de administración en MIIS</span><span class="sxs-lookup"><span data-stu-id="b117b-109">To configure the Management Agent within MIIS</span></span>  
  
1.  <span data-ttu-id="b117b-110">Abra MIIS y el **Identity Manager**.</span><span class="sxs-lookup"><span data-stu-id="b117b-110">Open MIIS, and open the **Identity Manager**.</span></span>  
  
2.  <span data-ttu-id="b117b-111">Abra la **crear agente de administración** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b117b-111">Open the **Create Management Agent** dialog box.</span></span>  
  
3.  <span data-ttu-id="b117b-112">Seleccione **Enterprise Single Sign-On** en la lista.</span><span class="sxs-lookup"><span data-stu-id="b117b-112">Select **Enterprise Single Sign-On** in the list.</span></span>  
  
     <span data-ttu-id="b117b-113">Esto inicia el **Asistente para crear un agente de administración**.</span><span class="sxs-lookup"><span data-stu-id="b117b-113">This starts the **Create Management Agent Wizard**.</span></span>  
  
4.  <span data-ttu-id="b117b-114">En el **configurar la información de conexión** página, en la **Connect To:** , escriba el nombre del servidor de SSO.</span><span class="sxs-lookup"><span data-stu-id="b117b-114">On the **Configure Connection Information** page, in the **Connect To:** field, enter the name of the SSO Server.</span></span>  
  
5.  <span data-ttu-id="b117b-115">Escriba el nombre del agente de administración de ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="b117b-115">Enter the name of the ENTSSO Management Agent.</span></span> <span data-ttu-id="b117b-116">Debe coincidir con el nombre especificado en el archivo ENTSSO.xml.</span><span class="sxs-lookup"><span data-stu-id="b117b-116">This name must match the name specified in your ENTSSO.xml file.</span></span>  
  
6.  <span data-ttu-id="b117b-117">En el **usuario** campo, especifique la cuenta de dominio que utiliza el agente de administración de ENTSSO para administrar las asignaciones en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="b117b-117">In the **User** field, specify the domain account that the ENTSSO Management Agent uses to manage mappings in the SSO Database.</span></span>  
  
     <span data-ttu-id="b117b-118">La cuenta debe ser miembro de las cuentas de administradores de SSO o de las de administradores afiliados de SSO en el sistema de inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="b117b-118">This account should be either a member of the SSO Affiliate Administrators or SSO Administrators accounts within the SSO System.</span></span>  
  
7.  <span data-ttu-id="b117b-119">En el **contraseña** , escriba la contraseña para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="b117b-119">In the **Password** field, enter the password for that user.</span></span>  
  
8.  <span data-ttu-id="b117b-120">Haga clic en **siguiente**, acepte los valores predeterminados hasta llegar a la **configurar extensiones** página.</span><span class="sxs-lookup"><span data-stu-id="b117b-120">Click **Next**, accepting the defaults until you reach the **Configure Extensions** page.</span></span>  
  
9. <span data-ttu-id="b117b-121">Cerca de **información de conexión** para la extensión de contraseña, haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="b117b-121">Near **Connection information** for password extension, click **Settings**.</span></span>  
  
     <span data-ttu-id="b117b-122">El **configuración de conexión** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b117b-122">The **Connection Settings** dialog box appears.</span></span>  
  
10. <span data-ttu-id="b117b-123">En el **Connect To** cuadro, escriba la cuenta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b117b-123">In the **Connect To** box, enter the appropriate account.</span></span> <span data-ttu-id="b117b-124">Esta cuenta debe coincidir con la cuenta de servicio del servicio de ENTSSO que se ejecuta en el equipo especificado.</span><span class="sxs-lookup"><span data-stu-id="b117b-124">This account must be the same as the service account for the ENTSSO service running on the computer specified.</span></span>  
  
11. <span data-ttu-id="b117b-125">En el **usuario** y **contraseña** campos, escriba el nombre de usuario y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="b117b-125">In the **User** and **Password** fields, enter the user name and password for the account.</span></span>  
  
12. <span data-ttu-id="b117b-126">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b117b-126">Click **OK**.</span></span>  
  
13. <span data-ttu-id="b117b-127">En el **MIISCreate Management Agent**, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b117b-127">In the **MIISCreate Management Agent**, click **Finish**.</span></span>  
  
14. <span data-ttu-id="b117b-128">Mientras sigue en la **Identity Manager**, haga clic en el **herramientas** menú y, a continuación, haga clic en **opciones**.</span><span class="sxs-lookup"><span data-stu-id="b117b-128">While still in the **Identity Manager**, click the **Tools** menu, and then click **Options**.</span></span>  
  
     <span data-ttu-id="b117b-129">El **opciones** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b117b-129">The **Options** dialog box appears.</span></span>  
  
15. <span data-ttu-id="b117b-130">Seleccione **habilitar la extensión de las reglas del metaverso**.</span><span class="sxs-lookup"><span data-stu-id="b117b-130">Select **Enable metaverse rules extension**.</span></span>  
  
16. <span data-ttu-id="b117b-131">En el **campo de nombre de extensión de reglas**, escriba **Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**.</span><span class="sxs-lookup"><span data-stu-id="b117b-131">In the **Rules extension name field**, enter **Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**.</span></span>  
  
17. <span data-ttu-id="b117b-132">Haga clic en **Aceptar** y cierre MIIS.</span><span class="sxs-lookup"><span data-stu-id="b117b-132">Click **OK** and close MIIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b117b-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b117b-133">See Also</span></span>  
 [<span data-ttu-id="b117b-134">Cómo usar al agente de administración de ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b117b-134">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)