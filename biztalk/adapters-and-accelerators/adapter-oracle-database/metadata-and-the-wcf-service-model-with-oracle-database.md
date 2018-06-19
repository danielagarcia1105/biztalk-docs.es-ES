---
title: Modelo con la base de datos de Oracle del servicio WCF y metadatos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service model, metadata
- WCF client class
- WCF service contract
ms.assetid: b55cf4ed-c41a-4986-bbaf-88e80c32b01f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76933dba64e6e8bb75eb0394ab8e6eedd3fb7116
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214980"
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-database"></a><span data-ttu-id="b30b3-102">Metadatos y el modelo de servicio WCF con la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="b30b3-102">Metadata and the WCF Service Model with Oracle Database</span></span>
<span data-ttu-id="b30b3-103">En el modelo de servicio WCF, use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. o bien el ServiceModel Metadata Utility Tool (svcutile.exe) para generar clases de proxy a través del cual el código puede:</span><span class="sxs-lookup"><span data-stu-id="b30b3-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate proxy classes through which your code can either:</span></span>  
  
-   <span data-ttu-id="b30b3-104">Invocar las operaciones en el adaptador (una clase de cliente WCF)</span><span class="sxs-lookup"><span data-stu-id="b30b3-104">Invoke operations on the adapter (a WCF client class)</span></span>  
  
-   <span data-ttu-id="b30b3-105">Operaciones de recepción del adaptador (un contrato de servicio WCF)</span><span class="sxs-lookup"><span data-stu-id="b30b3-105">Receive operations from the adapter (a WCF service contract)</span></span>  
  
 <span data-ttu-id="b30b3-106">Estas herramientas generan clases de .NET que representan un contrato de servicio para las operaciones de destino (así como el apoyo de los contratos de mensaje, contratos de operación y contratos de datos) de los metadatos expuestos por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b30b3-106">These tools generate .NET classes that represent a service contract for target operations (as well as the supporting message contracts, operation contracts, and data contracts) from the metadata exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="b30b3-107">Para obtener ayuda acerca de la estructura de este genera código, vea "Introducción al código cliente generado" en [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span><span class="sxs-lookup"><span data-stu-id="b30b3-107">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="b30b3-108">Este tema describe específicamente código que genera svcutil.exe, pero su contenido también es aplicable al código que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="b30b3-108">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span> <span data-ttu-id="b30b3-109">Para obtener información acerca de cómo generar una clase de cliente WCF o el contrato de servicio WCF para las operaciones de destino y las diferencias entre svcutil.exe y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio de WCF para base de datos de Oracle Artefactos de la solución](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="b30b3-109">For information about how to generate a WCF client class or WCF service contract for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b30b3-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b30b3-110">See Also</span></span>  
 [<span data-ttu-id="b30b3-111">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="b30b3-111">Develop Oracle Database Applications by Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)