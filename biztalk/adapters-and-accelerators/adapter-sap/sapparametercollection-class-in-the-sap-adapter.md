---
title: Clase SAPParameterCollection en el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPParameterCollection, supported methods and classes
ms.assetid: fd09355b-95f4-4d49-a643-b13058e63d74
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 924cb884c64f337cec0e628c804b5c5a8c6cf37b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218044"
---
# <a name="sapparametercollection-class-in-the-sap-adapter"></a><span data-ttu-id="5710c-102">Clase SAPParameterCollection en el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="5710c-102">SAPParameterCollection class in the SAP adapter</span></span>
<span data-ttu-id="5710c-103">En la siguiente sección se enumera los métodos y propiedades para la **SAPParameterCollection** clase.</span><span class="sxs-lookup"><span data-stu-id="5710c-103">The following section lists the methods and properties for the **SAPParameterCollection** class.</span></span> <span data-ttu-id="5710c-104">Esto se deriva de **System.Data.Common.DbParameterCollection**.</span><span class="sxs-lookup"><span data-stu-id="5710c-104">This is derived from **System.Data.Common.DbParameterCollection**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="5710c-105">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="5710c-105">Supported Properties</span></span>  
  
|<span data-ttu-id="5710c-106">Nombre</span><span class="sxs-lookup"><span data-stu-id="5710c-106">Name</span></span>|<span data-ttu-id="5710c-107">Get/Set.</span><span class="sxs-lookup"><span data-stu-id="5710c-107">Get/Set</span></span>|<span data-ttu-id="5710c-108">Description</span><span class="sxs-lookup"><span data-stu-id="5710c-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="5710c-109">**Count**</span><span class="sxs-lookup"><span data-stu-id="5710c-109">**Count**</span></span>|<span data-ttu-id="5710c-110">Obtener</span><span class="sxs-lookup"><span data-stu-id="5710c-110">Get</span></span>|<span data-ttu-id="5710c-111">Número de parámetros de la colección.</span><span class="sxs-lookup"><span data-stu-id="5710c-111">Number of parameters in the collection.</span></span>|  
|<span data-ttu-id="5710c-112">**IsFixedSize**</span><span class="sxs-lookup"><span data-stu-id="5710c-112">**IsFixedSize**</span></span>|<span data-ttu-id="5710c-113">Obtener</span><span class="sxs-lookup"><span data-stu-id="5710c-113">Get</span></span>|<span data-ttu-id="5710c-114">No compatible.</span><span class="sxs-lookup"><span data-stu-id="5710c-114">Not supported.</span></span> <span data-ttu-id="5710c-115">Devuelve false.</span><span class="sxs-lookup"><span data-stu-id="5710c-115">Returns false.</span></span>|  
|<span data-ttu-id="5710c-116">**IsReadOnly**</span><span class="sxs-lookup"><span data-stu-id="5710c-116">**IsReadOnly**</span></span>|<span data-ttu-id="5710c-117">Obtener</span><span class="sxs-lookup"><span data-stu-id="5710c-117">Get</span></span>|<span data-ttu-id="5710c-118">No compatible.</span><span class="sxs-lookup"><span data-stu-id="5710c-118">Not supported.</span></span> <span data-ttu-id="5710c-119">Devuelve false.</span><span class="sxs-lookup"><span data-stu-id="5710c-119">Returns false.</span></span>|  
|<span data-ttu-id="5710c-120">**IsSynchronized**</span><span class="sxs-lookup"><span data-stu-id="5710c-120">**IsSynchronized**</span></span>|<span data-ttu-id="5710c-121">Obtener</span><span class="sxs-lookup"><span data-stu-id="5710c-121">Get</span></span>|<span data-ttu-id="5710c-122">No compatible.</span><span class="sxs-lookup"><span data-stu-id="5710c-122">Not supported.</span></span> <span data-ttu-id="5710c-123">Devuelve false.</span><span class="sxs-lookup"><span data-stu-id="5710c-123">Returns false.</span></span>|  
|<span data-ttu-id="5710c-124">**SyncRoot**</span><span class="sxs-lookup"><span data-stu-id="5710c-124">**SyncRoot**</span></span>|<span data-ttu-id="5710c-125">Obtener</span><span class="sxs-lookup"><span data-stu-id="5710c-125">Get</span></span>|<span data-ttu-id="5710c-126">Devuelve el objeto de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5710c-126">Returns the lock object.</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="5710c-127">Métodos admitidos</span><span class="sxs-lookup"><span data-stu-id="5710c-127">Supported Methods</span></span>  
  
