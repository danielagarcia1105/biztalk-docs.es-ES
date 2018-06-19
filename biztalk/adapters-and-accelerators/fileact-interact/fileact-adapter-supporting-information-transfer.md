---
title: Compatibilidad con la transferencia de información de adaptador de FileAct | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fc27561-9abb-4496-9db7-f221a6c90738
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5aefba5fe85a8a275d3b2050d8c08cc98f74d06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222820"
---
# <a name="fileact-adapter-supporting-information-transfer"></a><span data-ttu-id="10d8c-102">Transferencia de información de soporte de adaptador de FileAct</span><span class="sxs-lookup"><span data-stu-id="10d8c-102">FileAct Adapter Supporting Information Transfer</span></span>
<span data-ttu-id="10d8c-103">El adaptador de FileAct permite a la transferencia de información complementaria con archivos opcional.</span><span class="sxs-lookup"><span data-stu-id="10d8c-103">The FileAct adapter permits the optional transfer of supporting information with files.</span></span> <span data-ttu-id="10d8c-104">Esta información se transfiere a discreción de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10d8c-104">This information is transferred at the discretion of the application.</span></span> <span data-ttu-id="10d8c-105">El adaptador no realiza ningún procesamiento especial de esta información en el lado de origen excepto para validar que se encuentra en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="10d8c-105">The adapter does not do any special processing of this information on the originating side except to validate that it is in the correct format.</span></span> <span data-ttu-id="10d8c-106">Los elementos que componen la información de apoyo incluyen:</span><span class="sxs-lookup"><span data-stu-id="10d8c-106">The elements which comprise supporting information include:</span></span>  
  
-   <span data-ttu-id="10d8c-107">Descripción del archivo y la información de archivo</span><span class="sxs-lookup"><span data-stu-id="10d8c-107">File description and file information</span></span>  
  
-   <span data-ttu-id="10d8c-108">Descripción de la transferencia y la información de transferencia</span><span class="sxs-lookup"><span data-stu-id="10d8c-108">Transfer description and transfer information</span></span>  
  
-   <span data-ttu-id="10d8c-109">Descripción de confirmación y la información de confirmación</span><span class="sxs-lookup"><span data-stu-id="10d8c-109">Acknowledgement description and acknowledgement information</span></span>  
  
-   <span data-ttu-id="10d8c-110">Información de descripción y el rechazo de rechazo</span><span class="sxs-lookup"><span data-stu-id="10d8c-110">Rejection description and reject information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10d8c-111">Uno de los componentes de la información de archivo define la compresión y descompresión.</span><span class="sxs-lookup"><span data-stu-id="10d8c-111">One of the components of file information defines compression and decompression.</span></span> <span data-ttu-id="10d8c-112">Compresión y descompresión son responsabilidad de la aplicación, no el adaptador.</span><span class="sxs-lookup"><span data-stu-id="10d8c-112">Compression and decompression are the responsibility of the application, not the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10d8c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="10d8c-113">See Also</span></span>  
 <span data-ttu-id="10d8c-114">[Arquitectura del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="10d8c-114">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="10d8c-115">[Primitivas de extremo a extremo de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="10d8c-115">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="10d8c-116">[Primitivos locales de FileAct adaptador en tiempo real](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="10d8c-116">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="10d8c-117">[Almacenamiento de adaptador FileAct y reenvío](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="10d8c-117">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="10d8c-118">[Arquitectura de seguridad del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="10d8c-118">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="10d8c-119">[Archivo de adaptador FileAct e identificación de transferencia](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="10d8c-119">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="10d8c-120">[Notificación de entrega del adaptador de FileAct](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="10d8c-120">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="10d8c-121">Estado del adaptador de FileAct supervisión</span><span class="sxs-lookup"><span data-stu-id="10d8c-121">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)