---
title: Archivo de configuración de interceptor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 490f5607-e7f6-4f7f-9121-1070db32a7cf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bb4a57272ebae5b831552d9446dbdbc937dca1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256924"
---
# <a name="interceptor-configuration-file"></a><span data-ttu-id="3d720-102">Archivo de configuración de interceptor</span><span class="sxs-lookup"><span data-stu-id="3d720-102">Interceptor Configuration File</span></span>
<span data-ttu-id="3d720-103">Los interceptores de BAM para Windows Workflow Foundation y Windows Communication Foundation se basan en un archivo de configuración de interceptor para determinar los eventos y elementos de fecha que se van a interceptar.</span><span class="sxs-lookup"><span data-stu-id="3d720-103">The BAM interceptors for Windows Workflow Foundation and Windows Communication Foundation rely on an interceptor configuration file to determine what events and date elements to intercept.</span></span> <span data-ttu-id="3d720-104">El archivo de configuración es XML y se define mediante el esquema de configuración de interceptor y el esquema de Windows Workflow Foundation o el esquema de Windows Communication Framework en función de la tecnología que se va a especificar.</span><span class="sxs-lookup"><span data-stu-id="3d720-104">The configuration file is XML and is defined by the interceptor configuration schema and either the Windows Workflow Foundation schema or the Windows Communication Framework schema depending upon which technology you are targeting.</span></span>  
  
 <span data-ttu-id="3d720-105">Esta sección se centra en la configuración del interceptor base que incluye elementos y atributos.</span><span class="sxs-lookup"><span data-stu-id="3d720-105">This section focuses on the base interceptor configuration including elements and attributes.</span></span> <span data-ttu-id="3d720-106">Los interceptores específicos de la tecnología proporcionan la funcionalidad adicional y se explican en secciones individuales.</span><span class="sxs-lookup"><span data-stu-id="3d720-106">Additional functionality is provided by the technology-specific interceptors and are explained in separate sections.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d720-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3d720-107">In This Section</span></span>  
  
-   [<span data-ttu-id="3d720-108">Usar IntelliSense para crear un archivo de configuración de Interceptor</span><span class="sxs-lookup"><span data-stu-id="3d720-108">Using IntelliSense to Create an Interceptor Configuration File</span></span>](../core/using-intellisense-to-create-an-interceptor-configuration-file.md)  
  
-   [<span data-ttu-id="3d720-109">Esquema de configuración de interceptor</span><span class="sxs-lookup"><span data-stu-id="3d720-109">Interceptor Configuration Schema</span></span>](../core/interceptor-configuration-schema.md)  
  
-   [<span data-ttu-id="3d720-110">Estructura de un archivo de configuración de Interceptor</span><span class="sxs-lookup"><span data-stu-id="3d720-110">Structure of an Interceptor Configuration File</span></span>](../core/structure-of-an-interceptor-configuration-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="3d720-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d720-111">See Also</span></span>  
 <span data-ttu-id="3d720-112">[Interceptor de WF de BAM](../core/bam-wf-interceptor.md) </span><span class="sxs-lookup"><span data-stu-id="3d720-112">[BAM WF Interceptor](../core/bam-wf-interceptor.md) </span></span>  
 [<span data-ttu-id="3d720-113">Interceptor de WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="3d720-113">BAM WCF Interceptor</span></span>](../core/bam-wcf-interceptor.md)