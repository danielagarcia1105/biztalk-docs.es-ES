---
title: Modelo con SAP de servicio de WCF y metadatos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1900cf66-a0d0-46f4-896b-7f6de3b51875
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e4a3ca75470192f2237cf67c6ac0312b150b46a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972837"
---
# <a name="metadata-and-the-wcf-service-model-with-sap"></a><span data-ttu-id="93d30-102">Los metadatos y el modelo de servicio WCF con SAP</span><span class="sxs-lookup"><span data-stu-id="93d30-102">Metadata and the WCF Service Model with SAP</span></span>
<span data-ttu-id="93d30-103">En el modelo de servicio WCF, se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].o el ServiceModel Metadata Utility Tool (svcutile.exe) para generar clases de proxy a través del cual el código puede:</span><span class="sxs-lookup"><span data-stu-id="93d30-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate proxy classes through which your code can either:</span></span>  
  
- <span data-ttu-id="93d30-104">Invocar operaciones en el adaptador (una clase de cliente WCF)</span><span class="sxs-lookup"><span data-stu-id="93d30-104">Invoke operations on the adapter (a WCF client class)</span></span>  
  
- <span data-ttu-id="93d30-105">Operaciones de recepción del adaptador (un contrato de servicio WCF)</span><span class="sxs-lookup"><span data-stu-id="93d30-105">Receive operations from the adapter (a WCF service contract)</span></span>  
  
  <span data-ttu-id="93d30-106">Estas herramientas generan clases de .NET que representan un contrato de servicio para las operaciones de destino (así como el apoyo de los contratos de mensaje, los contratos de operación y los contratos de datos) de los metadatos expuestos por el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93d30-106">These tools generate .NET classes that represent a service contract for target operations (as well as the supporting message contracts, operation contracts, and data contracts) from the metadata exposed by the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span> <span data-ttu-id="93d30-107">Para obtener ayuda acerca de la estructura de este código generado, vea [comprensión de código de cliente generado](https://msdn.microsoft.com/library/ms733881.aspx).</span><span class="sxs-lookup"><span data-stu-id="93d30-107">For help in understanding the structure of this generated code, see [Understanding Generated Client Code](https://msdn.microsoft.com/library/ms733881.aspx).</span></span> <span data-ttu-id="93d30-108">Este tema describe específicamente a código que genera svcutil.exe, pero su contenido también es aplicable al código que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="93d30-108">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span> <span data-ttu-id="93d30-109">Para obtener información acerca de cómo generar una clase de cliente WCF o el contrato de servicio WCF (interfaz) para las operaciones de destino y las diferencias entre svcutil.exe y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF para SAP artefactos de la solución](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="93d30-109">For information about how to generate a WCF client class or WCF service contract (interface) for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d30-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="93d30-110">See Also</span></span>  
[<span data-ttu-id="93d30-111">Desarrollar aplicaciones de SAP mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="93d30-111">Develop SAP applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)