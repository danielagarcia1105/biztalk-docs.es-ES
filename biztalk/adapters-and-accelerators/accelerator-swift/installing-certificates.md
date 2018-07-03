---
title: Instalación de certificados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, installing
- installing, certificates
ms.assetid: 7525f771-623c-420f-99ca-c834e819829d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 111bd267bc7d0bc12d582c3b74846b8874ed8b4d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012549"
---
# <a name="installing-certificates"></a><span data-ttu-id="f41df-102">Instalación de certificados</span><span class="sxs-lookup"><span data-stu-id="f41df-102">Installing Certificates</span></span>
<span data-ttu-id="f41df-103">Para enviar, reparar o enviar mensajes, debe tener instalados los certificados apropiados.</span><span class="sxs-lookup"><span data-stu-id="f41df-103">To send, repair, or submit messages, you must have the proper certificates installed.</span></span> <span data-ttu-id="f41df-104">Este tema describe cómo agregar certificados.</span><span class="sxs-lookup"><span data-stu-id="f41df-104">This topic describes how to add certificates.</span></span> <span data-ttu-id="f41df-105">En un entorno de producción, consulte el departamento de TI para los certificados.</span><span class="sxs-lookup"><span data-stu-id="f41df-105">In a production environment, see your IT department for certificates.</span></span>  

 <span data-ttu-id="f41df-106">**Resumen**</span><span class="sxs-lookup"><span data-stu-id="f41df-106">**Summary**</span></span>  

 <span data-ttu-id="f41df-107">Esta sección proporciona instrucciones sobre cómo crear y almacenar los certificados siguientes:</span><span class="sxs-lookup"><span data-stu-id="f41df-107">This section provides instructions on how to create and store the following certificates:</span></span>  

- <span data-ttu-id="f41df-108">Almacén de certificados para cada uno de los roles de nuevo envío en la carpeta Personal de los certificados - usuario actual y la reparación de mensajes en cada equipo cliente</span><span class="sxs-lookup"><span data-stu-id="f41df-108">Certificates for each of the Message Repair and New Submission roles in the Personal folder of the Certificates - Current User store on each client computer</span></span>  

- <span data-ttu-id="f41df-109">Almacén de certificados para cada uno de los roles de nuevo envío en la carpeta de otras personas de los certificados (equipo Local) y la reparación de mensajes en cada equipo de orquestación de BizTalk server</span><span class="sxs-lookup"><span data-stu-id="f41df-109">Certificates for each of the Message Repair and New Submission roles in the Other People folder of the Certificates (Local Computer) store on each BizTalk orchestration server computer</span></span>  

- <span data-ttu-id="f41df-110">Certificado de entidad de certificación en la carpeta entidades emisoras raíz de confianza en el almacén de certificados (equipo Local) en cada equipo cliente</span><span class="sxs-lookup"><span data-stu-id="f41df-110">Certification Authority's certificate into the Trusted Root Certification Authorities folder in the Certificates (Local Computer) store on each client computer</span></span>  

  <span data-ttu-id="f41df-111">Si ha implementado [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] en un único equipo y también tiene un servidor de certificados instalado en el mismo equipo, deberá excluir el servidor de certificados de las rutas de acceso administrados para Microsoft SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="f41df-111">If you have deployed [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] on a single computer, and also have a certificate server installed on the same computer, you need to exclude the certificate server from the managed paths for Microsoft SharePoint Server.</span></span>  

  <span data-ttu-id="f41df-112">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="f41df-112">This section contains:</span></span>  

- [<span data-ttu-id="f41df-113">Agregar certificados al almacén de certificados en el cliente</span><span class="sxs-lookup"><span data-stu-id="f41df-113">Adding Certificates to the Certificates Store on the Client</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-client.md)  

- [<span data-ttu-id="f41df-114">Agregar certificados al almacén de certificados en el servidor</span><span class="sxs-lookup"><span data-stu-id="f41df-114">Adding Certificates to the Certificates Store on the Server</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-server.md)  

- [<span data-ttu-id="f41df-115">Exclusión de CertSrv de las rutas de acceso administradas en la implementación de un solo equipo</span><span class="sxs-lookup"><span data-stu-id="f41df-115">Excluding CertSrv from Managed Paths on a Single-Computer Deployment</span></span>](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)
