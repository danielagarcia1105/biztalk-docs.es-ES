---
title: Clase SAPDataReader en el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPDataReader, supported methods and classes
ms.assetid: bd0e55ea-7413-498f-851f-ed97bd8bacab
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70fe658058b6d00b4a22b333ef5683a285b9cab3
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sapdatareader-class-in-the-sap-adapter"></a><span data-ttu-id="02ec1-102">Clase SAPDataReader en el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="02ec1-102">SAPDataReader class in the SAP adapter</span></span>
<span data-ttu-id="02ec1-103">En la siguiente sección se enumera los métodos y propiedades para la **SAPDataReader** clase.</span><span class="sxs-lookup"><span data-stu-id="02ec1-103">The following section lists the methods and properties for the **SAPDataReader** class.</span></span> <span data-ttu-id="02ec1-104">Esto se deriva de **System.Data.Common.DbDataReader**.</span><span class="sxs-lookup"><span data-stu-id="02ec1-104">This is derived from **System.Data.Common.DbDataReader**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="02ec1-105">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="02ec1-105">Supported Properties</span></span>  
  
|<span data-ttu-id="02ec1-106">Nombre</span><span class="sxs-lookup"><span data-stu-id="02ec1-106">Name</span></span>|<span data-ttu-id="02ec1-107">Get/Set.</span><span class="sxs-lookup"><span data-stu-id="02ec1-107">Get/Set</span></span>|<span data-ttu-id="02ec1-108">Description</span><span class="sxs-lookup"><span data-stu-id="02ec1-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="02ec1-109">**Profundidad**</span><span class="sxs-lookup"><span data-stu-id="02ec1-109">**Depth**</span></span>|<span data-ttu-id="02ec1-110">Obtener</span><span class="sxs-lookup"><span data-stu-id="02ec1-110">Get</span></span>|<span data-ttu-id="02ec1-111">No compatible.</span><span class="sxs-lookup"><span data-stu-id="02ec1-111">Not supported.</span></span> <span data-ttu-id="02ec1-112">Devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="02ec1-112">Returns 0.</span></span>|  
|<span data-ttu-id="02ec1-113">**FieldCount**</span><span class="sxs-lookup"><span data-stu-id="02ec1-113">**FieldCount**</span></span>|<span data-ttu-id="02ec1-114">Obtener</span><span class="sxs-lookup"><span data-stu-id="02ec1-114">Get</span></span>|<span data-ttu-id="02ec1-115">Número de campos en el conjunto de registros actual</span><span class="sxs-lookup"><span data-stu-id="02ec1-115">Number of fields in the current record set</span></span>|  
|<span data-ttu-id="02ec1-116">**IsClosed**</span><span class="sxs-lookup"><span data-stu-id="02ec1-116">**IsClosed**</span></span>|<span data-ttu-id="02ec1-117">Obtener</span><span class="sxs-lookup"><span data-stu-id="02ec1-117">Get</span></span>|<span data-ttu-id="02ec1-118">Devuelve el estado del lector de datos</span><span class="sxs-lookup"><span data-stu-id="02ec1-118">Returns status of data reader</span></span>|  
|<span data-ttu-id="02ec1-119">**RecordsAffected**</span><span class="sxs-lookup"><span data-stu-id="02ec1-119">**RecordsAffected**</span></span>|<span data-ttu-id="02ec1-120">Obtener</span><span class="sxs-lookup"><span data-stu-id="02ec1-120">Get</span></span>|<span data-ttu-id="02ec1-121">No compatible.</span><span class="sxs-lookup"><span data-stu-id="02ec1-121">Not supported.</span></span> <span data-ttu-id="02ec1-122">Devuelve -1</span><span class="sxs-lookup"><span data-stu-id="02ec1-122">Returns -1</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="02ec1-123">Métodos admitidos</span><span class="sxs-lookup"><span data-stu-id="02ec1-123">Supported Methods</span></span>  
  
|<span data-ttu-id="02ec1-124">Nombre</span><span class="sxs-lookup"><span data-stu-id="02ec1-124">Name</span></span>|<span data-ttu-id="02ec1-125">Description</span><span class="sxs-lookup"><span data-stu-id="02ec1-125">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="02ec1-126">**Close()**</span><span class="sxs-lookup"><span data-stu-id="02ec1-126">**Close()**</span></span>|<span data-ttu-id="02ec1-127">Cierra el DataReader</span><span class="sxs-lookup"><span data-stu-id="02ec1-127">Closes the DataReader</span></span>|  
|<span data-ttu-id="02ec1-128">**Get [métodos]** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="02ec1-128">**Get [methods]** <sup>\*</sup></span></span><br /><br /> <span data-ttu-id="02ec1-129">donde [métodos] es el tipo de datos esperado.</span><span class="sxs-lookup"><span data-stu-id="02ec1-129">where [methods] is the expected data type.</span></span> <span data-ttu-id="02ec1-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02ec1-130">E.g.</span></span> <span data-ttu-id="02ec1-131">GetInt32(int)</span><span class="sxs-lookup"><span data-stu-id="02ec1-131">GetInt32(int)</span></span>|<span data-ttu-id="02ec1-132">Obtiene el valor de la columna en función del tipo de datos esperado</span><span class="sxs-lookup"><span data-stu-id="02ec1-132">Gets column value based on the data type expected</span></span>|  
|<span data-ttu-id="02ec1-133">**IsDBNull(int)**</span><span class="sxs-lookup"><span data-stu-id="02ec1-133">**IsDBNull(int)**</span></span>|<span data-ttu-id="02ec1-134">No compatible.</span><span class="sxs-lookup"><span data-stu-id="02ec1-134">Not supported.</span></span> <span data-ttu-id="02ec1-135">Devuelve false.</span><span class="sxs-lookup"><span data-stu-id="02ec1-135">Returns false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02ec1-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="02ec1-136">See Also</span></span>  
 [<span data-ttu-id="02ec1-137">Extender Interfaces de ADO.NET con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="02ec1-137">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)