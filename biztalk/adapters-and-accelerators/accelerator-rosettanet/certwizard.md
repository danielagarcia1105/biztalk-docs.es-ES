---
title: CertWizard | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, CertWizard utility
- CertWizard utility
- certificates, importing
ms.assetid: beeab3c0-d7b1-4bb9-8b19-f79b049d5aa1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ec4cebd4172ce8f95cb4add2af084ab026d295
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992381"
---
# <a name="certwizard"></a><span data-ttu-id="ed54d-102">CertWizard</span><span class="sxs-lookup"><span data-stu-id="ed54d-102">CertWizard</span></span>
<span data-ttu-id="ed54d-103">Use la utilidad CertWizard para importar un certificado desde un archivo .pfx o .cer en un almacén privado o público para su uso con Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed54d-103">You use the CertWizard utility to import a certificate from a .pfx or .cer file into a private or public store for use with Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="ed54d-104">Ubicación en SDK</span><span class="sxs-lookup"><span data-stu-id="ed54d-104">Location in SDK</span></span>  
 <span data-ttu-id="ed54d-105">\<*unidad*\>archivos \Program (x86)\\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\\</span><span class="sxs-lookup"><span data-stu-id="ed54d-105">\<*drive*\>\Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\\</span></span>  
  
## <a name="running-certwizard"></a><span data-ttu-id="ed54d-106">Ejecutando CertWizard</span><span class="sxs-lookup"><span data-stu-id="ed54d-106">Running CertWizard</span></span>  
  
#### <a name="to-run-certwizard"></a><span data-ttu-id="ed54d-107">Para ejecutar CertWizard</span><span class="sxs-lookup"><span data-stu-id="ed54d-107">To run CertWizard</span></span>  
  
1. <span data-ttu-id="ed54d-108">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="ed54d-108">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="ed54d-109">Mover a \< *unidad*\>\ archivos de programa (x86)\\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\\.</span><span class="sxs-lookup"><span data-stu-id="ed54d-109">Move to \<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
3. <span data-ttu-id="ed54d-110">En el símbolo del sistema, escriba **CertWizard**, escriba los conmutadores requeridos y correspondientes y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ed54d-110">At the command prompt, type **CertWizard**, type the required and appropriate switches, and then press ENTER.</span></span>  
  
## <a name="syntax-for-certwizard"></a><span data-ttu-id="ed54d-111">Sintaxis de CertWizard</span><span class="sxs-lookup"><span data-stu-id="ed54d-111">Syntax for CertWizard</span></span>  
 <span data-ttu-id="ed54d-112">A continuación se muestra la sintaxis que se utiliza para iniciar esta utilidad de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="ed54d-112">The following shows the syntax that you use to start this command-line utility:</span></span>  
  
### <a name="syntax-for-importing-a-private-key"></a><span data-ttu-id="ed54d-113">Sintaxis para importar una clave privada</span><span class="sxs-lookup"><span data-stu-id="ed54d-113">Syntax for Importing a Private Key</span></span>  
  
```  
CertWizard /Privatekey <filename>.pfx [/Filepassword <filepassword>] [/Useridentity <useridentity>] [/Password <password>] [/Thumbprint <thumbprint>] [/Usage sign|decrypt|both|none] [/Exportable true|false]  
```  
  
### <a name="syntax-for-importing-a-public-key"></a><span data-ttu-id="ed54d-114">Sintaxis para importar una clave pública</span><span class="sxs-lookup"><span data-stu-id="ed54d-114">Syntax for Importing a Public Key</span></span>  
  
```  
CertWizard /Publickey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-for-importing-a-root-key"></a><span data-ttu-id="ed54d-115">Sintaxis para importar una clave raíz</span><span class="sxs-lookup"><span data-stu-id="ed54d-115">Syntax for Importing a Root Key</span></span>  
  
```  
CertWizard /Rootkey <filename>.cer [/Thumbprint <thumbprint>]  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="ed54d-116">Descripción de la sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed54d-116">Syntax Description</span></span>  
 <span data-ttu-id="ed54d-117">La siguiente tabla describe las partes de la sintaxis que usa la utilidad CertWizard.</span><span class="sxs-lookup"><span data-stu-id="ed54d-117">The following table describes each part of the syntax that the CertWizard utility uses.</span></span>  
  
