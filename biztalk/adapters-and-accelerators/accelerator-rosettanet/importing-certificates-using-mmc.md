---
title: "Importación de certificados mediante MMC | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- certificates, importing
ms.assetid: 58fb1711-e295-4aa6-902e-e28e4a2cd921
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6030b711e0fd48d2632ff84428e1cb9ffc6e0402
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importing-certificates-using-mmc"></a><span data-ttu-id="96b7e-102">Importación de certificados mediante MMC</span><span class="sxs-lookup"><span data-stu-id="96b7e-102">Importing Certificates Using MMC</span></span>
<span data-ttu-id="96b7e-103">Este tema describe cómo importar un digital de certificado que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] utiliza para autenticar a un socio comercial, descifrar un mensaje entrante, o cifrar o firmar un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="96b7e-103">This topic describes how to import a digital certificate that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses to authenticate a trading partner, decrypt an incoming message, or encrypt or sign an outgoing message.</span></span>  
  
 <span data-ttu-id="96b7e-104">Este procedimiento utiliza el complemento de certificados para el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="96b7e-104">This procedure uses the Certificates snap-in for the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span></span> <span data-ttu-id="96b7e-105">Este proceso manual importa un certificado en el almacén de certificados, que sea necesario configurar el uso de certificados por separado.</span><span class="sxs-lookup"><span data-stu-id="96b7e-105">This manual process imports a certificate into the certificate store, requiring you to configure certificate use separately.</span></span> <span data-ttu-id="96b7e-106">También puede importar un certificado mediante la utilidad CertWizard que configura automáticamente el uso de los certificados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="96b7e-106">You can also import a certificate by using the CertWizard utility that automatically configures certificate use for you.</span></span>  
  
 <span data-ttu-id="96b7e-107">Para importar certificados privada, debe usar las cuentas de usuario en la que se ejecutan los Hosts de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="96b7e-107">To import private certificates, you must use the user accounts under which the BizTalk Hosts run.</span></span>  
  
### <a name="to-import-a-public-key-certificate"></a><span data-ttu-id="96b7e-108">Para importar un certificado de clave pública</span><span class="sxs-lookup"><span data-stu-id="96b7e-108">To import a public-key certificate</span></span>  
  
1.  <span data-ttu-id="96b7e-109">Copia el certificado de clave pública (.cer) del archivo a una ubicación en el disco duro del servidor al que va a copiar certificados.</span><span class="sxs-lookup"><span data-stu-id="96b7e-109">Copy the public-key (.cer) certificate file to a location on the hard disk of the server to which you are copying certificates.</span></span>  
  
