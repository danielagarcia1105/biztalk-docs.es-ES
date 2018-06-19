---
title: Cómo crear aplicaciones afiliadas para Host SSO iniciado por | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], host initiated SSO
- creating, applications [SSO]
- host initiated SSO, creating affiliate applications
ms.assetid: 06202d21-055a-46bc-acff-da461f5673f1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce8a5cf43cd1d6e455492a74985edb91f2cb0a94
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971290"
---
# <a name="how-to-create-affiliate-applications-for-host-initiated-sso"></a><span data-ttu-id="6ff5b-102">Cómo crear aplicaciones afiliadas SSO iniciado por Host</span><span class="sxs-lookup"><span data-stu-id="6ff5b-102">How to Create Affiliate Applications for Host Initiated SSO</span></span>
<span data-ttu-id="6ff5b-103">Se pueden definir dos tipos de aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="6ff5b-103">You can define two types of applications:</span></span>  
  
-   <span data-ttu-id="6ff5b-104">**Individuales** hay una relación de 1 a 1 entre los usuarios de Windows y distinta de Windows.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-104">**Individual** There is a 1 to 1 relationship between Windows users and non-Windows users.</span></span>  
  
-   <span data-ttu-id="6ff5b-105">**Grupo host** varios usuarios de Windows no pueden asignarse a la misma cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-105">**Host Group** Multiple non-Windows users can be mapped to the same Windows account.</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="6ff5b-106">Para crear una aplicación afiliada con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="6ff5b-106">To create an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="6ff5b-107">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-107">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="6ff5b-108">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-108">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="6ff5b-109">Haga clic en **aplicaciones afiliadas**y, a continuación, haga clic en **crear aplicación** para abrir el **Enterprise Single Sign-On Asistente para aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-109">Right-click **Affiliate Applications**, and then click **Create Application** to open the **Enterprise Single Sign-On Application Wizard**.</span></span>  
  
4.  <span data-ttu-id="6ff5b-110">Utilice el asistente para seleccionar las propiedades de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-110">Use the wizard to select the properties of your affiliate application.</span></span>  
  
### <a name="to-create-an-individual-type-affiliate-application-using-the-command-line"></a><span data-ttu-id="6ff5b-111">Para crear una aplicación afiliada de tipo individual utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="6ff5b-111">To create an individual type affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="6ff5b-112">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-112">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="6ff5b-113">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-113">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="6ff5b-114">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="6ff5b-115">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-115">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="6ff5b-116">Tipo de **ssomanage – createapps \<AffApp.xml\>**, donde AffApp.xml es el nombre del archivo xml.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-116">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6ff5b-117">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="6ff5b-118">A continuación, se muestra un archivo de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ff5b-118">A sample file is shown below:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
      <application name="SSOApp_Host1">  
        <description>An Individual Type Affiliate Application for Host Initiated SSO</description>  
        <contact>someone@companyname.com</contact>  
        <appUserAccount>DomainName\AppUserGroup_HISSO</appUserAccount>  
        <appAdminAccount>DomainName\AppAdminGroup_HISSO</appAdminAccount>  
        <field ordinal="0" label="User ID" masked="no" />  
        <field ordinal="1" label="Password" masked="yes" />  
        <flags windowsInitiatedSSO="no" enableApp="yes" />  
      </application>  
    </SSO>  
  
    ```  
  
### <a name="to-create-a-host-group-type-affiliate-application-using-the-command-line"></a><span data-ttu-id="6ff5b-119">Para crear una aplicación afiliada de tipo de grupo de host utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="6ff5b-119">To create a host group type affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="6ff5b-120">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-120">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="6ff5b-121">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-121">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="6ff5b-122">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="6ff5b-123">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-123">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="6ff5b-124">Tipo de **ssomanage – createapps \<AffApp.xml\>**, donde AffApp.xml es el nombre del archivo xml.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-124">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6ff5b-125">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-125">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="6ff5b-126">A continuación, se muestra un archivo de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ff5b-126">A sample file is shown below:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
      <application name="SSOApp_HostGroupApp1">  
        <description>A Group Type Affiliate Application for Host Initiated SSO associating multiple non-Windows user to a single Windows user account(DomainName\WindowsUserAccount1)</description>  
        <contact>someone@companyname.com</contact>  
        <windowsAccount>DomainName\WindowsUserAccount1</windowsAccount>  
        <appAdminAccount>DomainName\AppAdminGroup_HISSO</appAdminAccount>  
        <field ordinal="0" label="User ID" masked="no" />  
        <field ordinal="1" label="Password" masked="yes" />  
        <flags  enableApp="yes" />  
      </application>  
    </SSO>  
  
    ```  
  
### <a name="to-create-an-affiliate-application-supporting-both-windows-initiated-sso-and-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="6ff5b-127">Para crear una aplicación afiliada que admita tanto SSO iniciado por Windows como SSO iniciado por host utilizando la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="6ff5b-127">To create an affiliate application supporting both Windows initiated SSO and host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="6ff5b-128">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-128">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="6ff5b-129">En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-129">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="6ff5b-130">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-130">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="6ff5b-131">El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-131">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="6ff5b-132">Tipo de **ssomanage – createapps \<AffApp.xml\>**, donde AffApp.xml es el nombre del archivo xml.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-132">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6ff5b-133">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="6ff5b-133">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="6ff5b-134">A continuación, se muestra un archivo de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ff5b-134">A sample file is shown below:</span></span>  
  
    ```  
    <?xml version="1.0" ?>   
    - <SSO>  
    - <application name="SSOApp1">  
      <description>An Individual Type Affiliate Application for both Host Initiated SSO and Windows Initiated SSO</description>   
      <contact>someone@companyname.com</contact>   
      <appUserAccount>DomainName\AppUserGroup</appUserAccount>   
      <appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>   
      <field ordinal="0" label="User ID" masked="no" />   
      <field ordinal="1" label="Password" masked="yes" />   
      <flags  enableApp="yes" />   
      </application>  
      </SSO>  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6ff5b-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ff5b-135">See Also</span></span>  
 [<span data-ttu-id="6ff5b-136">SSO iniciado por host</span><span class="sxs-lookup"><span data-stu-id="6ff5b-136">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)