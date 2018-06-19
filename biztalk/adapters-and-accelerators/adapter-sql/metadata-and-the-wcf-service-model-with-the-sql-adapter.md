---
title: Metadatos y el modelo de servicio de WCF con el adaptador de SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4353ce67-f0e8-4f96-b1d9-95deeee7f3e6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95ed3188c01f0f6d568bd745decd9e601e6ee3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222436"
---
# <a name="metadata-and-the-wcf-service-model-with-the-sql-adapter"></a><span data-ttu-id="22e35-102">Metadatos y el modelo de servicio de WCF con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="22e35-102">Metadata and the WCF Service Model with the SQL adapter</span></span>
<span data-ttu-id="22e35-103">En el modelo de servicio WCF, use el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutile.exe) para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22e35-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to do the following:</span></span>  
  
-   <span data-ttu-id="22e35-104">Generar un contrato de servicio, el contrato de servicio WCF: a través del cual el código puede operaciones de recepción del adaptador.</span><span class="sxs-lookup"><span data-stu-id="22e35-104">Generate a service contract—the WCF service contract—through which your code can receive operations from the adapter.</span></span> <span data-ttu-id="22e35-105">Esta interfaz .NET representa el contrato de servicio para las operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="22e35-105">This .NET interface represents the service contract for target operations.</span></span>  
  
-   <span data-ttu-id="22e35-106">Generar clases de proxy, la clase de cliente WCF: a través del cual el código puede invocar las operaciones en el adaptador.</span><span class="sxs-lookup"><span data-stu-id="22e35-106">Generate proxy classes—the WCF client class—through which your code can invoke operations on the adapter.</span></span>  
  
-   <span data-ttu-id="22e35-107">Anotado clases que representan los auxiliares contratos de mensaje, los contratos de operación y los contratos de datos para el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="22e35-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
 <span data-ttu-id="22e35-108">Para obtener ayuda acerca de la estructura de este código generado, consulte [comprensión de código de cliente generado](https://msdn.microsoft.com/library/ms733881.aspx).</span><span class="sxs-lookup"><span data-stu-id="22e35-108">For help in understanding the structure of this generated code, see [Understanding Generated Client Code](https://msdn.microsoft.com/library/ms733881.aspx).</span></span> <span data-ttu-id="22e35-109">Este tema describe específicamente código que genera svcutil.exe, pero su contenido también es aplicable al código que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="22e35-109">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
 <span data-ttu-id="22e35-110">Para obtener información acerca de cómo generar una clase de cliente WCF o el contrato de servicio WCF para las operaciones de destino y las diferencias entre svcutil.exe y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server ](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="22e35-110">For information about how to generate a WCF client class or WCF service contract for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e35-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="22e35-111">See Also</span></span>  
[<span data-ttu-id="22e35-112">Desarrollar aplicaciones de SQL con el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="22e35-112">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)