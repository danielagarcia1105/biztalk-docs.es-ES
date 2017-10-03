---
title: Crear aplicaciones afiliadas aplicaciones 2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, creating tickets
- creating affiliate applications
- tickets, SSO
- affiliate applications, enabling XML
- affiliate applications, creating
- SSO tickets
ms.assetid: 95151163-5aaf-4683-afb7-02949ccda3e1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f39fbbfb62a9081937891b98e2b01a5e7f046e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="a7449-102">Crear aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="a7449-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="a7449-103">En los pasos siguientes se indica cómo comenzar a utilizar aplicaciones afiliadas y el Inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="a7449-103">The following steps show how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7449-104">Si recibe errores de SSO, compruebe que se ha utilizado una cuenta de dominio en la configuración de BizTalk Server, ya que puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="a7449-104">If you receive SSO errors, verify that you used a domain account when you were configuring BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="a7449-105">SSO sólo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="a7449-105">SSO only functions under a domain account.</span></span>  
  
### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="a7449-106">Para crear una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="a7449-106">To create an affiliate application</span></span>  
  
1.  <span data-ttu-id="a7449-107">En el Panel de Control, abra **Services**y compruebe que está ejecutando el servicio de Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="a7449-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="a7449-108">En el símbolo del sistema, cambie los directorios a la carpeta de instalación de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="a7449-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="a7449-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7449-109">For example:</span></span>  
  
     <span data-ttu-id="a7449-110">**C:\Program programa\Archivos comunes\enterprise Single Sign-On >**</span><span class="sxs-lookup"><span data-stu-id="a7449-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="a7449-111">Utilice los comandos del Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="a7449-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="a7449-112">Para obtener una lista de comandos, utilice la **-ayuda** cambiar.</span><span class="sxs-lookup"><span data-stu-id="a7449-112">For a list of commands, use the **-help** switch.</span></span>  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  <span data-ttu-id="a7449-113">Para crear una aplicación afiliada utilizando un archivo *.XML como inicio, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a7449-113">To create the affiliate application by using *.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="a7449-114">donde:</span><span class="sxs-lookup"><span data-stu-id="a7449-114">where:</span></span>  
  
    -   <span data-ttu-id="a7449-115">C:\SSOtest es la carpeta que contiene la aplicación XML.</span><span class="sxs-lookup"><span data-stu-id="a7449-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
    -   <span data-ttu-id="a7449-116">El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="a7449-116">AffiliateApplication.xml is the application XML you created that contains the sign-on information.</span></span>  
  
     <span data-ttu-id="a7449-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7449-117">For example:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
         <application name="PeopleSoftApp">  
              <description>PeopleSoft SSO Application</description>  
              <contact>someone@microsoft.com</contact>  
             <appUserAccount>DomainName\AppUserGroup</appUserAccount>  
              <!—-an existing group on the domain controller - >   
              <appAdminAccount>DomainName\AppAdminGroup<appAdminAccount>   
              <!-- an existing account in the domain group - >   
              <field ordinal="0" label="User ID" masked="no" />  
              <field ordinal="1" label="Password" masked="yes" />  
              <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
         </application>  
    </SSO>  
    ```  
  
## <a name="creating-single-sign-on-tickets"></a><span data-ttu-id="a7449-118">Crear vales de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="a7449-118">Creating Single Sign-On Tickets</span></span>  
  
#### <a name="to-create-sso-tickets"></a><span data-ttu-id="a7449-119">Para crear vales SSO</span><span class="sxs-lookup"><span data-stu-id="a7449-119">To create SSO tickets</span></span>  
  
1.  <span data-ttu-id="a7449-120">Escriba el comando siguiente para controlar el comportamiento del vale SSO:</span><span class="sxs-lookup"><span data-stu-id="a7449-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="a7449-121">Responda a las preguntas:</span><span class="sxs-lookup"><span data-stu-id="a7449-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="a7449-122">Una vez completada, recibirá una confirmación:</span><span class="sxs-lookup"><span data-stu-id="a7449-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="a7449-123">**Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**</span><span class="sxs-lookup"><span data-stu-id="a7449-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enabling-the-affiliate-application-xml"></a><span data-ttu-id="a7449-124">Habilitar el archivo XML de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="a7449-124">Enabling the Affiliate Application XML</span></span>  
  
#### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="a7449-125">Para habilitar un archivo XML de aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="a7449-125">To enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="a7449-126">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a7449-126">Type the following command:</span></span>  
  
     `ssomanage -enableapp PeopleSoftApp`  
  
2.  <span data-ttu-id="a7449-127">Escriba el comando siguiente para que se enumeren las aplicaciones y para comprobar que se ha creado la aplicación:</span><span class="sxs-lookup"><span data-stu-id="a7449-127">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="a7449-128">Aparecerán en una lista las aplicaciones afiliadas disponibles para su utilización.</span><span class="sxs-lookup"><span data-stu-id="a7449-128">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="a7449-129">**Aplicaciones disponibles para IBI\YourID - PeopleSoftApp**</span><span class="sxs-lookup"><span data-stu-id="a7449-129">**Applications available for IBI\YourID - PeopleSoftApp**</span></span>  
  
3.  <span data-ttu-id="a7449-130">Escriba el siguiente comando para establecer al afiliada credenciales de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="a7449-130">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials PeopleSoftApp`  
  
4.  <span data-ttu-id="a7449-131">Escriba el nombre de usuario y la contraseña en los cuadros.</span><span class="sxs-lookup"><span data-stu-id="a7449-131">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="a7449-132">Escriba las credenciales de inicio de sesión para la aplicación afiliada PeopleSoftApp.</span><span class="sxs-lookup"><span data-stu-id="a7449-132">Enter the logon credentials for the PeopleSoftApp affiliate application.</span></span>  
  
     <span data-ttu-id="a7449-133">Por ejemplo, escriba la identificación de usuario y la contraseña para que el usuario obtenga acceso al sistema a través del servidor SSO.</span><span class="sxs-lookup"><span data-stu-id="a7449-133">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="a7449-134">**Id. de usuario:**`user`</span><span class="sxs-lookup"><span data-stu-id="a7449-134">**User ID:** `user`</span></span>  
  
    -   <span data-ttu-id="a7449-135">**Contraseña:**`******`</span><span class="sxs-lookup"><span data-stu-id="a7449-135">**Password:** `******`</span></span>  
  
    -   <span data-ttu-id="a7449-136">**¿Confirmar? Contraseña:**`******`</span><span class="sxs-lookup"><span data-stu-id="a7449-136">**Confirm? Password:** `******`</span></span>  
  
5.  <span data-ttu-id="a7449-137">La aplicación afiliada aparecerá en el cuadro de diálogo Adaptador BizTalk para PeopleSoft Enterprise Transport Properties.</span><span class="sxs-lookup"><span data-stu-id="a7449-137">The affiliate application appears in the BizTalk Adapter for PeopleSoft Enterprise Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7449-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7449-138">See Also</span></span>  
 [<span data-ttu-id="a7449-139">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="a7449-139">Using Single Sign-On</span></span>](../core/using-single-sign-on2.md)