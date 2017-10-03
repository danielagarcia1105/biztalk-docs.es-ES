---
title: Asistente para la utilidad de certificados | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ff72810-c7b3-4f67-8f9f-e127eacc153e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e3acbb1198034e76bb1e0f45c0f9755ec6ac95d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="certificate-wizard-utility"></a><span data-ttu-id="2f616-102">Utilidad de Asistente para certificados</span><span class="sxs-lookup"><span data-stu-id="2f616-102">Certificate Wizard Utility</span></span>
<span data-ttu-id="2f616-103">Use la utilidad CertWizard para importar un certificado de un archivo .pfx o .cer en un almacén privado o público para usarlo con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f616-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2f616-104">El código fuente del Asistente para certificados puede encontrarse en el **C:\Program Files\Microsoft BizTalk Server \<versión > \SDK\Utilities\Certificate asistente** carpeta.</span><span class="sxs-lookup"><span data-stu-id="2f616-104">The source code for the Certificate Wizard can be found in the **C:\Program Files\Microsoft BizTalk Server \<version>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="2f616-105">Con un sistema operativo de 64 bits y la versión [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], estará en el **C:\Program Files (x86) \Microsoft BizTalk Server \<versión > \SDK\Utilities\Certificate asistente** carpeta.</span><span class="sxs-lookup"><span data-stu-id="2f616-105">With a 64-bit operating system and version of [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], it will be in the **C:\Program Files (x86)\Microsoft BizTalk Server \<version>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="2f616-106">Para usar el Asistente para certificados, en primer lugar deberá que generarlo mediante [!INCLUDE[vs2010](../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f616-106">To use the Certificate Wizard you will first have to build it using [!INCLUDE[vs2010](../includes/vs2010-md.md)].</span></span>  
  
 <span data-ttu-id="2f616-107">CertWizard importa una clave privada de un archivo .pfx en el almacén personal e importa una clave pública de un archivo .cer en un almacén público.</span><span class="sxs-lookup"><span data-stu-id="2f616-107">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="2f616-108">Al importar una clave privada, el certificado puede ser un certificado de descifrado para mensajes entrantes o un certificado de firma para mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="2f616-108">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="2f616-109">**Descripción de la sintaxis**</span><span class="sxs-lookup"><span data-stu-id="2f616-109">**Syntax Description**</span></span>  
  
 <span data-ttu-id="2f616-110">La siguiente tabla describe las partes de la sintaxis que usa la utilidad CertWizard.</span><span class="sxs-lookup"><span data-stu-id="2f616-110">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f616-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f616-111">Syntax</span></span>|<span data-ttu-id="2f616-112">Description</span><span class="sxs-lookup"><span data-stu-id="2f616-112">Description</span></span>|  
