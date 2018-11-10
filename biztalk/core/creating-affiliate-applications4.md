---
title: Creación de aplicaciones afiliadas Applications4 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tickets, Single Sign-On
- affiliate applications, setting credentials
- affiliate applications
- Single Sign-On, creating tickets
- SSO tickets
ms.assetid: 790fbe21-8081-4d57-803f-23014c8a3135
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a62a8c2c6d2bb74c9e68fcdcf1304e6d0cd99d67
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752628"
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="559c9-102">Crear aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="559c9-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="559c9-103">Los pasos siguientes describen cómo empezar a trabajar con aplicaciones afiliadas con SSO.</span><span class="sxs-lookup"><span data-stu-id="559c9-103">The following steps describe how to get started with affiliate applications using SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="559c9-104">Si obtiene errores de SSO, compruebe que ha usado una cuenta de dominio al configurar BizTalk Server, ya que esto puede afectar al funcionamiento del servicio SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="559c9-104">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="559c9-105">SSO sólo funciona con una cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="559c9-105">SSO only functions under a domain account.</span></span>  
  
### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="559c9-106">Para crear una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="559c9-106">To create an affiliate application</span></span>  
  
1. <span data-ttu-id="559c9-107">En el Panel de Control, abra **servicios**y compruebe que se está ejecutando el servicio Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="559c9-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2. <span data-ttu-id="559c9-108">En el símbolo del sistema, vaya al directorio de la carpeta de instalación del inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="559c9-108">In a command prompt, change directories to the Enterprise Single Sign On folder.</span></span>  
  
    <span data-ttu-id="559c9-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="559c9-109">For example:</span></span>  
  
    <span data-ttu-id="559c9-110">**C:\Program Files\Common Files\Enterprise Single Sign-On >**</span><span class="sxs-lookup"><span data-stu-id="559c9-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3. <span data-ttu-id="559c9-111">Utilice los comandos del Inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="559c9-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="559c9-112">Para obtener una lista de comandos, utilice el **-ayuda** cambie.</span><span class="sxs-lookup"><span data-stu-id="559c9-112">For a list of commands, use the **-help** switch.</span></span>  
  
4. <span data-ttu-id="559c9-113">Para crear la aplicación afiliada mediante \*. XML como un principio, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="559c9-113">To create the affiliate application using \*.XML as a beginning, type the following command:</span></span>  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    <span data-ttu-id="559c9-114">donde:</span><span class="sxs-lookup"><span data-stu-id="559c9-114">where:</span></span>  
  
   - <span data-ttu-id="559c9-115">C:\SSOtest es la carpeta que contiene la aplicación XML.</span><span class="sxs-lookup"><span data-stu-id="559c9-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
   - <span data-ttu-id="559c9-116">El archivo AffiliateApplication.xml es la aplicación XML creada que contiene la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="559c9-116">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="559c9-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="559c9-117">For example:</span></span>  
  
   ```  
   <?xml version="1.0"?>  
   <SSO>  
       <application name="JDEdwardsApp">  
           <description>JDEdwards SSO Application</description>  
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
  
### <a name="to-create-single-sign-on-tickets"></a><span data-ttu-id="559c9-118">Para crear vales de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="559c9-118">To create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="559c9-119">Escriba el comando siguiente para controlar el comportamiento del vale SSO:</span><span class="sxs-lookup"><span data-stu-id="559c9-119">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="559c9-120">Responda a las preguntas siguientes como se muestra:</span><span class="sxs-lookup"><span data-stu-id="559c9-120">Answer the following questions as shown:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="559c9-121">Cuando haya terminado, recibirá el siguiente mensaje de confirmación:</span><span class="sxs-lookup"><span data-stu-id="559c9-121">On completion, you receive the following confirmation:</span></span>  
  
     <span data-ttu-id="559c9-122">**Se está utilizando el servidor SSO en este equipo. La operación se completó correctamente.**</span><span class="sxs-lookup"><span data-stu-id="559c9-122">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="559c9-123">Para habilitar un archivo XML de aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="559c9-123">To enable affiliate application XML</span></span>  
  
1. <span data-ttu-id="559c9-124">Escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="559c9-124">Type the following command:</span></span>  
  
    `ssomanage -enableapp JDEdwardsApp`  
  
2. <span data-ttu-id="559c9-125">Escriba el comando siguiente para que se enumeren las aplicaciones y para comprobar que se ha creado la aplicación:</span><span class="sxs-lookup"><span data-stu-id="559c9-125">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
    `ssoclient.exe –listapps`  
  
    <span data-ttu-id="559c9-126">Aparecerán en una lista las aplicaciones afiliadas disponibles para su uso:</span><span class="sxs-lookup"><span data-stu-id="559c9-126">The affiliate applications that are available for use display in a list:</span></span>  
  
    <span data-ttu-id="559c9-127">**Aplicaciones disponibles para IBI\YourID - JDEdwardsApp**</span><span class="sxs-lookup"><span data-stu-id="559c9-127">**Applications available for IBI\YourID - JDEdwardsApp**</span></span>  
  
3. <span data-ttu-id="559c9-128">Escriba el siguiente comando para establecer a la filial de credenciales de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="559c9-128">Type the following command to set the affiliate application credentials:</span></span>  
  
    `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4. <span data-ttu-id="559c9-129">Escriba el nombre de usuario y la contraseña en los cuadros.</span><span class="sxs-lookup"><span data-stu-id="559c9-129">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="559c9-130">Escriba las credenciales de inicio de sesión para la aplicación afiliada JDEdwardsApp.</span><span class="sxs-lookup"><span data-stu-id="559c9-130">Enter the logon credentials for the JDEdwardsApp affiliate application.</span></span>  
  
    <span data-ttu-id="559c9-131">Por ejemplo, escriba la identificación de usuario y la contraseña para que el usuario obtenga acceso al sistema a través del servidor SSO.</span><span class="sxs-lookup"><span data-stu-id="559c9-131">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
   - <span data-ttu-id="559c9-132">Id. de usuario: **usuario**</span><span class="sxs-lookup"><span data-stu-id="559c9-132">User ID: **user**</span></span>  
  
   - <span data-ttu-id="559c9-133">Contraseña: `******`</span><span class="sxs-lookup"><span data-stu-id="559c9-133">Password: `******`</span></span>  
  
   - <span data-ttu-id="559c9-134">Confirmar?</span><span class="sxs-lookup"><span data-stu-id="559c9-134">Confirm?</span></span> <span data-ttu-id="559c9-135">Contraseña: `******`</span><span class="sxs-lookup"><span data-stu-id="559c9-135">Password: `******`</span></span>  
  
     <span data-ttu-id="559c9-136">La aplicación afiliada aparecerá en el adaptador de BizTalk para JD Edwards EnterpriseOne **propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="559c9-136">The affiliate application appears in the BizTalk Adapter for JD Edwards EnterpriseOne **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="559c9-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="559c9-137">See Also</span></span>  
 [<span data-ttu-id="559c9-138">Seguridad del adaptador de BizTalk para JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="559c9-138">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)