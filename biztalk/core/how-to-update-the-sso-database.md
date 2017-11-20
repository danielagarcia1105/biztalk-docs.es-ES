---
title: "Cómo actualizar la base de datos SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tickets [SSO], modifying
- managing [SSO], modifying Credential cache timeout
- tickets [SSO], timeouts
- modifying, SSO database
- managing [SSO], modifying ticket timeouts
- SSO database, modifying
ms.assetid: 45eb6a77-d91a-44a8-b26d-05508c288c36
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1381ee4e5c2b90a96c52b59d125ec3121af02a4e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-sso-database"></a><span data-ttu-id="65770-102">Cómo actualizar la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="65770-102">How to Update the SSO Database</span></span>
<span data-ttu-id="65770-103">Puede cambiar la información global de la base de datos de SSO (por ejemplo, identificación del servidor secreto principal, nombres de cuenta, auditoría de la base de datos, tiempo de espera de vales y tiempo de espera de almacenamiento de credenciales en caché) utilizando el Complemento MMC o la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="65770-103">You can change the global information in the SSO database, such as the master secret server identification, the account names, auditing in the database, ticket timeout, and credential cache timeout, by using either the MMC Snap-In or the command line.</span></span>  
  
## <a name="changing-timeouts-for-the-sso-system"></a><span data-ttu-id="65770-104">Cambiar los tiempos de espera del sistema de SSO</span><span class="sxs-lookup"><span data-stu-id="65770-104">Changing timeouts for the SSO System</span></span>  
 <span data-ttu-id="65770-105">Puede modificar dos tiempos de espera en el nivel del sistema de inicio de sesión único (SSO) empresarial:</span><span class="sxs-lookup"><span data-stu-id="65770-105">You can modify two timeouts at the Enterprise Single Sign-On (SSO) system level:</span></span>  
  
 <span data-ttu-id="65770-106">**Tiempo de espera de vale.**</span><span class="sxs-lookup"><span data-stu-id="65770-106">**Ticket timeout.**</span></span> <span data-ttu-id="65770-107">esta propiedad especifica el período de validez de un vale emitido por SSO.</span><span class="sxs-lookup"><span data-stu-id="65770-107">This property specifies the length of time for which a ticket SSO issues is valid.</span></span> <span data-ttu-id="65770-108">Para adaptarse a la mayoría de los escenarios de una empresa que utilice SSO, el tiempo de espera predeterminado del vale es de 2 minutos.</span><span class="sxs-lookup"><span data-stu-id="65770-108">To satisfy most of the scenarios in an enterprise that use SSO, the default ticket timeout is 2 minutes.</span></span> <span data-ttu-id="65770-109">El administrador de SSO puede cambiar este valor en función de los requisitos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="65770-109">The SSO administrator can change this based on the application requirements.</span></span>  
  
 <span data-ttu-id="65770-110">**Tiempo de espera de caché de credenciales.**</span><span class="sxs-lookup"><span data-stu-id="65770-110">**Credential Cache timeout.**</span></span> <span data-ttu-id="65770-111">Esta propiedad especifica el tiempo de espera de almacenamiento en caché de credenciales para todos los servidores de SSO.</span><span class="sxs-lookup"><span data-stu-id="65770-111">This property specifies the credential cache timeout for all SSO Servers.</span></span> <span data-ttu-id="65770-112">Los servidores de SSO almacenan en caché las credenciales después de la primera búsqueda.</span><span class="sxs-lookup"><span data-stu-id="65770-112">SSO Servers cache the credentials after the first lookup.</span></span> <span data-ttu-id="65770-113">De forma predeterminada, el tiempo de espera de almacenamiento en caché de las credenciales es de 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="65770-113">By default, the credential cache timeout is 60 minutes.</span></span> <span data-ttu-id="65770-114">El administrador de SSO puede cambiar este valor por otro más apropiado según los requisitos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="65770-114">The SSO administrator can change this to a suitable value based on the security requirements.</span></span>  
  
 <span data-ttu-id="65770-115">Ambos tiempos de espera pueden cambiarse actualizando la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="65770-115">You change both of these timeouts by updating the SSO database.</span></span>  
  
 <span data-ttu-id="65770-116">Un ejemplo de archivo XML para actualizar la base de datos de SSO es:</span><span class="sxs-lookup"><span data-stu-id="65770-116">A sample XML file for updating the SSO database is:</span></span>  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
<secretServer>ComputerA</secretServer>  
<auditDeletedApps>1000</auditDeletedApps>  
<auditDeletedMappings>1000</auditDeletedMappings>  
<auditCredentialLookups>1000</auditCredentialLookups>  
<ticketTimeout>2</ticketTimeout>  
<credCacheTimeout>60</credCacheTimeout>  
</globalInfo>  
</sso>  
  
```  
  
#### <a name="to-change-timeouts-using-the-mmc-snap-in"></a><span data-ttu-id="65770-117">Para cambiar los tiempo de espera utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="65770-117">To change timeouts using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="65770-118">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="65770-118">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="65770-119">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="65770-119">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="65770-120">Haga clic en **System**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="65770-120">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="65770-121">En el **propiedades del sistema** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="65770-121">On the **System Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="65770-122">Especifique la configuración adecuada y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="65770-122">Enter the appropriate settings, and click **OK**.</span></span>  
  
#### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a><span data-ttu-id="65770-123">Para actualizar la base de datos de SSO utilizando el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="65770-123">To update the SSO database using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="65770-124">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="65770-124">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="65770-125">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="65770-125">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="65770-126">Haga clic en **System**y, a continuación, haga clic en **Actualizar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="65770-126">Right-click **System**, and then click **Upgrade Database**.</span></span>  
  
#### <a name="to-update-the-sso-database-using-the-command-line"></a><span data-ttu-id="65770-127">Para actualizar la base de datos de SSO utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="65770-127">To update the SSO database using the command line</span></span>  
  
1.  <span data-ttu-id="65770-128">Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="65770-128">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="65770-129">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="65770-129">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="65770-130">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="65770-130">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="65770-131">Tipo de **ssomanage-updatedb \<archivo de actualización >**, donde  **\<archivo de actualización >** es la ruta de acceso y nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="65770-131">Type **ssomanage –updatedb \<update file>**, where **\<update file>** is the path and name of the file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65770-132">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="65770-132">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65770-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="65770-133">See Also</span></span>  
 <span data-ttu-id="65770-134">[Cómo configurar los vales de SSO](../core/how-to-configure-the-sso-tickets.md) </span><span class="sxs-lookup"><span data-stu-id="65770-134">[How to Configure the SSO Tickets](../core/how-to-configure-the-sso-tickets.md) </span></span>  
 [<span data-ttu-id="65770-135">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="65770-135">Using SSO</span></span>](../core/using-sso.md)