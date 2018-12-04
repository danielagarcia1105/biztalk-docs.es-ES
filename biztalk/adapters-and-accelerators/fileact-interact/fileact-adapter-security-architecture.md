---
title: Arquitectura de seguridad del adaptador de FileAct | Microsoft Docs
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
ms.openlocfilehash: be9997dca0a4b7a5c619848e4ed38cf9099bbc16
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826380"
---
# <a name="fileact-adapter-security-architecture"></a><span data-ttu-id="e0f83-102">Arquitectura de seguridad del adaptador de FileAct</span><span class="sxs-lookup"><span data-stu-id="e0f83-102">FileAct Adapter Security Architecture</span></span>
<span data-ttu-id="e0f83-103">Seguridad para la transmisión de archivos y la recepción se implementa mediante las características de certificado y clave criptográfica inherentes SNL y el SAG.</span><span class="sxs-lookup"><span data-stu-id="e0f83-103">Security for the file transmission and receipt is implemented using the certificate and crypto features inherent in SNL and the SAG.</span></span>  <span data-ttu-id="e0f83-104">La administración de certificados, etc., está completamente fuera del ámbito del adaptador de FileAct.</span><span class="sxs-lookup"><span data-stu-id="e0f83-104">The management of certificates, etc., is completely outside of the scope of the FileAct Adapter.</span></span> <span data-ttu-id="e0f83-105">Siempre que la instancia asociada de SNL/SAG está registrada para el servicio de FileAct con SWIFT y el software está instalado correctamente en SNL/SAG, el adaptador realiza el uso de las funciones a través de la API de SNL.</span><span class="sxs-lookup"><span data-stu-id="e0f83-105">As long as the associated SNL/SAG instance is registered for the FileAct service with SWIFT and the software properly installed on SNL/SAG, the adapter makes use of the facilities through the SNL APIs.</span></span> <span data-ttu-id="e0f83-106">El adaptador de FileAct siempre establecerá el FACryptoMode en "Advanced" (recomendado).</span><span class="sxs-lookup"><span data-stu-id="e0f83-106">The FileAct Adapter will always set the FACryptoMode to “Advanced” (best practice).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0f83-107">Para el adaptador, puede crear un contexto de seguridad independientes para cada puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="e0f83-107">For the adapter, you can create a separate security context for  each send port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0f83-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0f83-108">See Also</span></span>  
 <span data-ttu-id="e0f83-109">[Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="e0f83-109">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="e0f83-110">[Primitivas to-End en tiempo real del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="e0f83-110">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="e0f83-111">[Primitivas locales en tiempo real del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="e0f83-111">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="e0f83-112">[Avance y Store de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="e0f83-112">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="e0f83-113">[Identificación de transferencia y archivo de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="e0f83-113">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="e0f83-114">[Transferencia de información complementaria de adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="e0f83-114">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="e0f83-115">[Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="e0f83-115">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="e0f83-116">Supervisión de estado del adaptador de FileAct</span><span class="sxs-lookup"><span data-stu-id="e0f83-116">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)
