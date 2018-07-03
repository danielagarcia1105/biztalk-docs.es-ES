---
title: Importación de certificados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing certificates
- certificates, importing
ms.assetid: c2576f89-b5de-4250-9c54-74c8a218bb39
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96bdc2a681cf3632f6393a3fef05ec275f60f82f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006085"
---
# <a name="importing-certificates"></a><span data-ttu-id="4f203-102">Importación de certificados</span><span class="sxs-lookup"><span data-stu-id="4f203-102">Importing Certificates</span></span>
<span data-ttu-id="4f203-103">En esta sección se describe cómo importar certificados, incluidos where importarlos desde dónde almacenarla y qué herramientas para utilizar para importarlos.</span><span class="sxs-lookup"><span data-stu-id="4f203-103">This section describes how to import certificates, including where to import them from, where to store them, and what tools to use to import them.</span></span>  
  
 <span data-ttu-id="4f203-104">Hay dos formas de importar los certificados.</span><span class="sxs-lookup"><span data-stu-id="4f203-104">There are two ways to import certificates.</span></span> <span data-ttu-id="4f203-105">Puede usar la herramienta CertWizard o el complemento certificados para Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="4f203-105">You can use the CertWizard tool or the Certificates snap-in for Microsoft Management Console (MMC).</span></span>  
  
- <span data-ttu-id="4f203-106">CertWizard es un asistente paso a paso de línea de comandos que configura el uso del certificado según la configuración de modificadores.</span><span class="sxs-lookup"><span data-stu-id="4f203-106">CertWizard is a step-by-step command-line wizard that configures the use of the certificate based on the settings of switches.</span></span> <span data-ttu-id="4f203-107">Esta herramienta está disponible en Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] carpeta del SDK.</span><span class="sxs-lookup"><span data-stu-id="4f203-107">This tool is available in the Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK folder.</span></span>  
  
- <span data-ttu-id="4f203-108">Con el complemento de certificados en MMC, puede importar un certificado al almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="4f203-108">With the Certificates snap-in in MMC, you can import a certificate into the certificate store.</span></span> <span data-ttu-id="4f203-109">Sin embargo, este proceso manual requiere que configure el uso del certificado por separado.</span><span class="sxs-lookup"><span data-stu-id="4f203-109">However, this manual process requires that you configure the use of the certificate separately.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="4f203-110">Para importar o trabajar con certificados privados en MMC, el usuario que ha iniciado sesión debe tener la identidad del usuario de los Hosts de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4f203-110">To import or work with private certificates in MMC, the user who is logged on must have the user identity of the BizTalk Hosts.</span></span> <span data-ttu-id="4f203-111">Si no, debe ejecutar el **runas** comando con el modificador de usuario y la cuenta de servicio de host para iniciar MMC certificados, por ejemplo, **runas /user:hostsvc mmc**.</span><span class="sxs-lookup"><span data-stu-id="4f203-111">If not, you must run the **runas** command with the user switch and the host service account to start the Certificates MMC, for example, **runas /user:hostsvc mmc**.</span></span> <span data-ttu-id="4f203-112">Al ejecutar este comando, asume la identidad de usuario de los Hosts de BizTalk (BizTalkServerApplication y BizTalkServerIsolatedHost).</span><span class="sxs-lookup"><span data-stu-id="4f203-112">By running this command, you assume the user identity of the BizTalk Hosts (BizTalkServerApplication and BizTalkServerIsolatedHost).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f203-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4f203-113">In This Section</span></span>  
  
-   [<span data-ttu-id="4f203-114">Orígenes de certificados y almacenes</span><span class="sxs-lookup"><span data-stu-id="4f203-114">Certificate Sources and Stores</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [<span data-ttu-id="4f203-115">Importación de certificados mediante la utilidad CertWizard</span><span class="sxs-lookup"><span data-stu-id="4f203-115">Importing Certificates Using the CertWizard Utility</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [<span data-ttu-id="4f203-116">Importación de certificados mediante MMC</span><span class="sxs-lookup"><span data-stu-id="4f203-116">Importing Certificates Using MMC</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)