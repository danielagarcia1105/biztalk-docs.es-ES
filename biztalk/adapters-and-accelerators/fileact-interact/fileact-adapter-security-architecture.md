---
title: Arquitectura de seguridad del adaptador de FileAct | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5faeebd6-5287-4ac4-a1db-e3c055d323d2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ed8352b788af12fd3c38f489e9ddb65d8375f2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222796"
---
# <a name="fileact-adapter-security-architecture"></a><span data-ttu-id="bfc38-102">Arquitectura de seguridad del adaptador de FileAct</span><span class="sxs-lookup"><span data-stu-id="bfc38-102">FileAct Adapter Security Architecture</span></span>
<span data-ttu-id="bfc38-103">Seguridad para la transmisión de archivos y la recepción se implementa mediante las características de certificado y clave criptográfica inherentes en SNL y el SAG.</span><span class="sxs-lookup"><span data-stu-id="bfc38-103">Security for the file transmission and receipt is implemented using the certificate and crypto features inherent in SNL and the SAG.</span></span>  <span data-ttu-id="bfc38-104">La administración de certificados, etc., es completamente fuera del ámbito del adaptador de FileAct.</span><span class="sxs-lookup"><span data-stu-id="bfc38-104">The management of certificates, etc., is completely outside of the scope of the FileAct Adapter.</span></span> <span data-ttu-id="bfc38-105">Siempre y cuando la instancia asociada de SNL/SAG se registra para el servicio de FileAct con SWIFT y el software está instalado correctamente en SNL/SAG, el adaptador hace uso de la a través de instalaciones las API de SNL.</span><span class="sxs-lookup"><span data-stu-id="bfc38-105">As long as the associated SNL/SAG instance is registered for the FileAct service with SWIFT and the software properly installed on SNL/SAG, the adapter makes use of the facilities throught the SNL APIs.</span></span> <span data-ttu-id="bfc38-106">El adaptador de FileAct siempre establecerá el FACryptoMode en "Advanced" (se recomienda).</span><span class="sxs-lookup"><span data-stu-id="bfc38-106">The FileAct Adapter will always set the FACryptoMode to “Advanced” (best practice).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfc38-107">Para el adaptador, puede crear un contexto de seguridad independientes para cada puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="bfc38-107">For the adapter, you can create a separate security context for  each send port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfc38-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfc38-108">See Also</span></span>  
 <span data-ttu-id="bfc38-109">[Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="bfc38-109">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="bfc38-110">[Primitivas de extremo a extremo de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="bfc38-110">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="bfc38-111">[Primitivos locales de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="bfc38-111">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="bfc38-112">[Almacenamiento de adaptador FileAct y reenvío](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="bfc38-112">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="bfc38-113">[Archivo de adaptador FileAct e identificación de transferencia](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="bfc38-113">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="bfc38-114">[Transferencia de información de soporte de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="bfc38-114">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="bfc38-115">[Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="bfc38-115">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="bfc38-116">Estado del adaptador de FileAct supervisión</span><span class="sxs-lookup"><span data-stu-id="bfc38-116">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)