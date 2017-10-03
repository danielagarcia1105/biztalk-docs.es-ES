---
title: Clase SAPClientFactory en el adaptador SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPClientFactory, supported methods and classes
ms.assetid: e64de5e4-e53f-4708-ab02-9e12774e94cd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c82e4bea6a16085608ebf1f8fe10ea95b4db394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sapclientfactory-class-in-the-sap-adapter"></a><span data-ttu-id="67bfd-102">Clase SAPClientFactory en el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="67bfd-102">SAPClientFactory class in the SAP adapter</span></span>
<span data-ttu-id="67bfd-103">En la siguiente sección se enumera los métodos y propiedades para la **SAPClientFactory** clase.</span><span class="sxs-lookup"><span data-stu-id="67bfd-103">The following section lists the methods and properties for the **SAPClientFactory** class.</span></span> <span data-ttu-id="67bfd-104">Esto se deriva de **System.Data.Common.DbProviderFactory**.</span><span class="sxs-lookup"><span data-stu-id="67bfd-104">This is derived from **System.Data.Common.DbProviderFactory**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="67bfd-105">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="67bfd-105">Supported Properties</span></span>  
  
|<span data-ttu-id="67bfd-106">Nombre</span><span class="sxs-lookup"><span data-stu-id="67bfd-106">Name</span></span>|<span data-ttu-id="67bfd-107">Get/Set.</span><span class="sxs-lookup"><span data-stu-id="67bfd-107">Get/Set</span></span>|<span data-ttu-id="67bfd-108">Description</span><span class="sxs-lookup"><span data-stu-id="67bfd-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="67bfd-109">**Instancia**</span><span class="sxs-lookup"><span data-stu-id="67bfd-109">**Instance**</span></span>|-|<span data-ttu-id="67bfd-110">Instancia de singleton de SAPClientFactory</span><span class="sxs-lookup"><span data-stu-id="67bfd-110">Singleton instance of SAPClientFactory</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="67bfd-111">Métodos admitidos</span><span class="sxs-lookup"><span data-stu-id="67bfd-111">Supported Methods</span></span>  
  
|<span data-ttu-id="67bfd-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="67bfd-112">Name</span></span>|<span data-ttu-id="67bfd-113">Description</span><span class="sxs-lookup"><span data-stu-id="67bfd-113">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="67bfd-114">**CreateCommand()**</span><span class="sxs-lookup"><span data-stu-id="67bfd-114">**CreateCommand()**</span></span>|<span data-ttu-id="67bfd-115">Crea una instancia de SAPCommand</span><span class="sxs-lookup"><span data-stu-id="67bfd-115">Creates an instance of SAPCommand</span></span>|  
|<span data-ttu-id="67bfd-116">**CreateConnection()**</span><span class="sxs-lookup"><span data-stu-id="67bfd-116">**CreateConnection()**</span></span>|<span data-ttu-id="67bfd-117">Crea una instancia de SAPConnection</span><span class="sxs-lookup"><span data-stu-id="67bfd-117">Creates an instance of SAPConnection</span></span>|  
|<span data-ttu-id="67bfd-118">**CreateConnectionStringBuilder()**</span><span class="sxs-lookup"><span data-stu-id="67bfd-118">**CreateConnectionStringBuilder()**</span></span>|<span data-ttu-id="67bfd-119">Crea una instancia de SAPConnectionStringBuilder</span><span class="sxs-lookup"><span data-stu-id="67bfd-119">Creates an instance of SAPConnectionStringBuilder</span></span>|  
|<span data-ttu-id="67bfd-120">**CreateParameter()**</span><span class="sxs-lookup"><span data-stu-id="67bfd-120">**CreateParameter()**</span></span>|<span data-ttu-id="67bfd-121">Crea una instancia de SAPParameter</span><span class="sxs-lookup"><span data-stu-id="67bfd-121">Creates an instance of SAPParameter</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67bfd-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="67bfd-122">See Also</span></span>  
 [<span data-ttu-id="67bfd-123">Extender Interfaces de ADO.NET con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="67bfd-123">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)