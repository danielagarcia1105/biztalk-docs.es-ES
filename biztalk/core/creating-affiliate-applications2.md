---
title: Crear aplicaciones afiliadas para PeopleSoft Enterprise | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95151163-5aaf-4683-afb7-02949ccda3e1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f436c9c3193a895d38df630c1bec88abfadc12c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022890"
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="d6c2d-102">Crear aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="d6c2d-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="d6c2d-103">En los pasos siguientes se indica cómo comenzar a utilizar aplicaciones afiliadas y el Inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="d6c2d-103">The following steps show how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6c2d-104">Si recibe errores de SSO, compruebe que se ha utilizado una cuenta de dominio en la configuración de BizTalk Server, ya que puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-104">If you receive SSO errors, verify that you used a domain account when you were configuring BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="d6c2d-105">SSO sólo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-105">SSO only functions under a domain account.</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="d6c2d-106">Crear una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="d6c2d-106">Create an affiliate application</span></span>  
  
1. <span data-ttu-id="d6c2d-107">En el Panel de Control, abra **servicios**y compruebe que se está ejecutando el servicio Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2. <span data-ttu-id="d6c2d-108">En el símbolo del sistema, cambie los directorios a la carpeta de instalación de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
    <span data-ttu-id="d6c2d-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-109">For example:</span></span>  
  
    <span data-ttu-id="d6c2d-110">**C:\Program Files\Common Files\Enterprise Single Sign-On >**</span><span class="sxs-lookup"><span data-stu-id="d6c2d-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3. <span data-ttu-id="d6c2d-111">Utilice los comandos del Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="d6c2d-112">Para obtener una lista de comandos, utilice el **-ayuda** cambie.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-112">For a list of commands, use the **-help** switch.</span></span>  
  
    <span data-ttu-id="d6c2d-113">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span><span class="sxs-lookup"><span data-stu-id="d6c2d-113">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span></span>  
  
4. <span data-ttu-id="d6c2d-114">Para crear una aplicación afiliada utilizando un archivo \*.XML como inicio, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-114">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    <span data-ttu-id="d6c2d-115">donde:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-115">where:</span></span>  
  
   - <span data-ttu-id="d6c2d-116">C:\SSOtest es la carpeta que contiene la aplicación XML.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-116">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
   - <span data-ttu-id="d6c2d-117">El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-117">AffiliateApplication.xml is the application XML you created that contains the sign-on information.</span></span>  
  
     <span data-ttu-id="d6c2d-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-118">For example:</span></span>  
  
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
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="d6c2d-119">Crear vales de inicio de sesión únicos</span><span class="sxs-lookup"><span data-stu-id="d6c2d-119">Create Single Sign-On Tickets</span></span>  
  
1.  <span data-ttu-id="d6c2d-120">Escriba el comando siguiente para controlar el comportamiento del vale SSO:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="d6c2d-121">Responda a las preguntas:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="d6c2d-122">Una vez completada, recibirá una confirmación:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="d6c2d-123">**Se está utilizando el servidor SSO en este equipo. La operación se completó correctamente.**</span><span class="sxs-lookup"><span data-stu-id="d6c2d-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-the-affiliate-application-xml"></a><span data-ttu-id="d6c2d-124">Habilitar la aplicación afiliada XML</span><span class="sxs-lookup"><span data-stu-id="d6c2d-124">Enable the Affiliate Application XML</span></span>  
  
1.  <span data-ttu-id="d6c2d-125">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp PeopleSoftApp`  
  
2.  <span data-ttu-id="d6c2d-126">Escriba el comando siguiente para que se enumeren las aplicaciones y para comprobar que se ha creado la aplicación:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="d6c2d-127">Aparecerán en una lista las aplicaciones afiliadas disponibles para su utilización.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-127">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="d6c2d-128">**Aplicaciones disponibles para IBI\YourID - PeopleSoftApp**</span><span class="sxs-lookup"><span data-stu-id="d6c2d-128">**Applications available for IBI\YourID - PeopleSoftApp**</span></span>  
  
3.  <span data-ttu-id="d6c2d-129">Escriba el siguiente comando para establecer a la filial de credenciales de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="d6c2d-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials PeopleSoftApp`  
  
4.  <span data-ttu-id="d6c2d-130">Escriba el nombre de usuario y la contraseña en los cuadros.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="d6c2d-131">Escriba las credenciales de inicio de sesión para la aplicación afiliada PeopleSoftApp.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-131">Enter the logon credentials for the PeopleSoftApp affiliate application.</span></span>  
  
     <span data-ttu-id="d6c2d-132">Por ejemplo, escriba la identificación de usuario y la contraseña para que el usuario obtenga acceso al sistema a través del servidor SSO.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="d6c2d-133">**Id. de usuario:** `user`</span><span class="sxs-lookup"><span data-stu-id="d6c2d-133">**User ID:** `user`</span></span>  
  
    -   <span data-ttu-id="d6c2d-134">**Contraseña:** `******`</span><span class="sxs-lookup"><span data-stu-id="d6c2d-134">**Password:** `******`</span></span>  
  
    -   <span data-ttu-id="d6c2d-135">**¿Confirmar? Contraseña:** `******`</span><span class="sxs-lookup"><span data-stu-id="d6c2d-135">**Confirm? Password:** `******`</span></span>  
  
5.  <span data-ttu-id="d6c2d-136">La aplicación afiliada aparecerá en el cuadro de diálogo Adaptador BizTalk para PeopleSoft Enterprise Transport Properties.</span><span class="sxs-lookup"><span data-stu-id="d6c2d-136">The affiliate application appears in the BizTalk Adapter for PeopleSoft Enterprise Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c2d-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6c2d-137">See Also</span></span>  
 [<span data-ttu-id="d6c2d-138">Proteger el adaptador</span><span class="sxs-lookup"><span data-stu-id="d6c2d-138">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)