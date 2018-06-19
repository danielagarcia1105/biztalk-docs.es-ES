---
title: Cómo actualizar las propiedades de una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], updating properties
- applications [SSO], properties
ms.assetid: b06eefdd-a5ca-4a32-93d7-72246e31a2e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ef4a2fb99d423f7c7ccb08cec58c3c49928e1ed
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972650"
---
# <a name="how-to-update-the-properties-of-an-affiliate-application"></a><span data-ttu-id="693d6-102">Cómo actualizar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="693d6-102">How to Update the Properties of an Affiliate Application</span></span>
<span data-ttu-id="693d6-103">Puede utilizar el Complemento MMC o este comando para actualizar una o más propiedades de aplicaciones, como especificó el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="693d6-103">You can use the MMC Snap-In or this command to update one or more application properties, as specified by the XML file.</span></span> <span data-ttu-id="693d6-104">Deberá ser administrador afiliado para realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="693d6-104">You must be an Affiliate Administrator to perform this task.</span></span> <span data-ttu-id="693d6-105">A continuación se muestra un ejemplo de archivo XML que enumera los campos que puede actualizar.</span><span class="sxs-lookup"><span data-stu-id="693d6-105">The following is an example XML file that lists the fields you can update.</span></span>  
  
```  
<SSO>  
<application name="SSOApplication">  
<description>An SSO Application</description>  
<contact>someone@companyname.com</contact>  
<appUserAccount>DomainName\AppUserGroup</appUserAccount>  
<appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
<flags allowTickets="no" validateTickets="yes"  timeoutTickets="yes" enableApp="no" />  
</application>  
</SSO>  
  
```  
  
 <span data-ttu-id="693d6-106">Tras crear una aplicación afiliada, no podrá modificar las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="693d6-106">After you create an affiliate application, you cannot modify the following properties:</span></span>  
  
-   <span data-ttu-id="693d6-107">Nombre de la aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="693d6-107">Name of the affiliate application</span></span>  
  
-   <span data-ttu-id="693d6-108">Campos asociados con la aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="693d6-108">Fields associated with the affiliate application</span></span>  
  
-   <span data-ttu-id="693d6-109">Tipo de aplicación afiliada (grupo de host, individual o almacén de configuración)</span><span class="sxs-lookup"><span data-stu-id="693d6-109">Affiliate application type (host group, individual, or configuration store)</span></span>  
  
-   <span data-ttu-id="693d6-110">Cuenta de administración igual al grupo de administradores afiliados.</span><span class="sxs-lookup"><span data-stu-id="693d6-110">Administration account same as affiliate administrators group.</span></span> <span data-ttu-id="693d6-111">(Si especifica esta marca, se utilizará siempre el grupo de administradores afiliados como la cuenta de administrador para la aplicación afiliada)</span><span class="sxs-lookup"><span data-stu-id="693d6-111">(Specifying this flag will always use the affiliate administrators group as the administrator account for this affiliate application)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="693d6-112">Puede utilizar cuentas locales para la cuenta de administración y de usuario al establecer en Sí la marca allowLocalAccounts.</span><span class="sxs-lookup"><span data-stu-id="693d6-112">You can use local accounts for the administration account and user account by setting the allowLocalAccounts flag to yes.</span></span> <span data-ttu-id="693d6-113">Sin embargo, esta marca se puede utilizar sólo en escenarios de un único equipo.</span><span class="sxs-lookup"><span data-stu-id="693d6-113">However, you can only use this flag in single-computer scenarios.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="693d6-114">Para llevar a cabo esta tarea deberá ser administrador de SSO, administrador de aplicaciones o administrador afiliado de SSO.</span><span class="sxs-lookup"><span data-stu-id="693d6-114">You must be an SSO administrator, SSO affiliate administrator, or application administrator to perform this task.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="693d6-115">Debe ser un administrador de SSO para modificar las marcas de compras de vales (validateTickets y timeoutTickets).</span><span class="sxs-lookup"><span data-stu-id="693d6-115">You must be an SSO administrator to modify the ticketing flags (validateTickets and timeoutTickets).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="693d6-116">Debe ser un administrador de SSO o administrador afiliado de SSO para modificar la cuenta de administración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="693d6-116">You must be an SSO administrator or an SSO affiliate administrator to modify the application administration account.</span></span>  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="693d6-117">Para actualizar las propiedades de una aplicación afiliada con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="693d6-117">To update the properties of an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="693d6-118">En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="693d6-118">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="693d6-119">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="693d6-119">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="693d6-120">Haga clic en la aplicación afiliada y, a continuación, haga clic en **actualización**.</span><span class="sxs-lookup"><span data-stu-id="693d6-120">Right-click the affililate application, and then click **Update**.</span></span>  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="693d6-121">Para actualizar las propiedades de una aplicación afiliada con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="693d6-121">To update the properties of an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="693d6-122">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="693d6-122">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="693d6-123">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="693d6-123">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="693d6-124">El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="693d6-124">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="693d6-125">Tipo de **ssomanage – updateapps \<nombre de archivo de aplicación\>**, donde el nombre de archivo de aplicación es el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="693d6-125">Type **ssomanage –updateapps \<application file name\>**, where the application file name is the XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="693d6-126">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="693d6-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="693d6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="693d6-127">See Also</span></span>  
 <span data-ttu-id="693d6-128">[Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="693d6-128">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="693d6-129">[Cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="693d6-129">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="693d6-130">[Administrar asignaciones de usuario](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="693d6-130">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="693d6-131">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="693d6-131">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)