|<span data-ttu-id="2f616-113">Privatekey</span><span class="sxs-lookup"><span data-stu-id="2f616-113">Privatekey</span></span>|<span data-ttu-id="2f616-114">Usada para importar una clave privada.</span><span class="sxs-lookup"><span data-stu-id="2f616-114">Used to import a private key.</span></span>|  
|<span data-ttu-id="2f616-115">Publickey</span><span class="sxs-lookup"><span data-stu-id="2f616-115">Publickey</span></span>|<span data-ttu-id="2f616-116">Usada para importar una clave pública.</span><span class="sxs-lookup"><span data-stu-id="2f616-116">Used to import a public key.</span></span>|  
|<span data-ttu-id="2f616-117">Rootkey</span><span class="sxs-lookup"><span data-stu-id="2f616-117">Rootkey</span></span>|<span data-ttu-id="2f616-118">Usada para importar una clave raíz (de una autoridad de certificación).</span><span class="sxs-lookup"><span data-stu-id="2f616-118">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="2f616-119">filename.pfx (o .cer)</span><span class="sxs-lookup"><span data-stu-id="2f616-119">filename.pfx (or .cer)</span></span>|<span data-ttu-id="2f616-120">Ruta completa del archivo .pfx (claves privadas) o .cer (claves públicas).</span><span class="sxs-lookup"><span data-stu-id="2f616-120">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="2f616-121">Filepassword</span><span class="sxs-lookup"><span data-stu-id="2f616-121">Filepassword</span></span>|<span data-ttu-id="2f616-122">Contraseña requerida para desbloquear el archivo .pxf.</span><span class="sxs-lookup"><span data-stu-id="2f616-122">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="2f616-123">Useridentity</span><span class="sxs-lookup"><span data-stu-id="2f616-123">Useridentity</span></span>|<span data-ttu-id="2f616-124">Identidad de servicio que utilizan uno o varios host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2f616-124">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="2f616-125">Especifique una cuenta de usuario si no desea especificar el host pero desea importar un certificado en una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="2f616-125">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="2f616-126">**Nota:** si no se agrega el conmutador Useridentity, la utilidad importa y establecer el certificado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f616-126">**Note:**  If you do not add the Useridentity switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="2f616-127">**Nota:** si agrega el conmutador Useridentity, pero no especifica un valor, WMI genera automáticamente la identidad del usuario.</span><span class="sxs-lookup"><span data-stu-id="2f616-127">**Note:**  If you add the Useridentity switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="2f616-128">Contraseña</span><span class="sxs-lookup"><span data-stu-id="2f616-128">Password</span></span>|<span data-ttu-id="2f616-129">Contraseña del usuario de identidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="2f616-129">The password for the service identity user.</span></span>|  
|<span data-ttu-id="2f616-130">Thumbprint</span><span class="sxs-lookup"><span data-stu-id="2f616-130">Thumbprint</span></span>|<span data-ttu-id="2f616-131">La huella de un certificado específico, en caso de que el archivo contenga varios certificados.</span><span class="sxs-lookup"><span data-stu-id="2f616-131">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="2f616-132">**Nota:** para un archivo de certificado público, si el archivo contiene más de un certificado y no se especifica la huella digital, la utilidad importa todos los certificados en el archivo.</span><span class="sxs-lookup"><span data-stu-id="2f616-132">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="2f616-133">En el caso de un archivo de certificado privado, la utilidad solicita seleccionar el certificado que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="2f616-133">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="2f616-134">Uso</span><span class="sxs-lookup"><span data-stu-id="2f616-134">Usage</span></span>|<span data-ttu-id="2f616-135">Uso intencionado del certificado privado importado.</span><span class="sxs-lookup"><span data-stu-id="2f616-135">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="2f616-136">Puede ser uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f616-136">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="2f616-137">**inicio de sesión** (para un certificado de firma)</span><span class="sxs-lookup"><span data-stu-id="2f616-137">**sign** (for a signing certificate)</span></span><br /><br /> <span data-ttu-id="2f616-138">**descifrar** (para un certificado de descifrado)</span><span class="sxs-lookup"><span data-stu-id="2f616-138">**decrypt** (for a decryption certificate)</span></span><br /><br /> <span data-ttu-id="2f616-139">**ambos** (para un certificado que es un certificado de firma y un certificado de descifrado)</span><span class="sxs-lookup"><span data-stu-id="2f616-139">**both** (for a certificate that is both a signing certificate and a decryption certificate)</span></span><br /><br /> <span data-ttu-id="2f616-140">**Ninguno** (también para un certificado es un certificado de firma y un certificado de descifrado).</span><span class="sxs-lookup"><span data-stu-id="2f616-140">**none** (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="2f616-141">**Nota:** si el conmutador /Usage como se establece en none, el asistente no establecerá la huella digital del certificado en los Hosts de BizTalk o el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2f616-141">**Note:**  If you set the /Usage switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="2f616-142">Exportable</span><span class="sxs-lookup"><span data-stu-id="2f616-142">Exportable</span></span>|<span data-ttu-id="2f616-143">Puede ser **True** o **False**.</span><span class="sxs-lookup"><span data-stu-id="2f616-143">Can be **True** or **False**.</span></span> <span data-ttu-id="2f616-144">Si **True**, puede volver a exportar la clave privada.</span><span class="sxs-lookup"><span data-stu-id="2f616-144">If **True**, the private key can be re-exported.</span></span>|  
  
 <span data-ttu-id="2f616-145">**Sintaxis para importar una clave privada**</span><span class="sxs-lookup"><span data-stu-id="2f616-145">**Syntax for Importing a Private Key**</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
 <span data-ttu-id="2f616-146">**Sintaxis para importar una clave pública**</span><span class="sxs-lookup"><span data-stu-id="2f616-146">**Syntax for Importing a Public Key**</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
 <span data-ttu-id="2f616-147">**Sintaxis para importar una clave raíz**</span><span class="sxs-lookup"><span data-stu-id="2f616-147">**Syntax for Importing a Root Key**</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
## <a name="prerequisites"></a><span data-ttu-id="2f616-148">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2f616-148">Prerequisites</span></span>  
 <span data-ttu-id="2f616-149">A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:</span><span class="sxs-lookup"><span data-stu-id="2f616-149">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="2f616-150">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f616-150">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-run-the-certificate-wizard"></a><span data-ttu-id="2f616-151">Para ejecutar el Asistente para certificados</span><span class="sxs-lookup"><span data-stu-id="2f616-151">To run the certificate wizard</span></span>  
  
1.  <span data-ttu-id="2f616-152">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="2f616-152">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="2f616-153">Vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities.</span><span class="sxs-lookup"><span data-stu-id="2f616-153">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities.</span></span>  
  
3.  <span data-ttu-id="2f616-154">En el símbolo del sistema, escriba **CertWizard**, escriba los conmutadores requeridos y correspondientes y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="2f616-154">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f616-155">Si no proporciona el comando completo en el símbolo del sistema, CertWizard le solicitará que proporcione los valores requeridos.</span><span class="sxs-lookup"><span data-stu-id="2f616-155">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f616-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f616-156">See Also</span></span>  
 [<span data-ttu-id="2f616-157">Utilidades del SDK de</span><span class="sxs-lookup"><span data-stu-id="2f616-157">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)