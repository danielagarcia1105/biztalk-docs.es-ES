---
title: Importación de certificados mediante la utilidad CertWizard | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, root keys
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- CertWizard utility
- certificates, importing
- root keys
ms.assetid: 0c54d7ab-69cf-4f4a-b976-6f740a41280b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64be28927a49a1fc751870785ff3fc3f55a36cb1
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "26006845"
---
# <a name="importing-certificates-using-the-certwizard-utility"></a><span data-ttu-id="ff606-102">Importación de certificados mediante la utilidad CertWizard</span><span class="sxs-lookup"><span data-stu-id="ff606-102">Importing Certificates Using the CertWizard Utility</span></span>
<span data-ttu-id="ff606-103">Este tema describe cómo importar un certificado mediante la utilidad CertWizard, una utilidad de línea de comandos paso a paso disponible en la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="ff606-103">This topic describes how to import a certificate by using CertWizard utility, a step-by-step command-line utility available in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="ff606-104">Este tema describe la importación de una privada, pública o clave raíz.</span><span class="sxs-lookup"><span data-stu-id="ff606-104">This topic discusses importing a private, public, or root key.</span></span> <span data-ttu-id="ff606-105">Describe los modificadores que utilizan para configurar el certificado.</span><span class="sxs-lookup"><span data-stu-id="ff606-105">It describes the switches that you use to configure the certificate.</span></span>  
  
 <span data-ttu-id="ff606-106">La utilidad CertWizard automatiza muchos de los pasos que tendría que realizar manualmente mediante la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="ff606-106">The CertWizard utility automates many of the steps that you would have to do manually by using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span></span> <span data-ttu-id="ff606-107">La utilidad CertWizard realiza el **runas** comando para abrir MMC como la cuenta de servicio de host.</span><span class="sxs-lookup"><span data-stu-id="ff606-107">The CertWizard utility performs the **runas** command to open MMC as the host service account.</span></span> <span data-ttu-id="ff606-108">Si no se agrega un **Useridentity** conmutador, detectará y usar la cuenta de servicio de host, solicite una contraseña.</span><span class="sxs-lookup"><span data-stu-id="ff606-108">If you do not add a **Useridentity** switch, it will detect and use the host service account, prompting you for a password.</span></span> <span data-ttu-id="ff606-109">Almacena y configura el certificado.</span><span class="sxs-lookup"><span data-stu-id="ff606-109">It stores and configures the certificate.</span></span>  
  
 <span data-ttu-id="ff606-110">Puede importar varios certificados a la vez mediante la creación de un archivo por lotes con varios comandos de la utilidad CertWizard.</span><span class="sxs-lookup"><span data-stu-id="ff606-110">You can import multiple certificates at the same time by creating a batch file with multiple CertWizard utility commands.</span></span>  
  
### <a name="to-import-a-private-key"></a><span data-ttu-id="ff606-111">Para importar una clave privada</span><span class="sxs-lookup"><span data-stu-id="ff606-111">To import a private key</span></span>  
  
1.  <span data-ttu-id="ff606-112">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff606-112">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="ff606-113">En el símbolo del sistema, vaya a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] carpeta del SDK con MS-DOS **CD** comando, por ejemplo, escriba **cd C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK** .</span><span class="sxs-lookup"><span data-stu-id="ff606-113">At the command prompt, move to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK folder using the MS-DOS **CD** command, for example, type **cd C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** .</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff606-114">¿Para obtener ayuda con la utilidad CertWizard, escriba **CertWizard /?**</span><span class="sxs-lookup"><span data-stu-id="ff606-114">For help with the CertWizard utility, type **CertWizard /?**</span></span> <span data-ttu-id="ff606-115">en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="ff606-115">at the command prompt.</span></span>  
  
3.  <span data-ttu-id="ff606-116">En el símbolo del sistema, escriba **CertWizard /Privatekey \<filename\>.pfx**, donde \< *filename*\>.pfx contiene el certificado privado.</span><span class="sxs-lookup"><span data-stu-id="ff606-116">At the command prompt, type **CertWizard /Privatekey \<filename\>.pfx**, where \<*filename*\>.pfx contains the private certificate.</span></span> <span data-ttu-id="ff606-117">Para proporcionar la contraseña para el archivo, anexar **/Filepassword \<filepassword\>**  al comando.</span><span class="sxs-lookup"><span data-stu-id="ff606-117">To provide the password for the file, append **/Filepassword \<filepassword\>** to the command.</span></span>  
  
