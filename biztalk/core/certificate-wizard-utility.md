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
ms.openlocfilehash: 3b0341a11c45cd08f8476d48ea38cbf96bcc49c1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="certificate-wizard-utility"></a><span data-ttu-id="958c4-102">Utilidad de Asistente para certificados</span><span class="sxs-lookup"><span data-stu-id="958c4-102">Certificate Wizard Utility</span></span>
<span data-ttu-id="958c4-103">Use la utilidad CertWizard para importar un certificado de un archivo .pfx o .cer en un almacén privado o público para usarlo con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="958c4-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="958c4-104">El código fuente del Asistente para certificados puede encontrarse en el **C:\Program Files\Microsoft BizTalk Server \<versión\>\SDK\Utilities\Certificate asistente** carpeta.</span><span class="sxs-lookup"><span data-stu-id="958c4-104">The source code for the Certificate Wizard can be found in the **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="958c4-105">Con un sistema operativo de 64 bits y la versión de BizTalk Server, estará en el **C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\SDK\Utilities\Certificate asistente** carpeta.</span><span class="sxs-lookup"><span data-stu-id="958c4-105">With a 64-bit operating system and version of BizTalk Server, it will be in the **C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\SDK\Utilities\Certificate Wizard** folder.</span></span> <span data-ttu-id="958c4-106">Para usar al Asistente para certificados primero tendrá que cree mediante Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="958c4-106">To use the Certificate Wizard you will first have to build it using Visual Studio.</span></span>  
  
 <span data-ttu-id="958c4-107">CertWizard importa una clave privada de un archivo .pfx en el almacén personal e importa una clave pública de un archivo .cer en un almacén público.</span><span class="sxs-lookup"><span data-stu-id="958c4-107">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="958c4-108">Al importar una clave privada, el certificado puede ser un certificado de descifrado para mensajes entrantes o un certificado de firma para mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="958c4-108">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="958c4-109">**Descripción de la sintaxis**</span><span class="sxs-lookup"><span data-stu-id="958c4-109">**Syntax Description**</span></span>  
  
 <span data-ttu-id="958c4-110">La siguiente tabla describe las partes de la sintaxis que usa la utilidad CertWizard.</span><span class="sxs-lookup"><span data-stu-id="958c4-110">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="958c4-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="958c4-111">Syntax</span></span>|<span data-ttu-id="958c4-112">Description</span><span class="sxs-lookup"><span data-stu-id="958c4-112">Description</span></span>|  
