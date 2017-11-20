---
title: Con la herramienta de Microsoft BizTalk LoadGen 2007 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LoadGen tool, how to
- LoadGen tool, test environments
ms.assetid: d1973a26-1c98-4261-bd9a-6357cdb19ccf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b93018f093bbdffed64c44060f445a30d37344c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-microsoft-biztalk-loadgen-2007-tool"></a><span data-ttu-id="f1450-102">Uso de la herramienta de Microsoft BizTalk LoadGen 2007</span><span class="sxs-lookup"><span data-stu-id="f1450-102">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>
<span data-ttu-id="f1450-103">La herramienta Microsoft BizTalk LoadGen 2007 está diseñada para aquellos programadores y profesionales de TI que deseen simular cargas en un servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f1450-103">The Microsoft BizTalk LoadGen 2007 Tool is intended for developers and IT professionals to simulate load on a BizTalk Server.</span></span> <span data-ttu-id="f1450-104">Gracias a ella, en una implementación de BizTalk es posible simular la carga que se produce en la fuerza y el rendimiento de los instrumentos.</span><span class="sxs-lookup"><span data-stu-id="f1450-104">Using this tool, you can simulate load to instrument performance and stress against a BizTalk deployment.</span></span> <span data-ttu-id="f1450-105">Además, los programadores también podrán utilizarla para simular la carga en transportes personalizados.</span><span class="sxs-lookup"><span data-stu-id="f1450-105">In addition, this tool may also be extended by developers to simulate load for custom transports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1450-106">La herramienta LoadGen 2007 está disponible para su descarga en [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).</span><span class="sxs-lookup"><span data-stu-id="f1450-106">The LoadGen 2007 tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841).</span></span> <span data-ttu-id="f1450-107">La versión anterior de esta herramienta, la herramienta de generación de cargas de BizTalk Server 2004 está disponible para su descarga en [http://go.microsoft.com/fwlink/?LinkId=108999](http://go.microsoft.com/fwlink/?LinkId=108999).</span><span class="sxs-lookup"><span data-stu-id="f1450-107">The previous version of this tool, the BizTalk Server 2004 Load Generation Tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=108999](http://go.microsoft.com/fwlink/?LinkId=108999).</span></span>  
  
 <span data-ttu-id="f1450-108">Esta herramienta solo debe emplearse en un entorno de prueba, no en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="f1450-108">This tool should be used in a test environment only, and should not be used in a production environment.</span></span> <span data-ttu-id="f1450-109">Esta herramienta se suministra "como está", pero no incluye soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="f1450-109">This tool is provided "as-is" and is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1450-110">Puede usarse la herramienta para generación de cargas de BizTalk Server 2004 con el adaptador MSMQ, pero serán necesarios algunos pasos adicionales.</span><span class="sxs-lookup"><span data-stu-id="f1450-110">You can use BizTalk Server 2004 Load Generation Tool with the MSMQ adapter, but you must do some additional steps.</span></span> <span data-ttu-id="f1450-111">Para obtener instrucciones, consulte [uso de LoadGen 2007 con MSMQ](../core/using-loadgen-2007-with-msmq.md).</span><span class="sxs-lookup"><span data-stu-id="f1450-111">For instructions, see [Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1450-112">LoadGen no es compatible con equipos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f1450-112">LoadGen is not supported on 64-bit computers.</span></span> <span data-ttu-id="f1450-113">Puede utilizar LoadGen de forma remota en un equipo de 32 bits para generar cargas en un servidor de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f1450-113">You can use LoadGen remotely running on a 32-bit computer to generate load against a 64-bit server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1450-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1450-114">See Also</span></span>  
 [<span data-ttu-id="f1450-115">Prueba de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="f1450-115">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)