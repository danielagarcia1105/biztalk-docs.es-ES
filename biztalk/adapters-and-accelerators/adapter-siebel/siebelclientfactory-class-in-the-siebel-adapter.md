---
title: Clase SiebelClientFactory en el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelClientFactory
- Data Provider for Siebel, SiebelClientFactory
- SiebelClientFactory, supported properties and methods
ms.assetid: f3a807d3-a030-47d8-b145-e18075ec353c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50e47b22c1d5a2575b0da3fae432acd79886e2c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222068"
---
# <a name="siebelclientfactory-class-in-the-siebel-adapter"></a><span data-ttu-id="d4a15-102">Clase SiebelClientFactory en el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="d4a15-102">SiebelClientFactory class in the Siebel adapter</span></span>
<span data-ttu-id="d4a15-103">Un cliente ADO.NET tiene acceso a la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] con interfaces y clases ADO.NET genéricas.</span><span class="sxs-lookup"><span data-stu-id="d4a15-103">An ADO.NET client accesses the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] using generic ADO.NET classes and interfaces.</span></span> <span data-ttu-id="d4a15-104">Para habilitar esta característica, el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] hereda el **System.Data.Common.DbProviderFactory** clase.</span><span class="sxs-lookup"><span data-stu-id="d4a15-104">To enable this feature, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] inherits the **System.Data.Common.DbProviderFactory** class.</span></span> <span data-ttu-id="d4a15-105">El programa cliente consume al cliente como sigue:</span><span class="sxs-lookup"><span data-stu-id="d4a15-105">The client program consumes the client as follows:</span></span>  
  
```  
  
DbProviderFactory factory = DbProviderFactories.GetFactory("Microsoft.Data.SiebelClient");  
DbConnection connection = factory.CreateConnection();  
```  
  
 <span data-ttu-id="d4a15-106">Un enfoque alternativo es como sigue:</span><span class="sxs-lookup"><span data-stu-id="d4a15-106">An alternative approach is as follows:</span></span>  
  
```  
SiebelClientFactory factory = SiebelClientFactory.Instance;  
DbConnection connection = factory.CreateConnection();  
```  
  
 <span data-ttu-id="d4a15-107">SiebelClientFactory existe en el espacio de nombres Microsoft.Data.SiebelClient.</span><span class="sxs-lookup"><span data-stu-id="d4a15-107">SiebelClientFactory exists in the namespace Microsoft.Data.SiebelClient.</span></span>  
  
## <a name="supported-members"></a><span data-ttu-id="d4a15-108">Miembros admitidos</span><span class="sxs-lookup"><span data-stu-id="d4a15-108">Supported Members</span></span>  
 <span data-ttu-id="d4a15-109">**SiebelClientFactory** extiende **System.Data.CommonDbProviderFactory**.</span><span class="sxs-lookup"><span data-stu-id="d4a15-109">**SiebelClientFactory** extends **System.Data.CommonDbProviderFactory**.</span></span>  <span data-ttu-id="d4a15-110">En la tabla siguiente proporciona una descripción de los miembros que **SiebelClientFactory** invalida.</span><span class="sxs-lookup"><span data-stu-id="d4a15-110">The following table provides a description of the members that **SiebelClientFactory** overrides.</span></span>  
  
|<span data-ttu-id="d4a15-111">Nombre</span><span class="sxs-lookup"><span data-stu-id="d4a15-111">Name</span></span>|<span data-ttu-id="d4a15-112">Description</span><span class="sxs-lookup"><span data-stu-id="d4a15-112">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d4a15-113">**Instancia**</span><span class="sxs-lookup"><span data-stu-id="d4a15-113">**Instance**</span></span>|<span data-ttu-id="d4a15-114">Se trata de una variable de miembro.</span><span class="sxs-lookup"><span data-stu-id="d4a15-114">This is a member variable.</span></span>  <span data-ttu-id="d4a15-115">Proporciona una instancia de singleton de SiebelClientFactory.</span><span class="sxs-lookup"><span data-stu-id="d4a15-115">It provides a singleton instance of SiebelClientFactory.</span></span>|  
|<span data-ttu-id="d4a15-116">**CreateCommand()**</span><span class="sxs-lookup"><span data-stu-id="d4a15-116">**CreateCommand()**</span></span>|<span data-ttu-id="d4a15-117">Crea una instancia de SiebelCommand.</span><span class="sxs-lookup"><span data-stu-id="d4a15-117">Creates an instance of SiebelCommand.</span></span>|  
|<span data-ttu-id="d4a15-118">**CreateConnection()**</span><span class="sxs-lookup"><span data-stu-id="d4a15-118">**CreateConnection()**</span></span>|<span data-ttu-id="d4a15-119">Crea una instancia de SiebelConnection.</span><span class="sxs-lookup"><span data-stu-id="d4a15-119">Creates an instance of SiebelConnection.</span></span>|  
|<span data-ttu-id="d4a15-120">**CreateConnectionStringBuilder()**</span><span class="sxs-lookup"><span data-stu-id="d4a15-120">**CreateConnectionStringBuilder()**</span></span>|<span data-ttu-id="d4a15-121">Crea una instancia de SiebelConnectionStringBuilder.</span><span class="sxs-lookup"><span data-stu-id="d4a15-121">Creates an instance of SiebelConnectionStringBuilder.</span></span>|  
|<span data-ttu-id="d4a15-122">**CreateParameter()**</span><span class="sxs-lookup"><span data-stu-id="d4a15-122">**CreateParameter()**</span></span>|<span data-ttu-id="d4a15-123">Crea una instancia de SiebelParameter.</span><span class="sxs-lookup"><span data-stu-id="d4a15-123">Creates an instance of SiebelParameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4a15-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4a15-124">See Also</span></span>  
 [<span data-ttu-id="d4a15-125">Extender Interfaces de ADO.NET con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="d4a15-125">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)