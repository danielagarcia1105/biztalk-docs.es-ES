---
title: Administrar Certificates1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing certificates
- certificates, managing
ms.assetid: ffa60e2b-c131-4a49-ad1e-6c8a7271b05c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3d74342d15d65082b6d94f252023c3df1d601dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209292"
---
# <a name="managing-certificates"></a><span data-ttu-id="b745b-102">Administración de certificados</span><span class="sxs-lookup"><span data-stu-id="b745b-102">Managing Certificates</span></span>
<span data-ttu-id="b745b-103">Las comunicaciones seguras en RosettaNet requieren el uso de certificados.</span><span class="sxs-lookup"><span data-stu-id="b745b-103">Secure communications in RosettaNet require using certificates.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="b745b-104">® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] utiliza certificados para cifrar los mensajes salientes, firmar los mensajes salientes, descifrar los mensajes entrantes y comprobar la firma de los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="b745b-104">® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses certificates to encrypt outgoing messages, sign outgoing messages, decrypt incoming messages, and verify the signature in incoming messages.</span></span>  
  
 <span data-ttu-id="b745b-105">Para usar certificados, debe realizar todos o algunos de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b745b-105">To use certificates, you must perform some or all of the following steps:</span></span>  
  
-   <span data-ttu-id="b745b-106">Importar certificados al almacén de certificados para el servidor</span><span class="sxs-lookup"><span data-stu-id="b745b-106">Import certificates into the certificates store for the server</span></span>  
  
-   <span data-ttu-id="b745b-107">Configurar el uso de certificados en los mensajes</span><span class="sxs-lookup"><span data-stu-id="b745b-107">Configure the use of certificates in messages</span></span>  
  
-   <span data-ttu-id="b745b-108">Exportar certificados a los socios comerciales</span><span class="sxs-lookup"><span data-stu-id="b745b-108">Export certificates to partners</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b745b-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b745b-109">In This Section</span></span>  
  
-   [<span data-ttu-id="b745b-110">Importación de certificados</span><span class="sxs-lookup"><span data-stu-id="b745b-110">Importing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md)  
  
-   [<span data-ttu-id="b745b-111">Exportación de certificados</span><span class="sxs-lookup"><span data-stu-id="b745b-111">Exporting Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/exporting-certificates.md)