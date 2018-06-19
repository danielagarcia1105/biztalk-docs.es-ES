---
title: 'Paso 3: Importar Public y Private certificados | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public certificates
- importing certificates
- private certificates
- double action tutorial, importing certificates
- certificates, importing
ms.assetid: 955bdd69-9fbc-4100-ab8a-8f5dd4a17cbb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46d087c44cac350df2d58c880303668b5c3e0c24
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966954"
---
# <a name="step-3-importing-public-and-private-certificates"></a><span data-ttu-id="1ba22-102">Paso 3: Importar Public y Private certificados</span><span class="sxs-lookup"><span data-stu-id="1ba22-102">Step 3: Importing Public and Private Certificates</span></span>
<span data-ttu-id="1ba22-103">En este paso, importar los certificados se crean en [paso 2: crear pública y privada certificados &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) a los equipos de Contoso y Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="1ba22-103">In this step, you import the certificates you created in [Step 2: Creating Public and Private Certificates &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) to the Contoso and Fabrikam computers.</span></span> <span data-ttu-id="1ba22-104">Cada equipo importa sus propios certificados privadas e importa los certificados públicos de la otra organización.</span><span class="sxs-lookup"><span data-stu-id="1ba22-104">Each computer imports its own private certificates and imports the public certificates of the other organization.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ba22-105">Tendrá que transferir los certificados privados de Fabrikam y Contoso públicos certificados en el equipo de Fabrikam para importarlos.</span><span class="sxs-lookup"><span data-stu-id="1ba22-105">You have to transfer the Fabrikam private certificates and Contoso public certificates to the Fabrikam computer to import them.</span></span> <span data-ttu-id="1ba22-106">Este paso se asume que estos certificados se coloquen en la carpeta C:\Certs en el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="1ba22-106">This step assumes that you put these certificates in the C:\Certs folder on the Fabrikam computer.</span></span>  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a><span data-ttu-id="1ba22-107">Para importar los certificados privados de Contoso en el equipo de Contoso</span><span class="sxs-lookup"><span data-stu-id="1ba22-107">To import the Contoso private certificates on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="1ba22-108">En el equipo de Contoso, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-108">On the Contoso computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="1ba22-109">En el símbolo del sistema, vaya a  **\<**  *unidad***\>: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-109">At the command prompt, move to **\<***drive***\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="1ba22-110">En el símbolo del sistema, escriba **CertWizard /Privatekey "\<***unidad***\>: \Certs\Contoso Encryption.pfx privada"** y, a continuación, presione **Escriba**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-110">At the command prompt, type **CertWizard /Privatekey "\<***drive***\>:\Certs\Contoso Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="1ba22-111">En el **escriba la contraseña para el archivo de certificado** escriba **mysecret**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-111">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="1ba22-112">En el **escriba una contraseña para la identidad < contoso_machine > \HostSvc** símbolo del sistema, escriba la contraseña de la cuenta de HostSvc y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-112">At the **Enter password for identity <contoso_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ba22-113">Si su BizTalkServerApplication se ejecuta con un nombre de cuenta que no sea HostSvc, el símbolo del sistema debe ser diferente.</span><span class="sxs-lookup"><span data-stu-id="1ba22-113">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
6.  <span data-ttu-id="1ba22-114">En el **este certificado principal se usará para** escriba **d.** y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-114">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="1ba22-115">El CertWizard importa el certificado en el almacén de \Personal\Certificates para las cuentas de usuario que se ejecutan los hosts AplicaciónBizTalkServer y BizTalkServerIsolatedHost en.</span><span class="sxs-lookup"><span data-stu-id="1ba22-115">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
7.  <span data-ttu-id="1ba22-116">Repita los pasos 3 a 6 para el certificado privado de Contoso Signature.pfx que especifica que es un certificado de firma escribiendo **S** en el **este certificado principal se usará para** símbolo del sistema que anotó en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="1ba22-116">Repeat steps 3-6 for the Contoso Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt noted in step 6.</span></span>  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a><span data-ttu-id="1ba22-117">Para importar los certificados públicos de Fabrikam en el equipo de Contoso</span><span class="sxs-lookup"><span data-stu-id="1ba22-117">To import the Fabrikam public certificates on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="1ba22-118">En el equipo de Contoso, haga clic en **iniciar**, haga clic en **ejecutar,** tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-118">On the Contoso computer, click **Start**, click **Run,** type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="1ba22-119">En el símbolo del sistema, vaya a  *\<unidad\>***: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-119">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="1ba22-120">En el símbolo del sistema, escriba **/PublicKey CertWizard "***\<unidad\>***: \Certs\Fabrikam Encryption.cer pública"** y, a continuación, presione  **Escriba**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-120">At the command prompt, type **CertWizard /Publickey "***\<drive\>***:\Certs\Fabrikam Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="1ba22-121">Repita el paso 3 para el certificado público Signature.cer de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="1ba22-121">Repeat step 3 for the Fabrikam Public Signature.cer certificate.</span></span>  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="1ba22-122">Para importar los certificados privados de Fabrikam en el equipo de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="1ba22-122">To import the Fabrikam private certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="1ba22-123">Copie los siguientes archivos desde el equipo de Contoso a la \<unidad\>: \Certs carpeta en el equipo de Fabrikam: Encryption.cer públicas de Contoso, Signature.cer públicas de Contoso, Fabrikam privada Encryption.pfx y privados de Fabrikam Signature.pfx.</span><span class="sxs-lookup"><span data-stu-id="1ba22-123">Copy the following files from the Contoso computer to the \<drive\>:\Certs folder on the Fabrikam computer: Contoso Public Encryption.cer, Contoso Public Signature.cer, Fabrikam Private Encryption.pfx, and Fabrikam Private Signature.pfx.</span></span>  
  
