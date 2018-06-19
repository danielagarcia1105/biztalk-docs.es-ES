---
title: Problemas conocidos con el adaptador de POP3 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6d621a2-4801-44fe-a266-d4c05ac82633
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bc86b2ae14b04b160f7387f870615116e659b3f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261948"
---
# <a name="known-issues-with-the-pop3-adapter"></a><span data-ttu-id="c5e3c-102">Problemas conocidos del adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="c5e3c-102">Known Issues with the POP3 Adapter</span></span>
<span data-ttu-id="c5e3c-103">Esta sección contiene información que puede servir de ayuda para evitar errores.</span><span class="sxs-lookup"><span data-stu-id="c5e3c-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="c5e3c-104">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="c5e3c-104">Known Issues</span></span>  
  
#### <a name="the-pop3-adapter-fails-to-process-documents-when-running-on-a-64-bit-operating-system"></a><span data-ttu-id="c5e3c-105">Se produce un error en el adaptador de POP3 al procesar documentos cuando se ejecuta en un sistema operativo de 64 bits</span><span class="sxs-lookup"><span data-stu-id="c5e3c-105">The POP3 Adapter fails to process documents when running on a 64 bit operating system</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="c5e3c-106">Problema</span><span class="sxs-lookup"><span data-stu-id="c5e3c-106">Problem</span></span>  
 <span data-ttu-id="c5e3c-107">El adaptador de POP3 no procesará documentos cuando se ejecute en un sistema operativo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c5e3c-107">The POP3 Adapter will not process documents when running on a 64 bit operating system.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="c5e3c-108">Causa</span><span class="sxs-lookup"><span data-stu-id="c5e3c-108">Cause</span></span>  
 <span data-ttu-id="c5e3c-109">El controlador del adaptador de POP3 no puede ejecutarse en una instancia de host de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c5e3c-109">The POP3 Adapter adapter handler is unable to run in a 64 bit host instance.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="c5e3c-110">Solución</span><span class="sxs-lookup"><span data-stu-id="c5e3c-110">Resolution</span></span>  
 <span data-ttu-id="c5e3c-111">Si el adaptador de POP3 se ejecuta en un equipo de 64 bits, configure los controladores del adaptador de POP3 para que se ejecuten en un host de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="c5e3c-111">If you are running the POP3 Adapter on a 64 bit machine, configure the POP3 Adapter handlers to run in a 32 bit host.</span></span> <span data-ttu-id="c5e3c-112">Esta opción está disponible en la página de propiedades de host, a la que se tiene acceso desde la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c5e3c-112">This option is available on the Host Properties page accessible from the BizTalk Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e3c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5e3c-113">See Also</span></span>  
 [<span data-ttu-id="c5e3c-114">Solucionar problemas del adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="c5e3c-114">Troubleshooting the POP3 Adapter</span></span>](../core/troubleshooting-the-pop3-adapter.md)