|<span data-ttu-id="ed54d-118">**Sintaxis**</span><span class="sxs-lookup"><span data-stu-id="ed54d-118">**Syntax**</span></span>|<span data-ttu-id="ed54d-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ed54d-119">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="ed54d-120">**PrivateKey**</span><span class="sxs-lookup"><span data-stu-id="ed54d-120">**Privatekey**</span></span>|<span data-ttu-id="ed54d-121">Usada para importar una clave privada.</span><span class="sxs-lookup"><span data-stu-id="ed54d-121">Used to import a private key.</span></span>|  
|<span data-ttu-id="ed54d-122">**Clave pública**</span><span class="sxs-lookup"><span data-stu-id="ed54d-122">**Publickey**</span></span>|<span data-ttu-id="ed54d-123">Usada para importar una clave pública.</span><span class="sxs-lookup"><span data-stu-id="ed54d-123">Used to import a public key.</span></span>|  
|<span data-ttu-id="ed54d-124">**ROOTKEY**</span><span class="sxs-lookup"><span data-stu-id="ed54d-124">**Rootkey**</span></span>|<span data-ttu-id="ed54d-125">Usada para importar una clave raíz (de una autoridad de certificación).</span><span class="sxs-lookup"><span data-stu-id="ed54d-125">Used to import a root key—from a certification authority.</span></span>|  
|<span data-ttu-id="ed54d-126">**FileName.pfx (o .cer)**</span><span class="sxs-lookup"><span data-stu-id="ed54d-126">**filename.pfx (or .cer)**</span></span>|<span data-ttu-id="ed54d-127">Ruta completa del archivo .pfx (claves privadas) o .cer (claves públicas).</span><span class="sxs-lookup"><span data-stu-id="ed54d-127">Full path for the .pfx (private keys) or .cer (public keys) file.</span></span>|  
|<span data-ttu-id="ed54d-128">**Filepassword**</span><span class="sxs-lookup"><span data-stu-id="ed54d-128">**Filepassword**</span></span>|<span data-ttu-id="ed54d-129">Contraseña requerida para desbloquear el archivo .pxf.</span><span class="sxs-lookup"><span data-stu-id="ed54d-129">The password required to unlock the .pfx file.</span></span>|  
|<span data-ttu-id="ed54d-130">**Identidad de usuario**</span><span class="sxs-lookup"><span data-stu-id="ed54d-130">**Useridentity**</span></span>|<span data-ttu-id="ed54d-131">Identidad de servicio que utilizan uno o varios host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ed54d-131">A service identity that one or more BizTalk Hosts uses.</span></span> <span data-ttu-id="ed54d-132">Especifique una cuenta de usuario si no desea especificar el host pero desea importar un certificado en una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="ed54d-132">Enter a user account if you do not want to specify the host, but want to import a certificate under a user account.</span></span> <span data-ttu-id="ed54d-133">**Nota:** si no se agrega el **Useridentity** cambia, las importaciones de utilidad y establecer el certificado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ed54d-133">**Note:**  If you do not add the **Useridentity** switch, the utility imports and set the certificate for all users.</span></span> <span data-ttu-id="ed54d-134">**Nota:** si agrega el **Useridentity** cambiar, pero no especifica un valor, WMI genera automáticamente la identidad del usuario.</span><span class="sxs-lookup"><span data-stu-id="ed54d-134">**Note:**  If you add the **Useridentity** switch, but do not enter a value, WMI automatically generates the user identity.</span></span>|  
|<span data-ttu-id="ed54d-135">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="ed54d-135">**Password**</span></span>|<span data-ttu-id="ed54d-136">Contraseña del usuario de identidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="ed54d-136">The password for the service identity user.</span></span>|  
|<span data-ttu-id="ed54d-137">**Huella digital**</span><span class="sxs-lookup"><span data-stu-id="ed54d-137">**Thumbprint**</span></span>|<span data-ttu-id="ed54d-138">La huella de un certificado específico, en caso de que el archivo contenga varios certificados.</span><span class="sxs-lookup"><span data-stu-id="ed54d-138">The thumbprint of a specific certificate, in case the file contains more than one certificate.</span></span> <span data-ttu-id="ed54d-139">**Nota:** para un archivo de certificado público, si el archivo contiene más de un certificado y no se especifica la huella digital, la utilidad importa todos los certificados en el archivo.</span><span class="sxs-lookup"><span data-stu-id="ed54d-139">**Note:**  For a public certificate file, if the file contains more than one certificate and you do not specify the thumbprint, the utility imports all certificates in the file.</span></span> <span data-ttu-id="ed54d-140">En el caso de un archivo de certificado privado, la utilidad solicita seleccionar el certificado que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="ed54d-140">For a private certificate file, the utility prompts you to select the certificate to import.</span></span>|  
|<span data-ttu-id="ed54d-141">**Usage**</span><span class="sxs-lookup"><span data-stu-id="ed54d-141">**Usage**</span></span>|<span data-ttu-id="ed54d-142">Uso intencionado del certificado privado importado.</span><span class="sxs-lookup"><span data-stu-id="ed54d-142">The intended usage of the imported private certificate.</span></span> <span data-ttu-id="ed54d-143">Puede ser el inicio de sesión (para un certificado de firma), descifrar (para un certificado de descifrado), ambos (para un certificado que es un certificado de firma y un certificado de descifrado) o ninguno (también un certificado que es un certificado de firma y un certificado de descifrado ).</span><span class="sxs-lookup"><span data-stu-id="ed54d-143">Can be sign (for a signing certificate), decrypt (for a decryption certificate), both (for a certificate that is both a signing certificate and a decryption certificate), or none (also for a certificate that is both a signing certificate and a decryption certificate).</span></span> <span data-ttu-id="ed54d-144">**Nota:** si establece la **/Usage como** conmutador en none, el asistente no establecerá la huella digital del certificado en los Hosts de BizTalk o el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ed54d-144">**Note:**  If you set the **/Usage** switch to none, the wizard will not set the thumbprint for the certificate on the BizTalk Hosts or the BizTalk Group.</span></span>|  
|<span data-ttu-id="ed54d-145">**Exportable**</span><span class="sxs-lookup"><span data-stu-id="ed54d-145">**Exportable**</span></span>|<span data-ttu-id="ed54d-146">Puede ser `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="ed54d-146">Can be `True` or `False`.</span></span> <span data-ttu-id="ed54d-147">Si `True`, se puede volver a exportar la clave privada.</span><span class="sxs-lookup"><span data-stu-id="ed54d-147">If `True`, the private key can be re-exported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed54d-148">Notas</span><span class="sxs-lookup"><span data-stu-id="ed54d-148">Remarks</span></span>  
 <span data-ttu-id="ed54d-149">CertWizard importa una clave privada de un archivo .pfx en el almacén personal e importa una clave pública de un archivo .cer en un almacén público.</span><span class="sxs-lookup"><span data-stu-id="ed54d-149">CertWizard imports a private key from a .pfx file into the personal store, and imports a public key from a .cer file into a public store.</span></span> <span data-ttu-id="ed54d-150">Al importar una clave privada, el certificado puede ser un certificado de descifrado para mensajes entrantes o un certificado de firma para mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="ed54d-150">When importing a private key, the certificate can be a decryption certificate for incoming messages or a signing certificate for outgoing messages.</span></span>  
  
 <span data-ttu-id="ed54d-151">Si no proporciona el comando completo en el símbolo del sistema, CertWizard le solicitará que proporcione los valores requeridos.</span><span class="sxs-lookup"><span data-stu-id="ed54d-151">If you do not give the full command at the command prompt, CertWizard will prompt you to provide the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed54d-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed54d-152">See Also</span></span>  
 <span data-ttu-id="ed54d-153">[Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="ed54d-153">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="ed54d-154">Importación de certificados mediante la utilidad CertWizard</span><span class="sxs-lookup"><span data-stu-id="ed54d-154">Importing Certificates Using the CertWizard Utility</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)
