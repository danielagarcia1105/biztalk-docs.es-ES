---
title: "Cómo crear una aplicación afiliada | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], creating
- applications [SSO], creating
- creating, applications [SSO]
ms.assetid: d0967c4b-6201-416a-9d3a-23b5de5b83d6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d36fa977c7da90c3f894dd1153799008459c1feb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-an-affiliate-application"></a><span data-ttu-id="97330-102">Cómo crear una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="97330-102">How to Create an Affiliate Application</span></span>
<span data-ttu-id="97330-103">Puede utilizar el Complemento MMC o este comando para crear una o más aplicaciones, como especificó el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="97330-103">You can use the MMC Snap-In or this command to create one or more applications, as specified by the XML file.</span></span> <span data-ttu-id="97330-104">Un ejemplo de un archivo XML para SSO iniciado por Windows es:</span><span class="sxs-lookup"><span data-stu-id="97330-104">An example XML file for Windows Initiated SSO is:</span></span>  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags groupApp="no" configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 <span data-ttu-id="97330-105">Tras crear una aplicación afiliada, no podrá modificar las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="97330-105">After you create an affiliate application, you cannot modify the following properties:</span></span>  
  
-   <span data-ttu-id="97330-106">Nombre de la aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="97330-106">Name of the affiliate application</span></span>  
  
-   <span data-ttu-id="97330-107">Campos asociados con la aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="97330-107">Fields associated with the affiliate application</span></span>  
  
-   <span data-ttu-id="97330-108">Tipo de aplicación afiliada (grupo de host, individual o almacén de configuración)</span><span class="sxs-lookup"><span data-stu-id="97330-108">Affiliate application type (host group, individual, or configuration store)</span></span>  
  
-   <span data-ttu-id="97330-109">Cuenta de administración igual al grupo de administradores afiliados.</span><span class="sxs-lookup"><span data-stu-id="97330-109">Administration account same as affiliate administrators group.</span></span> <span data-ttu-id="97330-110">(Si especifica esta marca, se utilizará siempre el grupo de administradores afiliados como la cuenta de administrador para la aplicación afiliada)</span><span class="sxs-lookup"><span data-stu-id="97330-110">(Specifying this flag will always use the affiliate administrators group as the administrator account for this affiliate application)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="97330-111">Puede utilizar cuentas locales para la cuenta de administración y de usuario al establecer en Sí la marca allowLocalAccounts.</span><span class="sxs-lookup"><span data-stu-id="97330-111">You can use local accounts for the administration account and user account by setting the allowLocalAccounts flag to yes.</span></span> <span data-ttu-id="97330-112">Sin embargo, esta marca se debe utilizar sólo en escenarios de un sólo equipo.</span><span class="sxs-lookup"><span data-stu-id="97330-112">However, you should only use this flag in single-computer scenarios.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="97330-113">Para realizar esta tarea debe ser administrador de SSO o administrador afiliado de SSO.</span><span class="sxs-lookup"><span data-stu-id="97330-113">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
 <span data-ttu-id="97330-114">Después de crear esta aplicación afiliada, debe habilitarla.</span><span class="sxs-lookup"><span data-stu-id="97330-114">After you create the affiliate application, you must enable it.</span></span> <span data-ttu-id="97330-115">Para obtener más información, consulte [cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md).</span><span class="sxs-lookup"><span data-stu-id="97330-115">For more information, see [How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md).</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="97330-116">Para crear una aplicación afiliada con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="97330-116">To create an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="97330-117">En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="97330-117">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="97330-118">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="97330-118">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="97330-119">Haga clic en **aplicaciones afiliadas**y, a continuación, haga clic en **crear aplicación**.</span><span class="sxs-lookup"><span data-stu-id="97330-119">Right-click **Affiliate Applications**, and then click **Create Application**.</span></span>  
  
4.  <span data-ttu-id="97330-120">Siga las instrucciones de la **Enterprise Single Sign-On Asistente para aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="97330-120">Follow the instructions in the **Enterprise Single Sign-On Application Wizard**.</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="97330-121">Para crear una aplicación afiliada con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="97330-121">To create an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="97330-122">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="97330-122">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="97330-123">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="97330-123">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="97330-124">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="97330-124">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="97330-125">Tipo de **ssomanage – createapps  *\<nombre de archivo de aplicación >***, donde  *\<nombre de archivo de aplicación >* es el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="97330-125">Type **ssomanage –createapps *\<application file name>***, where *\<application file name>* is the XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="97330-126">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="97330-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97330-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="97330-127">See Also</span></span>  
 <span data-ttu-id="97330-128">[Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="97330-128">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="97330-129">[Cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="97330-129">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="97330-130">[Cómo eliminar una aplicación afiliada](../core/how-to-delete-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="97330-130">[How to Delete an Affiliate Application](../core/how-to-delete-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="97330-131">[Administrar asignaciones de usuario](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="97330-131">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="97330-132">Administrar aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="97330-132">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)