4.  <span data-ttu-id="ff606-118">Si desea importar el certificado a una cuenta específica utilizada por el BizTalk Host, se anexa **/Useridentity \<useridentity\> /Password \<contraseña\>**  al comando.</span><span class="sxs-lookup"><span data-stu-id="ff606-118">If you want to import the certificate into a specific account used by the BizTalk Host, append **/Useridentity \<useridentity\> /Password \<password\>** to the command.</span></span>  
  
5.  <span data-ttu-id="ff606-119">Si desea designar una huella digital específica en caso de que el archivo .pfx contiene más de un certificado, se anexa **/Thumbprint \<huella digital\>**  al comando.</span><span class="sxs-lookup"><span data-stu-id="ff606-119">If you want to designate a specific thumbprint in case the .pfx file contains more than one certificate, append **/Thumbprint \<thumbprint\>** to the command.</span></span>  
  
6.  <span data-ttu-id="ff606-120">Si desea configurar el uso del certificado, anexe **/Usage como** para el comando y, a continuación, anexe uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff606-120">If you want to configure the usage of the certificate, append **/Usage** to the command, and then append one of the following values:</span></span>  
  
    -   <span data-ttu-id="ff606-121">Anexar **inicio de sesión** para agregar la huella digital del certificado como certificado de firma para el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ff606-121">Append **sign** to add the certificate's thumbprint as the signing certificate for the BizTalk Group.</span></span> <span data-ttu-id="ff606-122">como está establecido en el cuadro de diálogo para Microsoft BizTalk Server (Local) en la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ff606-122">as set on the dialog box for Microsoft BizTalk Server (Local) in the BizTalk Administration Console.</span></span>  
  
    -   <span data-ttu-id="ff606-123">Anexar **descifrar** para agregar la huella digital del certificado como el certificado de descifrado para los Hosts de BizTalk, como está establecido en la ficha certificado de las páginas de propiedades para cada host de la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ff606-123">Append **decrypt** to add the certificate's thumbprint as the decryption certificate for the BizTalk Hosts, as set on the certificate tab of the property pages for each host in the BizTalk Administration Console.</span></span>  
  
    -   <span data-ttu-id="ff606-124">Anexar **ambos** para agregar el certificado de huella digital para ambos el grupo BizTalk de firma de certificado y el certificado de descifrado del BizTalk Host.</span><span class="sxs-lookup"><span data-stu-id="ff606-124">Append **both** to add the certificate's thumbprint for both the BizTalk Group's signing certificate and the BizTalk Host's decryption certificate.</span></span>  
  
    -   <span data-ttu-id="ff606-125">Anexar **ninguno** cuando no desea establecer la configuración para el grupo de BizTalk o los Hosts de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ff606-125">Append **none** when you do not want to set the configuration for the BizTalk Group or the BizTalk Hosts.</span></span>  
  
7.  <span data-ttu-id="ff606-126">Si desea configurar el certificado como exportable, anexe **/Exportable true**.</span><span class="sxs-lookup"><span data-stu-id="ff606-126">If you want to configure the certificate as exportable, append **/Exportable true**.</span></span> <span data-ttu-id="ff606-127">Para establecer el certificado como no exportable, anexar **/Exportable false**, que es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ff606-127">To set the certificate as non-exportable, append **/Exportable false**, which is the default behavior.</span></span>  
  
8.  <span data-ttu-id="ff606-128">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="ff606-128">Press **Enter**.</span></span>  
  
9. <span data-ttu-id="ff606-129">Si no escribió una de las contraseñas necesarias en el comando, la herramienta le avisará para él.</span><span class="sxs-lookup"><span data-stu-id="ff606-129">If you did not type one of the passwords required in the command, the tool prompts you for it.</span></span> <span data-ttu-id="ff606-130">Escriba la contraseña y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="ff606-130">Type the password, and then press **Enter**.</span></span>  
  
10. <span data-ttu-id="ff606-131">Si el archivo contiene varios certificados, pero no escribió una huella digital en el comando, la herramienta muestra las huellas digitales disponibles y le pide que seleccione uno.</span><span class="sxs-lookup"><span data-stu-id="ff606-131">If the file contains multiple certificates, but you did not type a thumbprint in the command, the tool displays the available thumbprints, and prompts you to select one.</span></span> <span data-ttu-id="ff606-132">Escriba el número de la huella digital que desee y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="ff606-132">Type the number of the thumbprint that you want, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="ff606-133">La herramienta importa el certificado en el almacén de \Personal\Certificates para el usuario especificado en el **/useridentity** cambiar.</span><span class="sxs-lookup"><span data-stu-id="ff606-133">The tool imports the certificate into the \Personal\Certificates store for the user specified in the **/useridentity** switch.</span></span> <span data-ttu-id="ff606-134">Si no especifica un usuario, el usuario predeterminado es la identidad del usuario para los hosts de BizTalkServerApplication y BizTalkServerIsolatedHost.</span><span class="sxs-lookup"><span data-stu-id="ff606-134">If you do not specify a user, the default user is the user identity for the BizTalkServerApplication and BizTalkServerIsolatedHost hosts.</span></span>  
  