2.  <span data-ttu-id="96b7e-110">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-110">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
3.  <span data-ttu-id="96b7e-111">En el [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expanda **certificados (equipo Local)**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-111">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="96b7e-112">El usuario ha iniciado la sesión debe tener permisos administrativos en el equipo.</span><span class="sxs-lookup"><span data-stu-id="96b7e-112">The logged-in user must have administrative permissions to the computer.</span></span>  
  
4.  <span data-ttu-id="96b7e-113">Haga clic en **otras personas**, seleccione **todas las tareas**y, a continuación, haga clic en **importación**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-113">Right-click **Other People**, point to **All Tasks**, and then click **Import**.</span></span>  
  
5.  <span data-ttu-id="96b7e-114">En el **principal del Asistente para certificados importación** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-114">On the **Certificate Import Wizard Welcome** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="96b7e-115">En el **archivo para importar** página, haga clic en **examinar** y busque la carpeta que contiene los archivos de certificado.</span><span class="sxs-lookup"><span data-stu-id="96b7e-115">On the **File to Import** page, click **Browse** and locate the folder that contains the certificate files.</span></span> <span data-ttu-id="96b7e-116">Seleccione el archivo desde el que desea importar el certificado y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-116">Select the file from which you want to import the certificate, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="96b7e-117">En el **almacén de certificados** página, seleccione **seleccionar automáticamente el certificado según el tipo de certificado** o **colocar todos los certificados en el siguiente almacén**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-117">On the **Certificate store** page, select either **Automatically select the certificate based on the type of certificate** or **Place all certificates in the following store**.</span></span> <span data-ttu-id="96b7e-118">Si selecciona **colocar todos los certificados en el siguiente almacén**, haga clic en **examinar**, seleccione el almacén de certificados, haga clic en **Aceptar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-118">If you select **Place all certificates in the following store**, click **Browse**, select the certificate store, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="96b7e-119">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-119">Click **Finish**.</span></span>  
  
### <a name="to-import-a-private-key-certificate"></a><span data-ttu-id="96b7e-120">Para importar un certificado de clave privada</span><span class="sxs-lookup"><span data-stu-id="96b7e-120">To import a private-key certificate</span></span>  
  
1.  <span data-ttu-id="96b7e-121">Certificado de clave privada (.pfx) copia archivos en una ubicación en el disco duro del servidor al que va a copiar certificados.</span><span class="sxs-lookup"><span data-stu-id="96b7e-121">Copy private-key (.pfx) certificate files to a location on the hard disk of the server to which you are copying certificates.</span></span>  
  
2.  <span data-ttu-id="96b7e-122">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **ejecutar como/User:\<servicio de host > mmc**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-122">Click **Start**, click **Run**, type **run as /user:\<host service> mmc**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96b7e-123">Para \< *hospedar servicio*>, escriba el nombre del servicio que se selecciona automáticamente para el servicio de host cuando instaló [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96b7e-123">For \<*host service*>, type the name of the service that was automatically selected for the host service when you installed [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span>  
  
3.  <span data-ttu-id="96b7e-124">Escriba la contraseña de \< *hospedar servicio*> y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-124">Type the password for \<*host service*>, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="96b7e-125">En [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] consola de administración, en la **archivo** menú, haga clic en **agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-125">In [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
5.  <span data-ttu-id="96b7e-126">En el cuadro de diálogo Agregar o quitar complemento, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-126">In the Add/Remove Snap-in dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="96b7e-127">En el cuadro de diálogo Add Standalone Snap-in, seleccione **certificados**, haga clic en **agregar**, haga clic en **cerrar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-127">In the Add Standalone Snap-in dialog box, select **Certificates**, click **Add**, click **Close**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="96b7e-128">En [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console, expanda **certificados - usuario actual**, haga clic en **Personal**, seleccione **todas las tareas**y, a continuación, haga clic en  **Importación**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-128">In [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console, expand **Certificates - Current User**, right-click **Personal**, point to **All Tasks**, and then click **Import**.</span></span>  
  
8.  <span data-ttu-id="96b7e-129">En el **principal del Asistente para certificados importación** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-129">On the **Certificate Import Wizard Welcome** page, click **Next**.</span></span>  
  
9. <span data-ttu-id="96b7e-130">En el **archivo para importar** página, haga clic en **examinar** y busque la carpeta que contiene el archivo de certificado .pfx que contiene el certificado que desea importar.</span><span class="sxs-lookup"><span data-stu-id="96b7e-130">On the **File to Import** page, click **Browse** and locate the folder that contains the .pfx certificate file that contains the certificate that you want to import.</span></span> <span data-ttu-id="96b7e-131">Seleccione el archivo adecuado y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-131">Select the appropriate file, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="96b7e-132">En el **contraseña** página, en la **contraseña** , escriba la contraseña para el archivo de clave privada.</span><span class="sxs-lookup"><span data-stu-id="96b7e-132">On the **Password** page, in the **Password** box, type the password for the private-key file.</span></span>  
  
11. <span data-ttu-id="96b7e-133">Seleccione **Habilitar protección segura de clave privada** o **marcar esta clave como exportable**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-133">Select **Enable strong private key protection** or **Mark this key as exportable**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="96b7e-134">En el **almacén de certificados** página, seleccione **seleccionar automáticamente el certificado según el tipo de certificado** o **colocar todos los certificados en el siguiente almacén**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-134">On the **Certificate store** page, select either **Automatically select the certificate based on the type of certificate** or **Place all certificates in the following store**.</span></span> <span data-ttu-id="96b7e-135">Si selecciona **colocar todos los certificados en el siguiente almacén**, haga clic en **examinar**, seleccione el almacén, haga clic en **Aceptar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-135">If you select **Place all certificates in the following store**, click **Browse**, select the store, click **OK**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="96b7e-136">En el **completar el Asistente para importación de certificados** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="96b7e-136">On the **Completing the Certificate Import Wizard** page, click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b7e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="96b7e-137">See Also</span></span>  
 <span data-ttu-id="96b7e-138">[Configuración de certificados importados con MMC](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md) </span><span class="sxs-lookup"><span data-stu-id="96b7e-138">[Configuring Certificates Imported Using MMC](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md) </span></span>  
 [<span data-ttu-id="96b7e-139">CertWizard</span><span class="sxs-lookup"><span data-stu-id="96b7e-139">CertWizard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)