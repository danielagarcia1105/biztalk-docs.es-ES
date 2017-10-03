---
title: "Orígenes y los almacenes de certificados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, certificate storage
- importing certificates
- certificates, certificate sources
- certificates, importing
ms.assetid: 3e98fb56-4368-46f3-9329-c44fed11f4fb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ade897bb51850b4ef9dd6b530f5fc04c6b2601
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="certificate-sources-and-stores"></a><span data-ttu-id="f662b-102">Orígenes de certificados y almacenes</span><span class="sxs-lookup"><span data-stu-id="f662b-102">Certificate Sources and Stores</span></span>
<span data-ttu-id="f662b-103">Este tema describe dónde desea importar certificados desde y dónde se almacenarán los certificados.</span><span class="sxs-lookup"><span data-stu-id="f662b-103">This topic describes where to import certificates from, and where to store certificates.</span></span>  
  
## <a name="certificate-sources"></a><span data-ttu-id="f662b-104">Orígenes de certificado</span><span class="sxs-lookup"><span data-stu-id="f662b-104">Certificate Sources</span></span>  
 <span data-ttu-id="f662b-105">Importar certificados de los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="f662b-105">You import certificates from the following files:</span></span>  
  
-   <span data-ttu-id="f662b-106">Certificados privados de archivos .pfx o. p12.</span><span class="sxs-lookup"><span data-stu-id="f662b-106">Private certificates from .pfx or .p12 files.</span></span> <span data-ttu-id="f662b-107">Después de importar los certificados, almacene estos archivos de forma segura.</span><span class="sxs-lookup"><span data-stu-id="f662b-107">After importing the certificates, store these files securely.</span></span> <span data-ttu-id="f662b-108">Si importa los certificados privados mediante la utilidad CertWizard, puede establecer la **/Exportable** cambie a `False`, que es la configuración predeterminada, por lo que no se puede exportar los certificados privados de la tienda en un archivo.</span><span class="sxs-lookup"><span data-stu-id="f662b-108">If you import the private certificates using the CertWizard utility, you can set the **/Exportable** switch to `False`, which is the default setting, so that the private certificates cannot be exported from the store into a file.</span></span> <span data-ttu-id="f662b-109">Si establece la **/Exportable** cambie a `True`, puede exportar estos certificados en un archivo de los certificados [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="f662b-109">If you set the **/Exportable** switch to `True`, you can export these certificates to a file from the Certificates [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span></span>  
  
-   <span data-ttu-id="f662b-110">Certificados públicos de archivos .cer o .der.</span><span class="sxs-lookup"><span data-stu-id="f662b-110">Public certificates from .cer or .der files.</span></span> <span data-ttu-id="f662b-111">Socios envían sus certificados para que en estos archivos.</span><span class="sxs-lookup"><span data-stu-id="f662b-111">Partners send their certificates to you in these files.</span></span>  
  
-   <span data-ttu-id="f662b-112">Certificados raíz de los archivos .cer o .der.</span><span class="sxs-lookup"><span data-stu-id="f662b-112">Root certificates from .cer or .der files.</span></span> <span data-ttu-id="f662b-113">Entidades de certificación envían sus certificados raíz para que en estos archivos.</span><span class="sxs-lookup"><span data-stu-id="f662b-113">Certification authorities send their root certificates to you in these files.</span></span>  
  
## <a name="certificate-storage"></a><span data-ttu-id="f662b-114">Almacenamiento de certificados</span><span class="sxs-lookup"><span data-stu-id="f662b-114">Certificate Storage</span></span>  
 <span data-ttu-id="f662b-115">Importar certificados a uno de los dos almacenes de certificados en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f662b-115">You import certificates into one of two Certificates stores on the local computer.</span></span> <span data-ttu-id="f662b-116">Almacenar certificados pública en el **certificados (equipo Local)** almacenar.</span><span class="sxs-lookup"><span data-stu-id="f662b-116">You store public certificates in the **Certificates (Local Computer)** store.</span></span> <span data-ttu-id="f662b-117">Puede abrir los nodos de este almacén abriendo el **certificados (equipo Local)** nodo en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span><span class="sxs-lookup"><span data-stu-id="f662b-117">You can open the nodes of this store by opening the **Certificates (Local Computer)** node in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span></span> <span data-ttu-id="f662b-118">Puede tener acceso a la **certificados (equipo Local)** almacenar si tiene permisos administrativos en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f662b-118">You can access the **Certificates (Local Computer)** store if you have administrative permissions on the computer.</span></span> <span data-ttu-id="f662b-119">Almacenar certificados pública en las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="f662b-119">Store public certificates in the following folders:</span></span>  
  
-   <span data-ttu-id="f662b-120">Inicio certificados pública en la carpeta Personal en el **certificados (equipo Local)** almacenar</span><span class="sxs-lookup"><span data-stu-id="f662b-120">Home public certificates in the Personal folder in the **Certificates (Local Computer)** store</span></span>  
  
-   <span data-ttu-id="f662b-121">Socios certificados pública en la carpeta de otras personas de la **certificados (equipo Local)** almacenar</span><span class="sxs-lookup"><span data-stu-id="f662b-121">Partner public certificates in the Other People folder of the **Certificates (Local Computer)** store</span></span>  
  
-   <span data-ttu-id="f662b-122">Certificados de entidades emisoras de certificados en la carpeta de la entidad de certificación raíz de confianza de la **certificados (equipo Local)** almacenar</span><span class="sxs-lookup"><span data-stu-id="f662b-122">Certificates from certification authorities in the Trusted Root Certification Authority folder of the **Certificates (Local Computer)** store</span></span>  
  
 <span data-ttu-id="f662b-123">Almacenar certificados privada en el **certificados - usuario actual** almacenar.</span><span class="sxs-lookup"><span data-stu-id="f662b-123">You store private certificates in the **Certificates - Current User** store.</span></span> <span data-ttu-id="f662b-124">Puede abrir los nodos de este almacén, abra la consola de administración utilizando la **runas** comando con el usuario de cuenta de servicio de host.</span><span class="sxs-lookup"><span data-stu-id="f662b-124">You can open the nodes of this store by opening the Management Console using the **runas** command with the host service account user.</span></span> <span data-ttu-id="f662b-125">Para obtener más información, consulte [importar certificados](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f662b-125">For more information, see [Importing Certificates](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f662b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f662b-126">See Also</span></span>  
 <span data-ttu-id="f662b-127">[Importación de certificados mediante la utilidad CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md) </span><span class="sxs-lookup"><span data-stu-id="f662b-127">[Importing Certificates Using the CertWizard Utility](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md) </span></span>  
 <span data-ttu-id="f662b-128">[Importación de certificados mediante MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md) </span><span class="sxs-lookup"><span data-stu-id="f662b-128">[Importing Certificates Using MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md) </span></span>  
 [<span data-ttu-id="f662b-129">Importar certificados &#91; RN3 &#93;</span><span class="sxs-lookup"><span data-stu-id="f662b-129">Importing Certificates &#91;RN3&#93;</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)