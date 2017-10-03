---
title: Clase SAPDataReader en el adaptador SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPDataReader, supported methods and classes
ms.assetid: bd0e55ea-7413-498f-851f-ed97bd8bacab
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70fe658058b6d00b4a22b333ef5683a285b9cab3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sapdatareader-class-in-the-sap-adapter"></a><span data-ttu-id="3734b-102">Clase SAPDataReader en el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="3734b-102">SAPDataReader class in the SAP adapter</span></span>
<span data-ttu-id="3734b-103">En la siguiente sección se enumera los métodos y propiedades para la **SAPDataReader** clase.</span><span class="sxs-lookup"><span data-stu-id="3734b-103">The following section lists the methods and properties for the **SAPDataReader** class.</span></span> <span data-ttu-id="3734b-104">Esto se deriva de **System.Data.Common.DbDataReader**.</span><span class="sxs-lookup"><span data-stu-id="3734b-104">This is derived from **System.Data.Common.DbDataReader**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="3734b-105">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="3734b-105">Supported Properties</span></span>  
  
|<span data-ttu-id="3734b-106">Nombre</span><span class="sxs-lookup"><span data-stu-id="3734b-106">Name</span></span>|<span data-ttu-id="3734b-107">Get/Set.</span><span class="sxs-lookup"><span data-stu-id="3734b-107">Get/Set</span></span>|<span data-ttu-id="3734b-108">Description</span><span class="sxs-lookup"><span data-stu-id="3734b-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="3734b-109">**Profundidad**</span><span class="sxs-lookup"><span data-stu-id="3734b-109">**Depth**</span></span>|<span data-ttu-id="3734b-110">Obtener</span><span class="sxs-lookup"><span data-stu-id="3734b-110">Get</span></span>|<span data-ttu-id="3734b-111">No compatible.</span><span class="sxs-lookup"><span data-stu-id="3734b-111">Not supported.</span></span> <span data-ttu-id="3734b-112">Devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="3734b-112">Returns 0.</span></span>|  
|<span data-ttu-id="3734b-113">**FieldCount**</span><span class="sxs-lookup"><span data-stu-id="3734b-113">**FieldCount**</span></span>|<span data-ttu-id="3734b-114">Obtener</span><span class="sxs-lookup"><span data-stu-id="3734b-114">Get</span></span>|<span data-ttu-id="3734b-115">Número de campos en el conjunto de registros actual</span><span class="sxs-lookup"><span data-stu-id="3734b-115">Number of fields in the current record set</span></span>|  
|<span data-ttu-id="3734b-116">**IsClosed**</span><span class="sxs-lookup"><span data-stu-id="3734b-116">**IsClosed**</span></span>|<span data-ttu-id="3734b-117">Obtener</span><span class="sxs-lookup"><span data-stu-id="3734b-117">Get</span></span>|<span data-ttu-id="3734b-118">Devuelve el estado del lector de datos</span><span class="sxs-lookup"><span data-stu-id="3734b-118">Returns status of data reader</span></span>|  
|<span data-ttu-id="3734b-119">**RecordsAffected**</span><span class="sxs-lookup"><span data-stu-id="3734b-119">**RecordsAffected**</span></span>|<span data-ttu-id="3734b-120">Obtener</span><span class="sxs-lookup"><span data-stu-id="3734b-120">Get</span></span>|<span data-ttu-id="3734b-121">No compatible.</span><span class="sxs-lookup"><span data-stu-id="3734b-121">Not supported.</span></span> <span data-ttu-id="3734b-122">Devuelve -1</span><span class="sxs-lookup"><span data-stu-id="3734b-122">Returns -1</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="3734b-123">Métodos admitidos</span><span class="sxs-lookup"><span data-stu-id="3734b-123">Supported Methods</span></span>  
  
|<span data-ttu-id="3734b-124">Nombre</span><span class="sxs-lookup"><span data-stu-id="3734b-124">Name</span></span>|<span data-ttu-id="3734b-125">Description</span><span class="sxs-lookup"><span data-stu-id="3734b-125">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="3734b-126">**Close()**</span><span class="sxs-lookup"><span data-stu-id="3734b-126">**Close()**</span></span>|<span data-ttu-id="3734b-127">Cierra el DataReader</span><span class="sxs-lookup"><span data-stu-id="3734b-127">Closes the DataReader</span></span>|  
|<span data-ttu-id="3734b-128">**Obtener [métodos]**<sup>*</sup></span><span class="sxs-lookup"><span data-stu-id="3734b-128">**Get [methods]** <sup>*</sup></span></span><br /><br /> <span data-ttu-id="3734b-129">donde [métodos] es el tipo de datos esperado.</span><span class="sxs-lookup"><span data-stu-id="3734b-129">where [methods] is the expected data type.</span></span> <span data-ttu-id="3734b-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3734b-130">E.g.</span></span> <span data-ttu-id="3734b-131">GetInt32(int)</span><span class="sxs-lookup"><span data-stu-id="3734b-131">GetInt32(int)</span></span>|<span data-ttu-id="3734b-132">Obtiene el valor de la columna en función del tipo de datos esperado</span><span class="sxs-lookup"><span data-stu-id="3734b-132">Gets column value based on the data type expected</span></span>|  
|<span data-ttu-id="3734b-133">**IsDBNull(int)**</span><span class="sxs-lookup"><span data-stu-id="3734b-133">**IsDBNull(int)**</span></span>|<span data-ttu-id="3734b-134">No compatible.</span><span class="sxs-lookup"><span data-stu-id="3734b-134">Not supported.</span></span> <span data-ttu-id="3734b-135">Devuelve false.</span><span class="sxs-lookup"><span data-stu-id="3734b-135">Returns false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3734b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="3734b-136">See Also</span></span>  
 [<span data-ttu-id="3734b-137">Extender Interfaces de ADO.NET con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="3734b-137">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)