### <a name="to-import-a-public-key"></a><span data-ttu-id="ff606-135">Para importar una clave pública</span><span class="sxs-lookup"><span data-stu-id="ff606-135">To import a public key</span></span>  
  
1.  <span data-ttu-id="ff606-136">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff606-136">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="ff606-137">En el símbolo del sistema, vaya a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] carpeta del SDK mediante el uso de MS-DOS **CD** comando, por ejemplo, escriba **cd C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK**.</span><span class="sxs-lookup"><span data-stu-id="ff606-137">At the command prompt, move to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK folder by using the MS-DOS **CD** command, for example, type **cd C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK**.</span></span>  
  
3.  <span data-ttu-id="ff606-138">En el símbolo del sistema, escriba **/PublicKey CertWizard \<filename\>.cer**, donde \< *filename*\>.cer contiene el certificado público.</span><span class="sxs-lookup"><span data-stu-id="ff606-138">At the command prompt, type **CertWizard /Publickey \<filename\>.cer**, where \<*filename*\>.cer contains the public certificate.</span></span>  
  
4.  <span data-ttu-id="ff606-139">Si desea designar una huella digital del certificado en el archivo .cer o .der, anexe **/Thumbprint \<huella digital\>**  al comando.</span><span class="sxs-lookup"><span data-stu-id="ff606-139">If you want to designate a thumbprint for the certificate in the .cer or .der file, append **/Thumbprint \<thumbprint\>** to the command.</span></span>  
  
     <span data-ttu-id="ff606-140">La herramienta importa el certificado en el almacén de certificados (equipo Local) \Other People\Certificates y establece su configuración.</span><span class="sxs-lookup"><span data-stu-id="ff606-140">The tool imports the certificate into the Certificates (Local Computer)\Other People\Certificates store, and sets its configuration.</span></span>  
  
### <a name="to-import-a-root-key"></a><span data-ttu-id="ff606-141">Para importar una clave raíz</span><span class="sxs-lookup"><span data-stu-id="ff606-141">To import a root key</span></span>  
  
1.  <span data-ttu-id="ff606-142">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff606-142">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="ff606-143">En el símbolo del sistema, vaya a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] carpeta del SDK mediante el uso de MS-DOS **CD** comando, por ejemplo, escriba **cd C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK**.</span><span class="sxs-lookup"><span data-stu-id="ff606-143">At the command prompt, move to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK folder by using the MS-DOS **CD** command, for example, type **cd C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK**.</span></span>  
  
3.  <span data-ttu-id="ff606-144">En el símbolo del sistema, escriba **CertWizard /Rootkey \<filename\>.cer**, donde \< *filename*\>.cer contiene el certificado raíz.</span><span class="sxs-lookup"><span data-stu-id="ff606-144">At the command prompt, type **CertWizard /Rootkey \<filename\>.cer**, where \<*filename*\>.cer contains the root certificate.</span></span>  
  
4.  <span data-ttu-id="ff606-145">Si desea designar una huella digital del certificado en el archivo .cer o .der, anexe **/Thumbprint \<huella digital\>**  al comando.</span><span class="sxs-lookup"><span data-stu-id="ff606-145">If you want to designate a thumbprint for the certificate in the .cer or .der file, append **/Thumbprint \<thumbprint\>** to the command.</span></span>  
  
     <span data-ttu-id="ff606-146">La herramienta importa el certificado en el almacén de certificados (equipo Local) \Trusted Root Certification Authority\Certificates y establece su configuración.</span><span class="sxs-lookup"><span data-stu-id="ff606-146">The tool imports the certificate into the Certificates (Local Computer)\Trusted Root Certification Authority\Certificates store, and sets its configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff606-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff606-147">See Also</span></span>  
 <span data-ttu-id="ff606-148">[CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md) </span><span class="sxs-lookup"><span data-stu-id="ff606-148">[CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md) </span></span>  
 [<span data-ttu-id="ff606-149">Administración de certificados</span><span class="sxs-lookup"><span data-stu-id="ff606-149">Managing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)