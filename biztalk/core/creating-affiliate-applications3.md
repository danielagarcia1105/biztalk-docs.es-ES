---
title: Crear aplicaciones afiliadas Applications3 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- affiliate applications
- Single Sign-On, creating tickets
- tickets, creating Single Sign-On
- affiliate applications, creating
- SSO tickets
ms.assetid: 800644fd-2286-4e59-894b-260f584dd29f
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 857ee7edd623332e72176ac09082f0ec9fc460f4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="cf3d1-102">Crear aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="cf3d1-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="cf3d1-103">Los pasos siguientes describen cómo empezar a usar aplicaciones afiliadas con el inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="cf3d1-103">The following steps describe how to get started with affiliate applications using Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf3d1-104">Si recibe errores de SSO, compruebe que usó una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio ESSO.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-104">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, because this affects the function of the ESSO service.</span></span> <span data-ttu-id="cf3d1-105">SSO sólo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-105">SSO only functions under a domain account.</span></span>  
  
## <a name="creating-an-affiliate-application"></a><span data-ttu-id="cf3d1-106">Creación de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="cf3d1-106">Creating an Affiliate Application</span></span>  
  
#### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="cf3d1-107">Para crear una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="cf3d1-107">To create an affiliate application</span></span>  
  
1.  <span data-ttu-id="cf3d1-108">En **el Panel de Control**, abra **Services**y compruebe que está ejecutando el servicio de Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-108">In **Control Panel**, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="cf3d1-109">En el símbolo del sistema, cambie los directorios a la carpeta de instalación de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-109">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="cf3d1-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf3d1-110">For example:</span></span>  
  
     <span data-ttu-id="cf3d1-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span><span class="sxs-lookup"><span data-stu-id="cf3d1-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="cf3d1-112">Utilice los comandos del Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-112">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="cf3d1-113">Para obtener una lista de comandos, use el modificador -help.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-113">For a list of commands, use the -help switch.</span></span>  
  
     <span data-ttu-id="cf3d1-114">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span><span class="sxs-lookup"><span data-stu-id="cf3d1-114">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span></span>  
  
4.  <span data-ttu-id="cf3d1-115">Para crear la aplicación afiliada mediante el \*. XML como un principio, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf3d1-115">To create the affiliate application using the \*.XML as a beginning, type in the following command:</span></span>  
  
     <span data-ttu-id="cf3d1-116">**ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml**</span><span class="sxs-lookup"><span data-stu-id="cf3d1-116">**ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml**</span></span>  
  
     <span data-ttu-id="cf3d1-117">donde:</span><span class="sxs-lookup"><span data-stu-id="cf3d1-117">where:</span></span>  
  
     <span data-ttu-id="cf3d1-118">C:\SSOtest es la carpeta que contiene el XML de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-118">C:\SSOtest is the folder containing your application XML.</span></span>  
  
     <span data-ttu-id="cf3d1-119">El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-119">AffiliateApplication.xml is the application XML you created containing the Sign On information.</span></span>  
  
     <span data-ttu-id="cf3d1-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf3d1-120">For example:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
         <application name="JDEdwardsApp">  
              <description>JDEdwards SSO Application</description>  
              <contact>someone@microsoft.com</contact>  
              <userGroup>ibi\Domain Users</userGroup>  
              <!—-an existing group on the domain controller - >   
              <appAdminGroup>ibi\YourID</appAdminGroup>  
              <!-- an existing account within the domain group - >   
              <field ordinal="0" label="User ID" masked="no" />  
              <field ordinal="1" label="Password" masked="yes" />  
              <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
         </application>  
    </SSO>  
    ```  
  
## <a name="creating-single-sign-on-tickets"></a><span data-ttu-id="cf3d1-121">Crear vales de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="cf3d1-121">Creating Single Sign-On Tickets</span></span>  
  
#### <a name="to-create-sso-tickets"></a><span data-ttu-id="cf3d1-122">Para crear vales SSO</span><span class="sxs-lookup"><span data-stu-id="cf3d1-122">To create SSO tickets</span></span>  
  
1.  <span data-ttu-id="cf3d1-123">Escriba el comando siguiente para controlar el comportamiento del vale SSO:</span><span class="sxs-lookup"><span data-stu-id="cf3d1-123">Type in the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="cf3d1-124">Responda a las preguntas:</span><span class="sxs-lookup"><span data-stu-id="cf3d1-124">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="cf3d1-125">Cuando haya terminado, recibirá un mensaje de confirmación:</span><span class="sxs-lookup"><span data-stu-id="cf3d1-125">On completion you receive a confirmation:</span></span>  
  
     <span data-ttu-id="cf3d1-126">**Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**</span><span class="sxs-lookup"><span data-stu-id="cf3d1-126">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enabling-the-affiliate-application-xml"></a><span data-ttu-id="cf3d1-127">Habilitar el archivo XML de aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-127">Enabling the Affiliate Application XML</span></span>  
  
#### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="cf3d1-128">Para habilitar un archivo XML de aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="cf3d1-128">To enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="cf3d1-129">Escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf3d1-129">Type in the following command:</span></span>  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  <span data-ttu-id="cf3d1-130">Escriba el siguiente comando para enumerar las aplicaciones y para comprobar que se creó la aplicación:</span><span class="sxs-lookup"><span data-stu-id="cf3d1-130">Type in the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="cf3d1-131">Las aplicaciones afiliadas disponibles para usar aparecen en una lista.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-131">The Affiliate Applications available for use appear in a list.</span></span>  
  
     <span data-ttu-id="cf3d1-132">**Aplicaciones disponibles para IBI\YourID - JDEdwardsApp**</span><span class="sxs-lookup"><span data-stu-id="cf3d1-132">**Applications available for IBI\YourID - JDEdwardsApp**</span></span>  
  
3.  <span data-ttu-id="cf3d1-133">Escriba el comando siguiente para establecer las credenciales de la aplicación afiliada:</span><span class="sxs-lookup"><span data-stu-id="cf3d1-133">Type in the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  <span data-ttu-id="cf3d1-134">Escriba el nombre de usuario y la contraseña en los cuadros.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-134">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="cf3d1-135">Escriba las credenciales de inicio de sesión para la aplicación afiliada JDEdwardsApp.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-135">Enter the logon credentials for the JDEdwardsApp affiliate application.</span></span> <span data-ttu-id="cf3d1-136">Por ejemplo, escriba la identificación de usuario y la contraseña para que el usuario obtenga acceso al sistema a través del servidor SSO.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-136">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="cf3d1-137">**Id. de usuario:** usuario</span><span class="sxs-lookup"><span data-stu-id="cf3d1-137">**User ID:** user</span></span>  
  
    -   <span data-ttu-id="cf3d1-138">**Contraseña:** ******</span><span class="sxs-lookup"><span data-stu-id="cf3d1-138">**Password:** ******</span></span>  
  
    -   <span data-ttu-id="cf3d1-139">**¿Confirmar? Contraseña:** ******</span><span class="sxs-lookup"><span data-stu-id="cf3d1-139">**Confirm? Password:** ******</span></span>  
  
5.  <span data-ttu-id="cf3d1-140">La aplicación afiliada aparece en la lista desplegable del cuadro de diálogo Propiedades de transporte de BizTalk Adapter para JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="cf3d1-140">The affiliate application appears in the drop-down list of the BizTalk Adapter for JD Edwards OneWorld Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf3d1-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf3d1-141">See Also</span></span>  
 [<span data-ttu-id="cf3d1-142">Seguridad en el adaptador</span><span class="sxs-lookup"><span data-stu-id="cf3d1-142">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)