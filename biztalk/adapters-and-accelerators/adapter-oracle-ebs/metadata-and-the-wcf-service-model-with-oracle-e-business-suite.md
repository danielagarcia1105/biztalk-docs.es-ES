---
title: WCF y metadatos de servicio modelo con Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95d3fcba-c72f-4ae9-82bd-abbfc2a0c2c4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c076d13e0adc32352c85901541d2be46b5fcd2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997845"
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-e-business-suite"></a><span data-ttu-id="ca031-102">Los metadatos y el modelo de servicio WCF con Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="ca031-102">Metadata and the WCF Service Model with Oracle E-Business Suite</span></span>
<span data-ttu-id="ca031-103">En el modelo de servicio WCF, se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutile.exe) para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ca031-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to do the following:</span></span>  
  
- <span data-ttu-id="ca031-104">Generar un contrato de servicio, el contrato de servicio WCF: a través del cual el código puede recibir operaciones desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca031-104">Generate a service contract—the WCF service contract—through which your code can receive operations from the adapter.</span></span> <span data-ttu-id="ca031-105">Esta interfaz .NET representa el contrato de servicio para las operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="ca031-105">This .NET interface represents the service contract for target operations.</span></span>  
  
- <span data-ttu-id="ca031-106">Generar clases de proxy, la clase de cliente WCF: a través del cual el código puede invocar operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca031-106">Generate proxy classes—the WCF client class—through which your code can invoke operations on the adapter.</span></span>  
  
- <span data-ttu-id="ca031-107">Anotado clases que representan el apoyo de los contratos de mensaje, contratos de operación y contratos de datos para el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="ca031-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
  <span data-ttu-id="ca031-108">Para obtener ayuda acerca de la estructura de este genera código, vea "Descripción genera código de cliente" en [ http://go.microsoft.com/fwlink/?LinkId=98365 ](http://go.microsoft.com/fwlink/?LinkId=98365).</span><span class="sxs-lookup"><span data-stu-id="ca031-108">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="ca031-109">Este tema describe específicamente a código que genera svcutil.exe, pero su contenido también es aplicable al código que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="ca031-109">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="ca031-110">Para obtener información acerca de cómo generar una clase de cliente WCF o el contrato de servicio WCF para las operaciones de destino y las diferencias entre svcutil.exe y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF para Oracle E-Business Artefactos de la solución Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="ca031-110">For information about how to generate a WCF client class or WCF service contract for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF Service Contract for Oracle E-Business Suite Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca031-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca031-111">See Also</span></span>  
 [<span data-ttu-id="ca031-112">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="ca031-112">Develop Oracle E-Business Suite Applications by Using the WCF service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)