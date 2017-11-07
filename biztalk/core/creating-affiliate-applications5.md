---
title: Crear aplicaciones afiliadas para TIBCO EMS | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 191e5b56-dab9-4bf3-9f89-a900907d64e0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce5df15794886f9177f12f2a9e9a33e3ffdc335f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="create-affiliate-applications"></a><span data-ttu-id="f8a49-102">Crear aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="f8a49-102">Create Affiliate Applications</span></span>
<span data-ttu-id="f8a49-103">En los pasos siguientes se describe cómo comenzar a usar aplicaciones afiliadas y el Inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="f8a49-103">The following steps describe how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8a49-104">Si recibe errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server; esto puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="f8a49-104">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server; this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="f8a49-105">SSO solo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="f8a49-105">SSO only functions under a domain account</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="f8a49-106">Crear una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="f8a49-106">Create an affiliate application</span></span>  
  
1.  <span data-ttu-id="f8a49-107">En el Panel de Control, abra **Services**y compruebe que está ejecutando el servicio de Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="f8a49-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="f8a49-108">En el símbolo del sistema, cambie los directorios a la carpeta de instalación de Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="f8a49-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="f8a49-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f8a49-109">For example:</span></span>  
  
     <span data-ttu-id="f8a49-110">**C:\Program programa\Archivos comunes\enterprise Single Sign-On >**</span><span class="sxs-lookup"><span data-stu-id="f8a49-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="f8a49-111">Utilice los comandos del Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="f8a49-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="f8a49-112">Para obtener una lista de comandos, utilice la **-ayuda** cambiar.</span><span class="sxs-lookup"><span data-stu-id="f8a49-112">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="f8a49-113">Para crear una aplicación afiliada utilizando un archivo *.XML como inicio, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f8a49-113">To create the affiliate application by using *.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="f8a49-114">donde:</span><span class="sxs-lookup"><span data-stu-id="f8a49-114">where:</span></span>  
  
    -   <span data-ttu-id="f8a49-115">C:\SSOtest es la carpeta que contiene la aplicación XML.</span><span class="sxs-lookup"><span data-stu-id="f8a49-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
    -   <span data-ttu-id="f8a49-116">El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="f8a49-116">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="f8a49-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f8a49-117">For example:</span></span>  
  
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
  
 <span data-ttu-id="f8a49-118">Mediante el uso del XML de ejemplo, la aplicación afiliada, TIBCO EMS App, contiene los valores mostrados en el indicador de comandos.</span><span class="sxs-lookup"><span data-stu-id="f8a49-118">By using the example XML, the affiliate application, TIBCO EMS App, contains the values as shown in the command prompt.</span></span>  
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="f8a49-119">Crear vales de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="f8a49-119">Create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="f8a49-120">Escriba el comando siguiente para controlar el comportamiento del vale SSO:</span><span class="sxs-lookup"><span data-stu-id="f8a49-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="f8a49-121">Responda a las preguntas:</span><span class="sxs-lookup"><span data-stu-id="f8a49-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="f8a49-122">Una vez completada, recibirá una confirmación:</span><span class="sxs-lookup"><span data-stu-id="f8a49-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="f8a49-123">**Se está utilizando el servidor SSO en este equipo. La operación finalizada correctamente.**</span><span class="sxs-lookup"><span data-stu-id="f8a49-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-affiliate-application-xml"></a><span data-ttu-id="f8a49-124">Habilitar la aplicación afiliada de XML</span><span class="sxs-lookup"><span data-stu-id="f8a49-124">Enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="f8a49-125">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f8a49-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp TIBCO EMSApp`  
  
2.  <span data-ttu-id="f8a49-126">Escriba el comando siguiente para que se enumeren las aplicaciones y para comprobar que se ha creado la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f8a49-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="f8a49-127">Aparecerán en una lista las aplicaciones afiliadas disponibles para su utilización:</span><span class="sxs-lookup"><span data-stu-id="f8a49-127">The affiliate applications that are available for use appear in a list:</span></span>  
  
     <span data-ttu-id="f8a49-128">**Aplicaciones disponibles para IBI\YourID - TIBCO EMSApp**</span><span class="sxs-lookup"><span data-stu-id="f8a49-128">**Applications available for IBI\YourID - TIBCO EMSApp**</span></span>  
  
3.  <span data-ttu-id="f8a49-129">Escriba el siguiente comando para establecer al afiliada credenciales de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f8a49-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `soclient.exe -setcredentials TIBCO EMSApp`  
  
4.  <span data-ttu-id="f8a49-130">Escriba el nombre de usuario y la contraseña en los cuadros.</span><span class="sxs-lookup"><span data-stu-id="f8a49-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="f8a49-131">Escriba las credenciales de inicio de sesión para la aplicación afiliada TIBCO EMS App.</span><span class="sxs-lookup"><span data-stu-id="f8a49-131">Enter the logon credentials for the TIBCO EMS App affiliate application.</span></span>  
  
     <span data-ttu-id="f8a49-132">Por ejemplo, escriba la identificación de usuario y la contraseña para que el usuario obtenga acceso al sistema a través del servidor SSO.</span><span class="sxs-lookup"><span data-stu-id="f8a49-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="f8a49-133">Id. de usuario: **usuario**</span><span class="sxs-lookup"><span data-stu-id="f8a49-133">User ID: **user**</span></span>  
  
    -   <span data-ttu-id="f8a49-134">Contraseña:`******`</span><span class="sxs-lookup"><span data-stu-id="f8a49-134">Password: `******`</span></span>  
  
    -   <span data-ttu-id="f8a49-135">Confirmar?</span><span class="sxs-lookup"><span data-stu-id="f8a49-135">Confirm?</span></span> <span data-ttu-id="f8a49-136">Contraseña:`******`</span><span class="sxs-lookup"><span data-stu-id="f8a49-136">Password: `******`</span></span>  
  
     <span data-ttu-id="f8a49-137">La aplicación afiliada aparecerá en el adaptador de BizTalk para TIBCO EMS **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f8a49-137">The affiliate application appears in the BizTalk Adapter for TIBCO EMS **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a49-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8a49-138">See Also</span></span>  
[<span data-ttu-id="f8a49-139">Proteger el adaptador</span><span class="sxs-lookup"><span data-stu-id="f8a49-139">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-tibco-ems.md)