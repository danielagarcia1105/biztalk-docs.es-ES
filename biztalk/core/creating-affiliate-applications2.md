---
title: Crear aplicaciones afiliadas para PeopleSoft Enterprise | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95151163-5aaf-4683-afb7-02949ccda3e1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a77926fa9d98606770ad2fe7715a3b0ff66ea5c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="3b717-102">Crear aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="3b717-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="3b717-103">En los pasos siguientes se indica cómo comenzar a utilizar aplicaciones afiliadas y el Inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="3b717-103">The following steps show how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b717-104">Si recibe errores de SSO, compruebe que se ha utilizado una cuenta de dominio en la configuración de BizTalk Server, ya que puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="3b717-104">If you receive SSO errors, verify that you used a domain account when you were configuring BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="3b717-105">SSO sólo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="3b717-105">SSO only functions under a domain account.</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="3b717-106">Crear una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="3b717-106">Create an affiliate application</span></span>  
  
1.  <span data-ttu-id="3b717-107">En el Panel de Control, abra **Services**y compruebe que está ejecutando el servicio de Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="3b717-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="3b717-108">En el símbolo del sistema, cambie los directorios a la carpeta de instalación de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="3b717-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="3b717-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3b717-109">For example:</span></span>  
  
     <span data-ttu-id="3b717-110">**C:\Program programa\Archivos comunes\enterprise Single Sign-On >**</span><span class="sxs-lookup"><span data-stu-id="3b717-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="3b717-111">Utilice los comandos del Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="3b717-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="3b717-112">Para obtener una lista de comandos, utilice la **-ayuda** cambiar.</span><span class="sxs-lookup"><span data-stu-id="3b717-112">For a list of commands, use the **-help** switch.</span></span>  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  <span data-ttu-id="3b717-113">Para crear una aplicación afiliada utilizando un archivo *.XML como inicio, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3b717-113">To create the affiliate application by using *.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="3b717-114">donde:</span><span class="sxs-lookup"><span data-stu-id="3b717-114">where:</span></span>  
  
    -   <span data-ttu-id="3b717-115">C:\SSOtest es la carpeta que contiene la aplicación XML.</span><span class="sxs-lookup"><span data-stu-id="3b717-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
    -   <span data-ttu-id="3b717-116">El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="3b717-116">AffiliateApplication.xml is the application XML you created that contains the sign-on information.</span></span>  
  
     <span data-ttu-id="3b717-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3b717-117">For example:</span></span>  
  
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
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="3b717-118">Crear vales de inicio de sesión únicos</span><span class="sxs-lookup"><span data-stu-id="3b717-118">Create Single Sign-On Tickets</span></span>  
  
1.  <span data-ttu-id="3b717-119">Escriba el comando siguiente para controlar el comportamiento del vale SSO:</span><span class="sxs-lookup"><span data-stu-id="3b717-119">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="3b717-120">Responda a las preguntas:</span><span class="sxs-lookup"><span data-stu-id="3b717-120">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="3b717-121">Una vez completada, recibirá una confirmación:</span><span class="sxs-lookup"><span data-stu-id="3b717-121">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="3b717-122">**Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**</span><span class="sxs-lookup"><span data-stu-id="3b717-122">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-the-affiliate-application-xml"></a><span data-ttu-id="3b717-123">Habilitar la aplicación afiliada XML</span><span class="sxs-lookup"><span data-stu-id="3b717-123">Enable the Affiliate Application XML</span></span>  
  
1.  <span data-ttu-id="3b717-124">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3b717-124">Type the following command:</span></span>  
  
     `ssomanage -enableapp PeopleSoftApp`  
  
2.  <span data-ttu-id="3b717-125">Escriba el comando siguiente para que se enumeren las aplicaciones y para comprobar que se ha creado la aplicación:</span><span class="sxs-lookup"><span data-stu-id="3b717-125">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="3b717-126">Aparecerán en una lista las aplicaciones afiliadas disponibles para su utilización.</span><span class="sxs-lookup"><span data-stu-id="3b717-126">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="3b717-127">**Aplicaciones disponibles para IBI\YourID - PeopleSoftApp**</span><span class="sxs-lookup"><span data-stu-id="3b717-127">**Applications available for IBI\YourID - PeopleSoftApp**</span></span>  
  
3.  <span data-ttu-id="3b717-128">Escriba el siguiente comando para establecer al afiliada credenciales de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="3b717-128">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials PeopleSoftApp`  
  
4.  <span data-ttu-id="3b717-129">Escriba el nombre de usuario y la contraseña en los cuadros.</span><span class="sxs-lookup"><span data-stu-id="3b717-129">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="3b717-130">Escriba las credenciales de inicio de sesión para la aplicación afiliada PeopleSoftApp.</span><span class="sxs-lookup"><span data-stu-id="3b717-130">Enter the logon credentials for the PeopleSoftApp affiliate application.</span></span>  
  
     <span data-ttu-id="3b717-131">Por ejemplo, escriba la identificación de usuario y la contraseña para que el usuario obtenga acceso al sistema a través del servidor SSO.</span><span class="sxs-lookup"><span data-stu-id="3b717-131">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="3b717-132">**Id. de usuario:**`user`</span><span class="sxs-lookup"><span data-stu-id="3b717-132">**User ID:** `user`</span></span>  
  
    -   <span data-ttu-id="3b717-133">**Contraseña:**`******`</span><span class="sxs-lookup"><span data-stu-id="3b717-133">**Password:** `******`</span></span>  
  
    -   <span data-ttu-id="3b717-134">**¿Confirmar? Contraseña:**`******`</span><span class="sxs-lookup"><span data-stu-id="3b717-134">**Confirm? Password:** `******`</span></span>  
  
5.  <span data-ttu-id="3b717-135">La aplicación afiliada aparecerá en el cuadro de diálogo Adaptador BizTalk para PeopleSoft Enterprise Transport Properties.</span><span class="sxs-lookup"><span data-stu-id="3b717-135">The affiliate application appears in the BizTalk Adapter for PeopleSoft Enterprise Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b717-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b717-136">See Also</span></span>  
 [<span data-ttu-id="3b717-137">Proteger el adaptador</span><span class="sxs-lookup"><span data-stu-id="3b717-137">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)