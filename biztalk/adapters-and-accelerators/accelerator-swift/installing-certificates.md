---
title: "Instalación de certificados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, installing
- installing, certificates
ms.assetid: 7525f771-623c-420f-99ca-c834e819829d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5ded26548303dfe9c9a095c24396b4e2683ca4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-certificates"></a><span data-ttu-id="15bcf-102">Instalación de certificados</span><span class="sxs-lookup"><span data-stu-id="15bcf-102">Installing Certificates</span></span>
<span data-ttu-id="15bcf-103">Para enviar, reparar o enviar mensajes, debe tener instalados los certificados apropiados.</span><span class="sxs-lookup"><span data-stu-id="15bcf-103">To send, repair, or submit messages, you must have the proper certificates installed.</span></span> <span data-ttu-id="15bcf-104">En este tema se describe cómo agregar certificados.</span><span class="sxs-lookup"><span data-stu-id="15bcf-104">This topic describes how to add certificates.</span></span> <span data-ttu-id="15bcf-105">En un entorno de producción, consulte el departamento de TI para los certificados.</span><span class="sxs-lookup"><span data-stu-id="15bcf-105">In a production environment, see your IT department for certificates.</span></span>  
  
 <span data-ttu-id="15bcf-106">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="15bcf-106">**Summary**</span></span>  
  
 <span data-ttu-id="15bcf-107">Esta sección proporciona instrucciones sobre cómo crear y almacenar los certificados siguientes:</span><span class="sxs-lookup"><span data-stu-id="15bcf-107">This section provides instructions on how to create and store the following certificates:</span></span>  
  
-   <span data-ttu-id="15bcf-108">Almacén de certificados para cada uno de los roles de nuevo envío en la carpeta Personal de los certificados - usuario actual y la reparación de mensajes en cada equipo cliente</span><span class="sxs-lookup"><span data-stu-id="15bcf-108">Certificates for each of the Message Repair and New Submission roles in the Personal folder of the Certificates - Current User store on each client computer</span></span>  
  
-   <span data-ttu-id="15bcf-109">Almacén de certificados para cada uno de los roles de nuevo envío en la carpeta de otras personas de los certificados (equipo Local) y la reparación de mensajes en cada equipo de servidor de la orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="15bcf-109">Certificates for each of the Message Repair and New Submission roles in the Other People folder of the Certificates (Local Computer) store on each BizTalk orchestration server computer</span></span>  
  
-   <span data-ttu-id="15bcf-110">Certificado de la entidad de certificación en la carpeta entidades emisoras raíz de confianza en el almacén de certificados (equipo Local) en cada equipo cliente</span><span class="sxs-lookup"><span data-stu-id="15bcf-110">Certification Authority's certificate into the Trusted Root Certification Authorities folder in the Certificates (Local Computer) store on each client computer</span></span>  
  
 <span data-ttu-id="15bcf-111">Si ha implementado [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] en un único equipo y también un servidor de certificados instalado en el mismo equipo, debe excluir el servidor de certificados de las rutas de acceso administradas para [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] servidor de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="15bcf-111">If you have deployed [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] on a single computer, and also have a certificate server installed on the same computer, you need to exclude the certificate server from the managed paths for [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] SharePoint Server.</span></span>  
  
 <span data-ttu-id="15bcf-112">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="15bcf-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="15bcf-113">Agregar certificados al almacén de certificados en el cliente</span><span class="sxs-lookup"><span data-stu-id="15bcf-113">Adding Certificates to the Certificates Store on the Client</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-client.md)  
  
-   [<span data-ttu-id="15bcf-114">Agregar certificados al almacén de certificados en el servidor</span><span class="sxs-lookup"><span data-stu-id="15bcf-114">Adding Certificates to the Certificates Store on the Server</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-server.md)  
  
-   [<span data-ttu-id="15bcf-115">Exclusión de CertSrv de rutas de acceso administradas en la implementación de una solo equipo</span><span class="sxs-lookup"><span data-stu-id="15bcf-115">Excluding CertSrv from Managed Paths on a Single-Computer Deployment</span></span>](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)