|<span data-ttu-id="5710c-128">Nombre</span><span class="sxs-lookup"><span data-stu-id="5710c-128">Name</span></span>|<span data-ttu-id="5710c-129">Description</span><span class="sxs-lookup"><span data-stu-id="5710c-129">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5710c-130">**Add(SAPParameter)**</span><span class="sxs-lookup"><span data-stu-id="5710c-130">**Add(SAPParameter)**</span></span>|<span data-ttu-id="5710c-131">Parámetro no puede pertenecer a más de un ParameterCollection.</span><span class="sxs-lookup"><span data-stu-id="5710c-131">Parameter cannot belong to more than one ParameterCollection.</span></span>|  
|<span data-ttu-id="5710c-132">**Add(Object)**</span><span class="sxs-lookup"><span data-stu-id="5710c-132">**Add(object)**</span></span>|<span data-ttu-id="5710c-133">Objeto debe ser del tipo SAPParameter.</span><span class="sxs-lookup"><span data-stu-id="5710c-133">Object should be of SAPParameter type.</span></span>|  
|<span data-ttu-id="5710c-134">**AddRange(System.Array)**</span><span class="sxs-lookup"><span data-stu-id="5710c-134">**AddRange(System.Array)**</span></span>|<span data-ttu-id="5710c-135">Agrega una matriz de instancias de SAPParameter.</span><span class="sxs-lookup"><span data-stu-id="5710c-135">Adds an array of SAPParameter instances.</span></span>|  
|<span data-ttu-id="5710c-136">**Clear()**</span><span class="sxs-lookup"><span data-stu-id="5710c-136">**Clear()**</span></span>|<span data-ttu-id="5710c-137">Borra los parámetros de la colección.</span><span class="sxs-lookup"><span data-stu-id="5710c-137">Clears the parameters in the collection.</span></span>|  
|<span data-ttu-id="5710c-138">**Contains(Object)**</span><span class="sxs-lookup"><span data-stu-id="5710c-138">**Contains(object)**</span></span>|<span data-ttu-id="5710c-139">Comprobaciones en función de la instancia del parámetro.</span><span class="sxs-lookup"><span data-stu-id="5710c-139">Checks based on parameter instance.</span></span>|  
|<span data-ttu-id="5710c-140">**Contains(String)**</span><span class="sxs-lookup"><span data-stu-id="5710c-140">**Contains(string)**</span></span>|<span data-ttu-id="5710c-141">Comprobación basada en nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="5710c-141">Checks based on parameter name.</span></span>|  
|<span data-ttu-id="5710c-142">**CopyTo ([] SAPParameter, int)**</span><span class="sxs-lookup"><span data-stu-id="5710c-142">**CopyTo(SAPParameter[], int)**</span></span>|<span data-ttu-id="5710c-143">Lista de parámetros de copias en una matriz de tipos de SAPParameter.</span><span class="sxs-lookup"><span data-stu-id="5710c-143">Copies parameter list to an array of SAPParameter types.</span></span>|  
|<span data-ttu-id="5710c-144">**CopyTo (System.Array, int)**</span><span class="sxs-lookup"><span data-stu-id="5710c-144">**CopyTo(System.Array, int)**</span></span>|<span data-ttu-id="5710c-145">Lista de parámetros de copias en una matriz.</span><span class="sxs-lookup"><span data-stu-id="5710c-145">Copies parameter list to an array.</span></span>|  
|<span data-ttu-id="5710c-146">**GetEnumerator()**</span><span class="sxs-lookup"><span data-stu-id="5710c-146">**GetEnumerator()**</span></span>|<span data-ttu-id="5710c-147">Obtiene un enumerador para los parámetros de la colección.</span><span class="sxs-lookup"><span data-stu-id="5710c-147">Gets an enumerator for the parameters in the collection.</span></span>|  
|<span data-ttu-id="5710c-148">**IndexOf(object)**</span><span class="sxs-lookup"><span data-stu-id="5710c-148">**IndexOf(object)**</span></span>|<span data-ttu-id="5710c-149">Índice del parámetro basado en la instancia de SAPParameter.</span><span class="sxs-lookup"><span data-stu-id="5710c-149">Index of parameter based on SAPParameter instance.</span></span>|  
|<span data-ttu-id="5710c-150">**IndexOf(string)**</span><span class="sxs-lookup"><span data-stu-id="5710c-150">**IndexOf(string)**</span></span>|<span data-ttu-id="5710c-151">Índice del parámetro en función del nombre de SAPParameter.</span><span class="sxs-lookup"><span data-stu-id="5710c-151">Index of parameter based on SAPParameter name.</span></span>|  
|<span data-ttu-id="5710c-152">**Insert (int, object)**</span><span class="sxs-lookup"><span data-stu-id="5710c-152">**Insert(int, object)**</span></span>|<span data-ttu-id="5710c-153">Inserta un SAPParameter en la colección.</span><span class="sxs-lookup"><span data-stu-id="5710c-153">Inserts an SAPParameter into the collection.</span></span>|  
|<span data-ttu-id="5710c-154">**Remove(Object)**</span><span class="sxs-lookup"><span data-stu-id="5710c-154">**Remove(object)**</span></span>|<span data-ttu-id="5710c-155">Quita un SAPParameter en la colección basándose en la instancia.</span><span class="sxs-lookup"><span data-stu-id="5710c-155">Removes an SAPParameter into the collection based on instance.</span></span>|  
|<span data-ttu-id="5710c-156">**RemoveAt(int)**</span><span class="sxs-lookup"><span data-stu-id="5710c-156">**RemoveAt(int)**</span></span>|<span data-ttu-id="5710c-157">Quita un SAPParameter en la colección en un índice determinado.</span><span class="sxs-lookup"><span data-stu-id="5710c-157">Removes an SAPParameter into the collection at a given index.</span></span>|  
|<span data-ttu-id="5710c-158">**RemoveAt(string)**</span><span class="sxs-lookup"><span data-stu-id="5710c-158">**RemoveAt(string)**</span></span>|<span data-ttu-id="5710c-159">Quita un SAPParameter en la colección basándose en el nombre.</span><span class="sxs-lookup"><span data-stu-id="5710c-159">Removes an SAPParameter into the collection based on name.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5710c-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="5710c-160">See Also</span></span>  
 [<span data-ttu-id="5710c-161">Extender Interfaces de ADO.NET con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="5710c-161">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)