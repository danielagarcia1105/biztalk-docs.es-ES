---
title: RNIFSend | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 780f7446-56c5-40bf-95e2-25d0cff12f12
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d9aca64afee9ed979b2eee58a5f2bdafb25b461
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011605"
---
# <a name="rnifsend"></a><span data-ttu-id="67dac-102">RNIFSend</span><span class="sxs-lookup"><span data-stu-id="67dac-102">RNIFSend</span></span>
<span data-ttu-id="67dac-103">Este ejemplo proporciona un Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] archivo RNIFSend.aspx que prepara un mensaje para el procesamiento de RNIF y envía el mensaje a la página de trabajo RNIFReceive.aspx en el servicio de respuesta.</span><span class="sxs-lookup"><span data-stu-id="67dac-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx file that prepares a message for RNIF processing, and sends the message to the RNIFReceive.aspx page at the responder.</span></span> <span data-ttu-id="67dac-104">Puede personalizar la página ASPX para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="67dac-104">You can customize the ASPX page to do the following:</span></span>  
  
- <span data-ttu-id="67dac-105">Agregar o quitar los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="67dac-105">Add or remove performance counters</span></span>  
  
- <span data-ttu-id="67dac-106">Agregar funciones a la página, como escribir datos en una base de datos o personalizar la función de seguimiento</span><span class="sxs-lookup"><span data-stu-id="67dac-106">Add functionality to the page, such as writing data to a database or customizing tracking functionality</span></span>  
  
- <span data-ttu-id="67dac-107">Agregar validación a la página</span><span class="sxs-lookup"><span data-stu-id="67dac-107">Add validation to the page</span></span>  
  
  <span data-ttu-id="67dac-108">Este ejemplo se encuentra en  *\<unidad\>*: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\WebApplication\RNIFSender.</span><span class="sxs-lookup"><span data-stu-id="67dac-108">This sample is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\WebApplication\RNIFSender.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="67dac-109">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="67dac-109">Demonstrates</span></span>  
 <span data-ttu-id="67dac-110">Este ejemplo muestra cómo preparar los mensajes salientes para RNIF procesar, incluido lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="67dac-110">This sample demonstrates how to prepare outgoing messages for RNIF processing, including the following:</span></span>  
  
-   <span data-ttu-id="67dac-111">Validación de los datos para el encabezado MIME</span><span class="sxs-lookup"><span data-stu-id="67dac-111">Validating the data for the MIME header</span></span>  
  
-   <span data-ttu-id="67dac-112">Agregar un encabezado MIME y límites MIME al mensaje</span><span class="sxs-lookup"><span data-stu-id="67dac-112">Adding a MIME header and MIME boundaries to the message</span></span>  
  
-   <span data-ttu-id="67dac-113">Enviar el mensaje al RNIFReceive.aspx del asociado</span><span class="sxs-lookup"><span data-stu-id="67dac-113">Sending the message to the partner's RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="67dac-114">Procesar un mensaje de señal devuelta</span><span class="sxs-lookup"><span data-stu-id="67dac-114">Processing a returned signal message</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67dac-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="67dac-115">See Also</span></span>  
 <span data-ttu-id="67dac-116">[Enviar y recibir páginas ASPX](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span><span class="sxs-lookup"><span data-stu-id="67dac-116">[Send and Receive ASPX Pages](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md) </span></span>  
 [<span data-ttu-id="67dac-117">Ejemplos de aplicaciones web</span><span class="sxs-lookup"><span data-stu-id="67dac-117">Web Application Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)