2.  <span data-ttu-id="1ba22-124">En el equipo Fabrikum, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-124">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1ba22-125">En el símbolo del sistema, vaya a  *\<unidad\>***: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-125">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="1ba22-126">En el símbolo del sistema, escriba **CertWizard /Privatekey "***\<unidad\>***: \Certs\Fabrikam Encryption.pfx privada"** y, a continuación, presione **Escriba**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-126">At the command prompt, type **CertWizard /Privatekey "***\<drive\>***:\Certs\Fabrikam Private Encryption.pfx"**, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="1ba22-127">En el **escriba la contraseña para el archivo de certificado** escriba **mysecret**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-127">At the **Please enter the password for the certificate file** prompt, type **mysecret**, and then press **Enter**.</span></span>  
  
6.  <span data-ttu-id="1ba22-128">En el **escriba una contraseña para la identidad < fabrikam_machine > \HostSvc** símbolo del sistema, escriba la contraseña de la cuenta de HostSvc y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-128">At the **Enter password for identity <fabrikam_machine>\HostSvc** prompt, type the HostSvc account password, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ba22-129">Si su BizTalkServerApplication se ejecuta con un nombre de cuenta que no sea HostSvc, el símbolo del sistema debe ser diferente.</span><span class="sxs-lookup"><span data-stu-id="1ba22-129">If your BizTalkServerApplication runs under an account name other than HostSvc, the prompt must be different.</span></span>  
  
7.  <span data-ttu-id="1ba22-130">En el **este certificado principal se usará para** escriba **d.** y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-130">At the **This home certificate will be used for** prompt, type **D**, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="1ba22-131">El CertWizard importa el certificado en el almacén de \Personal\Certificates para las cuentas de usuario que se ejecutan los hosts AplicaciónBizTalkServer y BizTalkServerIsolatedHost en.</span><span class="sxs-lookup"><span data-stu-id="1ba22-131">The CertWizard imports the certificate into the \Personal\Certificates store for the user accounts that BizTalkServerApplication and BizTalkServerIsolatedHost hosts run under.</span></span>  
  
8.  <span data-ttu-id="1ba22-132">Repita los pasos del 4 al 7 para el certificado de Fabrikam privada Signature.pfx para especificar que es un certificado de firma escribiendo **S** en el **este certificado principal se usará para** símbolo del sistema en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="1ba22-132">Repeat steps 4-7 for the Fabrikam Private Signature.pfx certificate specifying that it is a signature certificate by typing **S** at the **This home certificate will be used for** prompt in step 6.</span></span>  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a><span data-ttu-id="1ba22-133">Para importar los certificados públicos de Contoso en el equipo de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="1ba22-133">To import the Contoso public certificates on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="1ba22-134">En el equipo Fabrikum, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-134">On the Fabrikum computer, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="1ba22-135">En el símbolo del sistema, vaya a  *\<unidad\>***: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-135">At the command prompt, move to *\<drive\>***:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK** and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="1ba22-136">En el símbolo del sistema, escriba **/PublicKey CertWizard "***\<unidad\>***: \Certs\Contoso Encryption.cer pública"** y, a continuación, presione  **Escriba**.</span><span class="sxs-lookup"><span data-stu-id="1ba22-136">At the command prompt, type **CertWizard /Publickey "***\<drive\>***:\Certs\Contoso Public Encryption.cer"**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="1ba22-137">Repita el paso 3 para el certificado público Signature.cer de Contoso.</span><span class="sxs-lookup"><span data-stu-id="1ba22-137">Repeat step 3 for the Contoso Public Signature.cer certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba22-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ba22-138">See Also</span></span>  
 [<span data-ttu-id="1ba22-139">Paso 4: Habilitar Capa de sockets seguros en IIS</span><span class="sxs-lookup"><span data-stu-id="1ba22-139">Step 4: Enabling Secure Sockets Layer in IIS</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)