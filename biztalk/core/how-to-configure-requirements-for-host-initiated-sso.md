---
title: "Cómo configurar los requisitos de Host para SSO iniciado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service accounts, granting privileges [SSO]
- host initiated SSO, configuring
- domain function level [SSO]
- host initiated SSO, Transaction Integrator (TI)
- SPN [SSO]
- managing [SSO], granting TCB privileges
- Transaction Integrator (TI)
- host initiated SSO, SPN
- host initiated SSO, TCB privileges
- configuring, host initiated SSO
- creating, SPNs [SSO]
- TCB privileges [SSO]
- managing [SSO], host initiated
- host initiated SSO, domain function level
- service accounts, SSO
- SSO, host initiated
- managing [SSO], creating SPNs
- SSO, service accounts
ms.assetid: 91d77c9f-bab2-4f6e-8bce-e31c59cebb20
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20b14539edc6b9b1026ca048feb881ce0d8a6d1e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-requirements-for-host-initiated-sso"></a><span data-ttu-id="dc047-102">Cómo configurar requisitos para SSO iniciado por host</span><span class="sxs-lookup"><span data-stu-id="dc047-102">How to Configure Requirements for Host Initiated SSO</span></span>
<span data-ttu-id="dc047-103">Si bien SSO empresarial y SSO iniciado por host tiene determinados aspectos en común, algunos requisitos de plataforma y Active Directory son únicos de SSO iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="dc047-103">Although Enterprise SSO and host initiated SSO have certain aspects in common, certain platform and Active Directory requirements are unique to host initiated SSO.</span></span> <span data-ttu-id="dc047-104">Este tema trata esos requisitos y enumera los pasos para comprobarlos o crearlos en el sistema.</span><span class="sxs-lookup"><span data-stu-id="dc047-104">This topic discusses those requirements, and lists the steps to check or create them on your system.</span></span>  
  
-   <span data-ttu-id="dc047-105">SSO iniciado por host se puede ejecutar solo en un entorno de dominio de Windows Server 2008 nativo.</span><span class="sxs-lookup"><span data-stu-id="dc047-105">Host initiated SSO can be executed only on a native Windows Server 2008 domain environment.</span></span>  
  
-   <span data-ttu-id="dc047-106">La cuenta de servicio SSO que lleva a cabo SSO iniciado por host debe estar configurada con privilegios TCB.</span><span class="sxs-lookup"><span data-stu-id="dc047-106">The service account for SSO Service that is performing host initiated SSO must be configured to have TCB privileges.</span></span> <span data-ttu-id="dc047-107">Puede configurar esto para la cuenta de servicio en la directiva de seguridad del dominio.</span><span class="sxs-lookup"><span data-stu-id="dc047-107">(You can configure this for the service account in the domain security policy.)</span></span>  
  
 <span data-ttu-id="dc047-108">Además, son necesarios determinados requisitos cuando se usa Transaction Integrator para el procesamiento iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="dc047-108">In addition, certain requirements are necessary when using Transaction Integrator for Host Initiated Processing.</span></span> <span data-ttu-id="dc047-109">TI for HIP aprovecha SSO iniciado por host para lograr inicio de sesión único para usuarios que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="dc047-109">TI for HIP leverages host initiated SSO to achieve Single Sign-On for non-Windows users.</span></span>  
  
 <span data-ttu-id="dc047-110">Por ejemplo, la cuenta de servicio de TI for HIP se ejecuta con una cuenta de dominio domainname\hipsvc.</span><span class="sxs-lookup"><span data-stu-id="dc047-110">For example, service account for TI for HIP service runs under a service account domainname\hipsvc.</span></span> <span data-ttu-id="dc047-111">Este servicio puede alojar aplicaciones que desean obtener acceso a recursos remotos o locales en Windows con la cuenta de Windows que corresponde a la cuenta que no es de Windows.</span><span class="sxs-lookup"><span data-stu-id="dc047-111">This service can host applications that want to access remote or local resources on Windows with the Windows account that correspond to the non-Windows account.</span></span>  
  
 <span data-ttu-id="dc047-112">La cuenta domainname\hipsvc debe pertenecer a la cuenta del grupo de administradores de aplicación para la aplicación afiliada que se usa para el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="dc047-112">The domainname\hipsvc account must belong to the Application Administrator group account for the Affiliate Application that is being used for Single Sign-On.</span></span>  
  
 <span data-ttu-id="dc047-113">La cuenta domainname\hipsvc debe tener privilegios de delegación restringida para usar el inicio de sesión único iniciado por host.</span><span class="sxs-lookup"><span data-stu-id="dc047-113">The domainname\hipsvc account must have constrained delegation privileges to use host initiated Single Sign-On.</span></span> <span data-ttu-id="dc047-114">Esto lo puede configurar el administrador del dominio en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dc047-114">This can be configured by the domain administrator in Active Directory.</span></span> <span data-ttu-id="dc047-115">Se puede configurar delegación para las cuentas que tienen SPN registrados.</span><span class="sxs-lookup"><span data-stu-id="dc047-115">Delegation can be configured for accounts that have registered SPNs.</span></span> <span data-ttu-id="dc047-116">La delegación restringida permite a la cuenta de servicio obtener acceso sólo a los componentes que especifica el administrador.</span><span class="sxs-lookup"><span data-stu-id="dc047-116">Constrained delegation allows the service account to access only components that are specified by the administrator.</span></span>  
  
