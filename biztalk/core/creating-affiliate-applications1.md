---
title: Crear aplicaciones para TIBCO Rendezvous afiliadas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f3603fcb-3594-460b-b74a-618e22d9c4e0
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a286a80ef2c867dd196fcdce414f2d0ff3c8255c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="05dc9-102">Crear aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="05dc9-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="05dc9-103">En los pasos siguientes se describe cómo comenzar a trabajar con aplicaciones afiliadas y el Inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="05dc9-103">The following steps describe how to start working with affiliate applications and Single Sign-On (SSO).</span></span> <span data-ttu-id="05dc9-104">Para obtener información completa acerca de cómo usar el Inicio de sesión único de Enterprise, vea la documentación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05dc9-104">For complete information about how to use Enterprise Single Sign-On, see the Microsoft documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05dc9-105">Si recibe errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="05dc9-105">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="05dc9-106">SSO sólo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="05dc9-106">SSO only functions under a domain account.</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="05dc9-107">Crear una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="05dc9-107">Create an affiliate application</span></span>  
  
1.  <span data-ttu-id="05dc9-108">En el Panel de Control, abra **Services**y compruebe que está ejecutando el servicio de Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="05dc9-108">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="05dc9-109">En el símbolo del sistema, cambie los directorios a la carpeta de instalación de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="05dc9-109">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span> <span data-ttu-id="05dc9-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="05dc9-110">For example:</span></span>  
  
     <span data-ttu-id="05dc9-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span><span class="sxs-lookup"><span data-stu-id="05dc9-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="05dc9-112">Utilice los comandos del Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="05dc9-112">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="05dc9-113">Para obtener una lista de comandos, utilice la **-ayuda** cambiar.</span><span class="sxs-lookup"><span data-stu-id="05dc9-113">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="05dc9-114">Para crear una aplicación afiliada utilizando un archivo \*.XML como inicio, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="05dc9-114">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="05dc9-115">Donde:</span><span class="sxs-lookup"><span data-stu-id="05dc9-115">Where:</span></span>  
  
     <span data-ttu-id="05dc9-116">C:\SSOtest es la carpeta que contiene la aplicación XML.</span><span class="sxs-lookup"><span data-stu-id="05dc9-116">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
     <span data-ttu-id="05dc9-117">El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="05dc9-117">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="05dc9-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="05dc9-118">For example:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="TIBCO RendezvousApp">  
            <description> TIBCO Rendezvous SSO Application</description>  
            <contact>someone@microsoft.com</contact>  
            <userGroup>ibi\Domain Users</userGroup>  
            <!—an existing group on the domain controller - >   
            <appAdminGroup>ibi\YourID</appAdminGroup>  
            <!-- an existing account within the domain group - >   
  
            <field ordinal="0" label="User ID" masked="no" />  
            <field ordinal="1" label="Password" masked="yes" />  
            <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
  
        </application>  
    </SSO>  
    ```  
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="05dc9-119">Crear vales de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="05dc9-119">Create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="05dc9-120">Escriba el comando siguiente para controlar el comportamiento del vale SSO:</span><span class="sxs-lookup"><span data-stu-id="05dc9-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="05dc9-121">Responda a las preguntas siguientes como se muestra:</span><span class="sxs-lookup"><span data-stu-id="05dc9-121">Answer the following questions as shown:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
3.  <span data-ttu-id="05dc9-122">Cuando haya terminado, recibirá el siguiente mensaje de confirmación:</span><span class="sxs-lookup"><span data-stu-id="05dc9-122">On completion, you receive the following confirmation:</span></span>  
  
     <span data-ttu-id="05dc9-123">**Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**</span><span class="sxs-lookup"><span data-stu-id="05dc9-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-affiliate-application-xml"></a><span data-ttu-id="05dc9-124">Habilitar la aplicación afiliada de XML</span><span class="sxs-lookup"><span data-stu-id="05dc9-124">Enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="05dc9-125">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="05dc9-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp TIBCO RendezvousApp`  
  
2.  <span data-ttu-id="05dc9-126">Escriba el comando siguiente para que se enumeren las aplicaciones y para comprobar que se ha creado la aplicación:</span><span class="sxs-lookup"><span data-stu-id="05dc9-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="05dc9-127">Aparecerán en una lista las aplicaciones afiliadas disponibles para su utilización.</span><span class="sxs-lookup"><span data-stu-id="05dc9-127">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="05dc9-128">**Aplicaciones disponibles para IBI\YourID - TIBCO RendezvousApp**</span><span class="sxs-lookup"><span data-stu-id="05dc9-128">**Applications available for IBI\YourID - TIBCO RendezvousApp**</span></span>  
  
3.  <span data-ttu-id="05dc9-129">Escriba el siguiente comando para establecer al afiliada credenciales de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="05dc9-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials TIBCO RendezvousApp`  
  
4.  <span data-ttu-id="05dc9-130">Escriba el nombre de usuario y contraseña en los cuadros.</span><span class="sxs-lookup"><span data-stu-id="05dc9-130">Enter the User name and password at the prompts.</span></span>  
  
5.  <span data-ttu-id="05dc9-131">Escriba las credenciales de inicio de sesión para la aplicación afiliada TIBCO RendezvousApp.</span><span class="sxs-lookup"><span data-stu-id="05dc9-131">Enter the logon credentials for the TIBCO RendezvousApp affiliate application.</span></span>  
  
     <span data-ttu-id="05dc9-132">Por ejemplo, escriba la identificación de usuario y la contraseña para que dicho usuario obtenga acceso al sistema a través del servidor SSO.</span><span class="sxs-lookup"><span data-stu-id="05dc9-132">For example, enter the user identification and the password for the user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="05dc9-133">Id. de usuario: usuario</span><span class="sxs-lookup"><span data-stu-id="05dc9-133">User ID: user</span></span>  
  
    -   <span data-ttu-id="05dc9-134">Contraseña: ******</span><span class="sxs-lookup"><span data-stu-id="05dc9-134">Password: ******</span></span>  
  
    -   <span data-ttu-id="05dc9-135">Confirmar contraseña: ******</span><span class="sxs-lookup"><span data-stu-id="05dc9-135">Confirm Password: ******</span></span>  
  
6.  <span data-ttu-id="05dc9-136">La aplicación afiliada aparecerá en el adaptador de BizTalk para TIBCO Rendezvous **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="05dc9-136">The affiliate application appears in the BizTalk Adapter for TIBCO Rendezvous **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05dc9-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="05dc9-137">See Also</span></span>  
 [<span data-ttu-id="05dc9-138">Seguridad en el adaptador de BizTalk para TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="05dc9-138">Security in BizTalk Adapter for TIBCO Rendezvous</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)   