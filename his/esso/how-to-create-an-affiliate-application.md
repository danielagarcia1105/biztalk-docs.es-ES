---
title: Cómo crear una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3be483f8-2617-459e-9081-aab886c75d93
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5145111b2c585edab92cc10c3e3614e8bb91a85d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250992"
---
# <a name="how-to-create-an-affiliate-application"></a><span data-ttu-id="caac0-102">Cómo crear una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="caac0-102">How to Create an Affiliate Application</span></span>
<span data-ttu-id="caac0-103">Puede usar el complemento MMC o la **createapps** comando para crear una o varias aplicaciones, tal y como especifica el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="caac0-103">You can use the MMC Snap-In or the **createapps** command to create one or more applications, as specified by the XML file.</span></span> <span data-ttu-id="caac0-104">El siguiente es un archivo XML de ejemplo para Windows-Initiated Single Sign-On (SSO):</span><span class="sxs-lookup"><span data-stu-id="caac0-104">The following is an example XML file for Windows-Initiated Single Sign-On (SSO):</span></span>  
  
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
  
 <span data-ttu-id="caac0-105">Tras crear una aplicación afiliada, no podrá modificar las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="caac0-105">After you create an affiliate application, you cannot modify the following properties:</span></span>  
  
-   <span data-ttu-id="caac0-106">Nombre de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="caac0-106">Name of the affiliate application.</span></span>  
  
-   <span data-ttu-id="caac0-107">Campos asociados a la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="caac0-107">Fields associated with the affiliate application.</span></span>  
  
-   <span data-ttu-id="caac0-108">Afiliada de tipo de aplicación (almacén de configuración, individual, grupo de host).</span><span class="sxs-lookup"><span data-stu-id="caac0-108">Affiliate application type (host group, individual, or configuration store).</span></span>  
  
-   <span data-ttu-id="caac0-109">Cuenta de administración igual al grupo de administradores afiliados.</span><span class="sxs-lookup"><span data-stu-id="caac0-109">Administration account same as affiliate administrators group.</span></span> <span data-ttu-id="caac0-110">(Si especifica esta marca siempre usará el grupo de administradores afiliados como la cuenta de administrador para la aplicación afiliada.)</span><span class="sxs-lookup"><span data-stu-id="caac0-110">(Specifying this flag will always use the affiliate administrators group as the administrator account for this affiliate application.)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="caac0-111">Puede utilizar cuentas locales para la cuenta de administración y de usuario al establecer en Sí la marca allowLocalAccounts.</span><span class="sxs-lookup"><span data-stu-id="caac0-111">You can use local accounts for the administration account and user account by setting the allowLocalAccounts flag to yes.</span></span> <span data-ttu-id="caac0-112">Sin embargo, esta marca se debe utilizar sólo en escenarios de un sólo equipo.</span><span class="sxs-lookup"><span data-stu-id="caac0-112">However, you should only use this flag in single-computer scenarios.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="caac0-113">Para realizar esta tarea debe ser administrador de SSO o administrador afiliado de SSO.</span><span class="sxs-lookup"><span data-stu-id="caac0-113">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="caac0-114">Si va a realizar la configuración en un controlador de dominio y los grupos de ámbito Local de dominio se especifican para los administradores de aplicaciones o usuarios de la aplicación al crear aplicaciones afiliadas, se recomienda que habilite la marca de la cuenta local.</span><span class="sxs-lookup"><span data-stu-id="caac0-114">If you are performing the configuration on a Domain Controller, and the Domain Local scope groups are specified for Application Administrators or Application Users while creating Affiliate Applications, it is recommended that you enable the local account flag.</span></span> <span data-ttu-id="caac0-115">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="caac0-115">To do this:</span></span>  
  
-   <span data-ttu-id="caac0-116">En el complemento de MMC, seleccione Permitir cuentas locales para cuentas de acceso durante el proceso de creación.</span><span class="sxs-lookup"><span data-stu-id="caac0-116">In the MMC Snap-in, select Allow local accounts for access accounts during the creation process.</span></span>  
  
-   <span data-ttu-id="caac0-117">Desde la línea de comandos, especifique allowLocalAccounts = sí en el archivo XML para la creación de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="caac0-117">From the command line, specify allowLocalAccounts=yes in the XML file for Affiliate Application creation.</span></span>  
  
 <span data-ttu-id="caac0-118">Después de crear esta aplicación afiliada, debe habilitarla.</span><span class="sxs-lookup"><span data-stu-id="caac0-118">After you create the affiliate application, you must enable it.</span></span> <span data-ttu-id="caac0-119">Para obtener más información, consulte [cómo habilitar una aplicación afiliada](../esso/how-to-enable-an-affiliate-application.md).</span><span class="sxs-lookup"><span data-stu-id="caac0-119">For more information, see [How to Enable an Affiliate Application](../esso/how-to-enable-an-affiliate-application.md).</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-microsoft-management-console-mmc-snap-in"></a><span data-ttu-id="caac0-120">Para crear una aplicación afiliada con el complemento de Microsoft Management Console (MMC)</span><span class="sxs-lookup"><span data-stu-id="caac0-120">To create an affiliate application using the Microsoft Management Console (MMC) Snap-In</span></span>  
  
1.  <span data-ttu-id="caac0-121">Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="caac0-121">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="caac0-122">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="caac0-122">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="caac0-123">Haga clic en **aplicaciones afiliadas**y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="caac0-123">Right-click **Affiliate Applications**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="caac0-124">Siga las instrucciones de la **crear nueva aplicación afiliada** asistente.</span><span class="sxs-lookup"><span data-stu-id="caac0-124">Follow the instructions in the **Create New Affiliate Application** wizard.</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="caac0-125">Para crear una aplicación afiliada con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="caac0-125">To create an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="caac0-126">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="caac0-126">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="caac0-127">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="caac0-127">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="caac0-128">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="caac0-128">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="caac0-129">Tipo de `ssomanage –createapps <application file name>`, donde  *\<nombre de archivo de aplicación >* es el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="caac0-129">Type `ssomanage –createapps <application file name>`, where *\<application file name>* is the XML file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caac0-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="caac0-130">See Also</span></span>  
 <span data-ttu-id="caac0-131">[Aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="caac0-131">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="caac0-132">[Cómo habilitar una aplicación afiliada](../esso/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="caac0-132">[How to Enable an Affiliate Application](../esso/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="caac0-133">[Cómo eliminar una aplicación afiliada](../esso/how-to-delete-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="caac0-133">[How to Delete an Affiliate Application](../esso/how-to-delete-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="caac0-134">[Administrar asignaciones de usuario](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="caac0-134">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="caac0-135">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="caac0-135">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)