### <a name="to-check-your-domain-function-level"></a><span data-ttu-id="dc047-117">Para comprobar su nivel funcional del dominio</span><span class="sxs-lookup"><span data-stu-id="dc047-117">To check your domain function level</span></span>  
  
1.  <span data-ttu-id="dc047-118">En su **dominios de Active Directory y confianzas** complemento MMC, derecho, haga clic en el nodo **dominios de Active Directory y confianzas**y, a continuación, haga clic en **elevar el nivel funcional del bosque**.</span><span class="sxs-lookup"><span data-stu-id="dc047-118">In your **Active Directory Domains and Trusts** MMC snap-in, right click the node **Active Directory Domains and Trusts**, and then click **Raise Forest Functional Level**.</span></span>  
  
2.  <span data-ttu-id="dc047-119">Compruebe que el nivel funcional es **Windows Server 2008**.</span><span class="sxs-lookup"><span data-stu-id="dc047-119">Verify that the functional level is **Windows Server 2008**.</span></span> <span data-ttu-id="dc047-120">Si no es así, consulte la documentación de Active Directory antes de intentar cambiar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="dc047-120">If it is not, refer to your Active Directory documentation before you attempt to change the setting.</span></span>  
  
### <a name="to-create-an-spn"></a><span data-ttu-id="dc047-121">Para crear un SPN</span><span class="sxs-lookup"><span data-stu-id="dc047-121">To create an SPN</span></span>  
  
1.  <span data-ttu-id="dc047-122">Descargue el **setspn** utilidad desde la siguiente ubicación: [http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178).</span><span class="sxs-lookup"><span data-stu-id="dc047-122">Download the **setspn** utility from the following location: [http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178).</span></span>  
  
2.  <span data-ttu-id="dc047-123">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="dc047-123">On the **Start** menu, click **Run**.</span></span>  
  
3.  <span data-ttu-id="dc047-124">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dc047-124">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="dc047-125">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc047-125">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="dc047-126">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="dc047-126">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
5.  <span data-ttu-id="dc047-127">Tipo de **setpsn - a hipsvc\computername.domain.com domain\hissvc**</span><span class="sxs-lookup"><span data-stu-id="dc047-127">Type **setpsn -a hipsvc\computername.domain.com domain\hissvc**</span></span>  
  
     <span data-ttu-id="dc047-128">donde **hipsvc\computername.domain.com** es el servicio que se llevará a cabo la operación y el equipo se está ejecutando, y **domain\hissvc** es la cuenta de servicio para hipsvc.</span><span class="sxs-lookup"><span data-stu-id="dc047-128">where **hipsvc\computername.domain.com** is the service that will perform the operation and the computer it is running on, and **domain\hissvc** is the service account for hipsvc.</span></span>  
  
 <span data-ttu-id="dc047-129">Tras hacer esto, puede configurar la delegación restringida en Active Directory para que esta cuenta de servicio (domain\hissvc) tenga acceso al recurso correspondiente en la red.</span><span class="sxs-lookup"><span data-stu-id="dc047-129">After doing this, you can configure constrained delegation in Active Directory for this service account (domain\hissvc) to access the appropriate resource in the network.</span></span>  
  
#### <a name="to-give-tcb-privileges-for-the-sso-service-account"></a><span data-ttu-id="dc047-130">Para conceder a TCB privilegios para la cuenta de servicio SSO</span><span class="sxs-lookup"><span data-stu-id="dc047-130">To give TCB privileges for the SSO service account</span></span>  
  
-   <span data-ttu-id="dc047-131">En su **asignación de derechos de usuario de directiva de seguridad de dominio - directivas locales -**, agregue la cuenta de servicio de SSO para el **actuar como parte del sistema operativo** directiva.</span><span class="sxs-lookup"><span data-stu-id="dc047-131">Under your **Domain Security Policy - Local Policies - User Rights Assignment**, add the SSO Service account to the **Act as part of operating system** policy.</span></span>  
  
     <span data-ttu-id="dc047-132">Para obtener más información acerca de Kerberos Protocol Transition and Constrained Delegation, vaya a [http://go.microsoft.com/fwlink/?LinkId=195484](http://go.microsoft.com/fwlink/?LinkId=195484).</span><span class="sxs-lookup"><span data-stu-id="dc047-132">For more information about Kerberos Protocol Transition and Constrained Delegation, go to [http://go.microsoft.com/fwlink/?LinkId=195484](http://go.microsoft.com/fwlink/?LinkId=195484).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc047-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc047-133">See Also</span></span>  
 [<span data-ttu-id="dc047-134">SSO iniciado por host</span><span class="sxs-lookup"><span data-stu-id="dc047-134">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)