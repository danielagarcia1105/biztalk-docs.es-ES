---
title: WCF y metadatos de servicio modelo con Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, metadata
- metadata, and the WCF service model
ms.assetid: 3aca1835-fb9e-4841-a920-078da0b3fe76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb47a69efc6522eb6868ce2ecda5c608d2652c99
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752788"
---
# <a name="metadata-and-the-wcf-service-model-with-siebel"></a><span data-ttu-id="d59a3-102">Los metadatos y el modelo de servicio WCF con Siebel</span><span class="sxs-lookup"><span data-stu-id="d59a3-102">Metadata and the WCF Service Model with Siebel</span></span>
<span data-ttu-id="d59a3-103">En el modelo de servicio WCF, se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutile.exe) para generar una clase de proxy, la clase de cliente WCF: a través de que el código puede invocar operaciones en el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d59a3-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate a proxy class—the WCF client class—through which your code can invoke operations on the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
 <span data-ttu-id="d59a3-104">Estas herramientas usan los metadatos expuestos por el adaptador para generar:</span><span class="sxs-lookup"><span data-stu-id="d59a3-104">These tools use the metadata exposed by the adapter to generate:</span></span>  
  
- <span data-ttu-id="d59a3-105">Una interfaz .NET anotada que representa el contrato de servicio para las operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="d59a3-105">An annotated .NET interface that represents the service contract for target operations.</span></span> <span data-ttu-id="d59a3-106">Esta interfaz se denomina el contrato de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="d59a3-106">This interface is called the WCF service contract.</span></span>  
  
- <span data-ttu-id="d59a3-107">Anotado clases que representan el apoyo de los contratos de mensaje, contratos de operación y contratos de datos para el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="d59a3-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
- <span data-ttu-id="d59a3-108">Una clase de cliente WCF cuyos métodos pueden usarse para invocar los métodos de servicio (operaciones) expuestos por el contrato de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="d59a3-108">A WCF client class whose methods can be used to invoke the service methods (operations) exposed by the WCF service contract.</span></span>  
  
  <span data-ttu-id="d59a3-109">Para obtener ayuda acerca de la estructura de este genera código, vea "Descripción genera código de cliente" en [ http://go.microsoft.com/fwlink/?LinkId=98365 ](http://go.microsoft.com/fwlink/?LinkId=98365).</span><span class="sxs-lookup"><span data-stu-id="d59a3-109">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="d59a3-110">Este tema describe específicamente a código que genera svcutil.exe, pero su contenido también es aplicable al código que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="d59a3-110">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="d59a3-111">Para obtener información acerca de cómo generar una clase de cliente WCF para las operaciones de destino y las diferencias entre svcutil.exe y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de solución de Siebel](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)</span><span class="sxs-lookup"><span data-stu-id="d59a3-111">For information about how to generate a WCF client class for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF service contract for Siebel solution Artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d59a3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d59a3-112">See Also</span></span>  
 [<span data-ttu-id="d59a3-113">Desarrollar aplicaciones de Siebel mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="d59a3-113">Develop Siebel applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)
