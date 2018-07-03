---
title: RNIFReceive | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf1253b0-ceca-4e7a-91ed-3837bd904472
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d54b66c42fae286ec748ef560c461a22124165b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991781"
---
# <a name="rnifreceive"></a><span data-ttu-id="6d8f2-102">RNIFReceive</span><span class="sxs-lookup"><span data-stu-id="6d8f2-102">RNIFReceive</span></span>
<span data-ttu-id="6d8f2-103">Este ejemplo proporciona un Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx archivo que recibe un mensaje RNIF y lo prepara para el procesamiento por la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] proceso público.</span><span class="sxs-lookup"><span data-stu-id="6d8f2-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx file that receives an RNIF message, and prepares it for processing by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public process.</span></span> <span data-ttu-id="6d8f2-104">Puede personalizar la página ASPX para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d8f2-104">You can customize the ASPX page to do the following:</span></span>  
  
- <span data-ttu-id="6d8f2-105">Agregar o quitar los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="6d8f2-105">Add or remove performance counters</span></span>  
  
- <span data-ttu-id="6d8f2-106">Agregar funciones a la página, como escribir datos en una base de datos o personalizar la función de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6d8f2-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
- <span data-ttu-id="6d8f2-107">Agregar validación a la página</span><span class="sxs-lookup"><span data-stu-id="6d8f2-107">Add validation to the page</span></span>  
  
  <span data-ttu-id="6d8f2-108">Este ejemplo se encuentra en  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\WebApplication\RNIFReceiver.</span><span class="sxs-lookup"><span data-stu-id="6d8f2-108">This sample is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\WebApplication\RNIFReceiver.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6d8f2-109">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="6d8f2-109">Demonstrates</span></span>  
 <span data-ttu-id="6d8f2-110">Este ejemplo muestra cómo preparar los mensajes entrantes para el proceso público, incluidos los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="6d8f2-110">This sample demonstrates how to prepare incoming messages for the public process, including the following:</span></span>  
  
-   <span data-ttu-id="6d8f2-111">Recibir el mensaje del RNIFSend.aspx del asociado</span><span class="sxs-lookup"><span data-stu-id="6d8f2-111">Receiving the message from the partner's RNIFSend.aspx</span></span>  
  
-   <span data-ttu-id="6d8f2-112">Validar el encabezado MIME</span><span class="sxs-lookup"><span data-stu-id="6d8f2-112">Validating the MIME header</span></span>  
  
-   <span data-ttu-id="6d8f2-113">Quitar el encabezado MIME y los límites del mensaje</span><span class="sxs-lookup"><span data-stu-id="6d8f2-113">Removing the MIME header and boundaries from the message</span></span>  
  
-   <span data-ttu-id="6d8f2-114">Redirigir el mensaje al RNIFReceive.aspx del asociado</span><span class="sxs-lookup"><span data-stu-id="6d8f2-114">Routing the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="6d8f2-115">Devolver un mensaje de señal</span><span class="sxs-lookup"><span data-stu-id="6d8f2-115">Returning a signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d8f2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d8f2-116">See Also</span></span>  
 <span data-ttu-id="6d8f2-117">[Enviar y recibir páginas ASPX](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="6d8f2-117">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="6d8f2-118">Ejemplos de aplicaciones web</span><span class="sxs-lookup"><span data-stu-id="6d8f2-118">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)