|<span data-ttu-id="958c4-113">Privatekey</span><span class="sxs-lookup"><span data-stu-id="958c4-113">Privatekey</span></span>|<span data-ttu-id="958c4-114">Usada para importar una clave privada.</span><span class="sxs-lookup"><span data-stu-id="958c4-114">Used to import a private key.</span></span>|  
|<span data-ttu-id="958c4-115">Publickey</span><span class="sxs-lookup"><span data-stu-id="958c4-115">Publickey</span></span>|<span data-ttu-id="958c4-116">Usada para importar una clave pública.</span><span class="sxs-lookup"><span data-stu-id="958c4-116">Used to import a public key.</span></span>|  
|<span data-ttu-id="958c4-117">Rootkey</span><span class="sxs-lookup"><span data-stu-id="958c4-117">Rootkey</span></span>|<span data-ttu-id="958c4-118">Usada para importar una clave raíz (de una autoridad de certificación).</span><span class="sxs-lookup"><span data-stu-id="958c4-118">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="958c4-119">filename.pfx (o .cer)</span><span class="sxs-lookup"><span data-stu-id="958c4-119">filename.pfx (or .cer)</span></span>|<span data-ttu-id="958c4-120">Ruta completa del archivo .pfx (claves privadas) o .cer (claves públicas).</span><span class="sxs-lookup"><span data-stu-id="958c4-120">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="958c4-121">Filepassword</span><span class="sxs-lookup"><span data-stu-id="958c4-121">Filepassword</span></span>|<span data-ttu-id="958c4-122">Contraseña requerida para desbloquear el archivo .pxf.</span><span class="sxs-lookup"><span data-stu-id="958c4-122">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="958c4-123">Useridentity</span><span class="sxs-lookup"><span data-stu-id="958c4-123">Useridentity</span></span>|<span data-ttu-id="958c4-124">Identidad de servicio que utilizan uno o varios host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="958c4-124">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="958c4-125">Especifique una cuenta de usuario si no desea especificar el host pero desea importar un certificado en una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="958c4-125">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="958c4-126">**Nota:** si no se agrega el conmutador Useridentity, la utilidad importa y establecer el certificado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="958c4-126">**Note:**  If you do not add the Useridentity switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="958c4-127">**Nota:** si agrega el conmutador Useridentity, pero no especifica un valor, WMI genera automáticamente la identidad del usuario.</span><span class="sxs-lookup"><span data-stu-id="958c4-127">**Note:**  If you add the Useridentity switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="958c4-128">Contraseña</span><span class="sxs-lookup"><span data-stu-id="958c4-128">Password</span></span>|<span data-ttu-id="958c4-129">Contraseña del usuario de identidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="958c4-129">The password for the service identity user.</span></span>|  
|<span data-ttu-id="958c4-130">Thumbprint</span><span class="sxs-lookup"><span data-stu-id="958c4-130">Thumbprint</span></span>|<span data-ttu-id="958c4-131">La huella de un certificado específico, en caso de que el archivo contenga varios certificados.</span><span class="sxs-lookup"><span data-stu-id="958c4-131">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="958c4-132">**Nota:** para un archivo de certificado público, si el archivo contiene más de un certificado y no se especifica la huella digital, la utilidad importa todos los certificados en el archivo.</span><span class="sxs-lookup"><span data-stu-id="958c4-132">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="958c4-133">En el caso de un archivo de certificado privado, la utilidad solicita seleccionar el certificado que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="958c4-133">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="958c4-134">Uso</span><span class="sxs-lookup"><span data-stu-id="958c4-134">Usage</span></span>|<span data-ttu-id="958c4-135">Uso intencionado del certificado privado importado.</span><span class="sxs-lookup"><span data-stu-id="958c4-135">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="958c4-136">Puede ser uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="958c4-136">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="958c4-137">**inicio de sesión** (para un certificado de firma)</span><span class="sxs-lookup"><span data-stu-id="958c4-137">**sign** (for a signing certificate)</span></span><br /><br /> <span data-ttu-id="958c4-138">**descifrar** (para un certificado de descifrado)</span><span class="sxs-lookup"><span data-stu-id="958c4-138">**decrypt** (for a decryption certificate)</span></span><br /><br /> <span data-ttu-id="958c4-139">**ambos** (para un certificado que es un certificado de firma y un certificado de descifrado)</span><span class="sxs-lookup"><span data-stu-id="958c4-139">**both** (for a certificate that is both a signing certificate and a decryption certificate)</span></span><br /><br /> <span data-ttu-id="958c4-140">**Ninguno** (también para un certificado es un certificado de firma y un certificado de descifrado).</span><span class="sxs-lookup"><span data-stu-id="958c4-140">**none** (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="958c4-141">**Nota:** si el conmutador /Usage como se establece en none, el asistente no establecerá la huella digital del certificado en los Hosts de BizTalk o el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="958c4-141">**Note:**  If you set the /Usage switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="958c4-142">Exportable</span><span class="sxs-lookup"><span data-stu-id="958c4-142">Exportable</span></span>|<span data-ttu-id="958c4-143">Puede ser **True** o **False**.</span><span class="sxs-lookup"><span data-stu-id="958c4-143">Can be **True** or **False**.</span></span> <span data-ttu-id="958c4-144">Si **True**, puede volver a exportar la clave privada.</span><span class="sxs-lookup"><span data-stu-id="958c4-144">If **True**, the private key can be re-exported.</span></span>|  
  
 <span data-ttu-id="958c4-145">**Sintaxis para importar una clave privada**</span><span class="sxs-lookup"><span data-stu-id="958c4-145">**Syntax for Importing a Private Key**</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
 <span data-ttu-id="958c4-146">**Sintaxis para importar una clave pública**</span><span class="sxs-lookup"><span data-stu-id="958c4-146">**Syntax for Importing a Public Key**</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
 <span data-ttu-id="958c4-147">**Sintaxis para importar una clave raíz**</span><span class="sxs-lookup"><span data-stu-id="958c4-147">**Syntax for Importing a Root Key**</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
## <a name="prerequisites"></a><span data-ttu-id="958c4-148">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="958c4-148">Prerequisites</span></span>  
 <span data-ttu-id="958c4-149">A continuación, se enumeran los requisitos previos para efectuar los procedimientos de este tema:</span><span class="sxs-lookup"><span data-stu-id="958c4-149">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="958c4-150">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="958c4-150">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-run-the-certificate-wizard"></a><span data-ttu-id="958c4-151">Para ejecutar el Asistente para certificados</span><span class="sxs-lookup"><span data-stu-id="958c4-151">To run the certificate wizard</span></span>  
  
1.  <span data-ttu-id="958c4-152">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="958c4-152">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="958c4-153">Vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities.</span><span class="sxs-lookup"><span data-stu-id="958c4-153">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities.</span></span>  
  
3.  <span data-ttu-id="958c4-154">En el símbolo del sistema, escriba **CertWizard**, escriba los conmutadores requeridos y correspondientes y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="958c4-154">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="958c4-155">Si no proporciona el comando completo en el símbolo del sistema, CertWizard le solicitará que proporcione los valores requeridos.</span><span class="sxs-lookup"><span data-stu-id="958c4-155">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="958c4-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="958c4-156">See Also</span></span>  
 [<span data-ttu-id="958c4-157">Utilidades del SDK</span><span class="sxs-lookup"><span data-stu-id="958c4-157">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)