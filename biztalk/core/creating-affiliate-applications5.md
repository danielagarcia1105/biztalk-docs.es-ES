---
title: Crear aplicaciones afiliadas Applications5 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, affiliate
- Single Sign-On, tickets
- affiliate applications
- creating affiliate applications
- tickets, SSO
- affiliate applications, enabling XML
- SSO tickets
ms.assetid: 191e5b56-dab9-4bf3-9f89-a900907d64e0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc6b42a6f3251d9e897af21fcb4207b6790e91cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="553be-102">Crear aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="553be-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="553be-103">En los pasos siguientes se describe cómo comenzar a usar aplicaciones afiliadas y el Inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="553be-103">The following steps describe how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="553be-104">Si recibe errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server; esto puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="553be-104">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server; this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="553be-105">SSO solo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="553be-105">SSO only functions under a domain account</span></span>  
  
### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="553be-106">Para crear una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="553be-106">To create an affiliate application</span></span>  
  
1.  <span data-ttu-id="553be-107">En el Panel de Control, abra **Services**y compruebe que está ejecutando el servicio de Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="553be-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="553be-108">En el símbolo del sistema, cambie los directorios a la carpeta de instalación de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="553be-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="553be-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="553be-109">For example:</span></span>  
  
     <span data-ttu-id="553be-110">**C:\Program programa\Archivos comunes\enterprise Single Sign-On >**</span><span class="sxs-lookup"><span data-stu-id="553be-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="553be-111">Utilice los comandos del Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="553be-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="553be-112">Para obtener una lista de comandos, utilice la **-ayuda** cambiar.</span><span class="sxs-lookup"><span data-stu-id="553be-112">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="553be-113">Para crear una aplicación afiliada utilizando un archivo *.XML como inicio, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="553be-113">To create the affiliate application by using *.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="553be-114">donde:</span><span class="sxs-lookup"><span data-stu-id="553be-114">where:</span></span>  
  
    -   <span data-ttu-id="553be-115">C:\SSOtest es la carpeta que contiene la aplicación XML.</span><span class="sxs-lookup"><span data-stu-id="553be-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
    -   <span data-ttu-id="553be-116">El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="553be-116">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="553be-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="553be-117">For example:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="TIBCO EMS App">  
            <description>TIBCO EMS SSO Application</description>  
            <contact>someone@example.com</contact>  
            <appUserAccount>DomainName\AppUserGroup</appUserAccount>  
            <!—an existing group on the domain controller - >   
            <appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
            <!-- an existing account in the domain group - >   
            <field ordinal="0" label="User ID" masked="no" />  
            <field ordinal="1" label="Password" masked="yes" />  
            <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
        </application>  
    </SSO>  
    ```  
  
 <span data-ttu-id="553be-118">Mediante el uso del XML de ejemplo, la aplicación afiliada, TIBCO EMS App, contiene los valores mostrados en el indicador de comandos.</span><span class="sxs-lookup"><span data-stu-id="553be-118">By using the example XML, the affiliate application, TIBCO EMS App, contains the values as shown in the command prompt.</span></span>  
  
### <a name="to-create-single-sign-on-tickets"></a><span data-ttu-id="553be-119">Para crear vales de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="553be-119">To create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="553be-120">Escriba el comando siguiente para controlar el comportamiento del vale SSO:</span><span class="sxs-lookup"><span data-stu-id="553be-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="553be-121">Responda a las preguntas:</span><span class="sxs-lookup"><span data-stu-id="553be-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="553be-122">Una vez completada, recibirá una confirmación:</span><span class="sxs-lookup"><span data-stu-id="553be-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="553be-123">**Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**</span><span class="sxs-lookup"><span data-stu-id="553be-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="553be-124">Para habilitar un archivo XML de aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="553be-124">To enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="553be-125">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="553be-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp TIBCO EMSApp`  
  
2.  <span data-ttu-id="553be-126">Escriba el comando siguiente para que se enumeren las aplicaciones y para comprobar que se ha creado la aplicación:</span><span class="sxs-lookup"><span data-stu-id="553be-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="553be-127">Aparecerán en una lista las aplicaciones afiliadas disponibles para su utilización:</span><span class="sxs-lookup"><span data-stu-id="553be-127">The affiliate applications that are available for use appear in a list:</span></span>  
  
     <span data-ttu-id="553be-128">**Aplicaciones disponibles para IBI\YourID - TIBCO EMSApp**</span><span class="sxs-lookup"><span data-stu-id="553be-128">**Applications available for IBI\YourID - TIBCO EMSApp**</span></span>  
  
3.  <span data-ttu-id="553be-129">Escriba el siguiente comando para establecer al afiliada credenciales de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="553be-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `soclient.exe -setcredentials TIBCO EMSApp`  
  
4.  <span data-ttu-id="553be-130">Escriba el nombre de usuario y la contraseña en los cuadros.</span><span class="sxs-lookup"><span data-stu-id="553be-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="553be-131">Escriba las credenciales de inicio de sesión para la aplicación afiliada TIBCO EMS App.</span><span class="sxs-lookup"><span data-stu-id="553be-131">Enter the logon credentials for the TIBCO EMS App affiliate application.</span></span>  
  
     <span data-ttu-id="553be-132">Por ejemplo, escriba la identificación de usuario y la contraseña para que el usuario obtenga acceso al sistema a través del servidor SSO.</span><span class="sxs-lookup"><span data-stu-id="553be-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="553be-133">Id. de usuario: **usuario**</span><span class="sxs-lookup"><span data-stu-id="553be-133">User ID: **user**</span></span>  
  
    -   <span data-ttu-id="553be-134">Contraseña:`******`</span><span class="sxs-lookup"><span data-stu-id="553be-134">Password: `******`</span></span>  
  
    -   <span data-ttu-id="553be-135">Confirmar?</span><span class="sxs-lookup"><span data-stu-id="553be-135">Confirm?</span></span> <span data-ttu-id="553be-136">Contraseña:`******`</span><span class="sxs-lookup"><span data-stu-id="553be-136">Password: `******`</span></span>  
  
     <span data-ttu-id="553be-137">La aplicación afiliada aparecerá en el adaptador de BizTalk para TIBCO EMS **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="553be-137">The affiliate application appears in the BizTalk Adapter for TIBCO EMS **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553be-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="553be-138">See Also</span></span>  
 [<span data-ttu-id="553be-139">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="553be-139">Using Single Sign-On</span></span>](../core/using-single-sign-on4.md)