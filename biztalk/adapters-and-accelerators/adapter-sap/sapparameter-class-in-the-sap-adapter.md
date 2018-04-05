---
title: Clase SAPParameter en el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPParameter, supported methods, classes, and constructors
ms.assetid: 60053393-ad22-4c99-abae-e538d43c8e18
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ff43c344cc14adb3deef226c270adc3ca94f2a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sapparameter-class-in-the-sap-adapter"></a><span data-ttu-id="aa4f6-102">Clase SAPParameter en el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="aa4f6-102">SAPParameter class in the SAP adapter</span></span>
<span data-ttu-id="aa4f6-103">En la siguiente sección se enumera los métodos y propiedades para la **SAPParameter** clase.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-103">The following section lists the methods and properties for the **SAPParameter** class.</span></span> <span data-ttu-id="aa4f6-104">Esto se deriva de **System.Data.Common.DbParameter**.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-104">This is derived from **System.Data.Common.DbParameter**.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="aa4f6-105">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="aa4f6-105">Supported Properties</span></span>  
  
|<span data-ttu-id="aa4f6-106">Nombre</span><span class="sxs-lookup"><span data-stu-id="aa4f6-106">Name</span></span>|<span data-ttu-id="aa4f6-107">Get/Set.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-107">Get/Set</span></span>|<span data-ttu-id="aa4f6-108">Description</span><span class="sxs-lookup"><span data-stu-id="aa4f6-108">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="aa4f6-109">**DbType**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-109">**DbType**</span></span>|<span data-ttu-id="aa4f6-110">Obtener</span><span class="sxs-lookup"><span data-stu-id="aa4f6-110">Get</span></span>|<span data-ttu-id="aa4f6-111">DbType si el parámetro devuelto.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-111">DbType if the parameter returned.</span></span> <span data-ttu-id="aa4f6-112">No se puede establecer.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-112">Cannot be set.</span></span>|  
|<span data-ttu-id="aa4f6-113">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-113">**Direction**</span></span>|<span data-ttu-id="aa4f6-114">Get y Set</span><span class="sxs-lookup"><span data-stu-id="aa4f6-114">Get and Set</span></span>|<span data-ttu-id="aa4f6-115">ParameterDirection.ReturnValue no compatible.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-115">ParameterDirection.ReturnValue not supported.</span></span>|  
|<span data-ttu-id="aa4f6-116">**IsNullable**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-116">**IsNullable**</span></span>|-|<span data-ttu-id="aa4f6-117">No compatible.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-117">Not supported.</span></span>|  
|<span data-ttu-id="aa4f6-118">**ParameterName**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-118">**ParameterName**</span></span>|<span data-ttu-id="aa4f6-119">Get y Set</span><span class="sxs-lookup"><span data-stu-id="aa4f6-119">Get and Set</span></span>|<span data-ttu-id="aa4f6-120">Nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-120">Name of the parameter.</span></span>|  
|<span data-ttu-id="aa4f6-121">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-121">**Size**</span></span>|-|<span data-ttu-id="aa4f6-122">No compatible.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-122">Not supported.</span></span>|  
|<span data-ttu-id="aa4f6-123">**SourceColumn**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-123">**SourceColumn**</span></span>|-|<span data-ttu-id="aa4f6-124">No compatible.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-124">Not supported.</span></span>|  
|<span data-ttu-id="aa4f6-125">**SourceColumnNullMapping**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-125">**SourceColumnNullMapping**</span></span>|-|<span data-ttu-id="aa4f6-126">No compatible.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-126">Not supported.</span></span>|  
|<span data-ttu-id="aa4f6-127">**SourceVersion**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-127">**SourceVersion**</span></span>|-|<span data-ttu-id="aa4f6-128">No compatible.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-128">Not supported.</span></span>|  
|<span data-ttu-id="aa4f6-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-129">**Value**</span></span>|<span data-ttu-id="aa4f6-130">Get y Set</span><span class="sxs-lookup"><span data-stu-id="aa4f6-130">Get and Set</span></span>|<span data-ttu-id="aa4f6-131">Valor del parámetro</span><span class="sxs-lookup"><span data-stu-id="aa4f6-131">Value of the parameter</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="aa4f6-132">Métodos admitidos</span><span class="sxs-lookup"><span data-stu-id="aa4f6-132">Supported Methods</span></span>  
  
|<span data-ttu-id="aa4f6-133">Nombre</span><span class="sxs-lookup"><span data-stu-id="aa4f6-133">Name</span></span>|<span data-ttu-id="aa4f6-134">Description</span><span class="sxs-lookup"><span data-stu-id="aa4f6-134">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="aa4f6-135">**ResetDbType()**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-135">**ResetDbType()**</span></span>|<span data-ttu-id="aa4f6-136">No compatible.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-136">Not supported.</span></span>|  
  
## <a name="supported-constructors"></a><span data-ttu-id="aa4f6-137">Constructores</span><span class="sxs-lookup"><span data-stu-id="aa4f6-137">Supported Constructors</span></span>  
  
|<span data-ttu-id="aa4f6-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="aa4f6-138">Name</span></span>|<span data-ttu-id="aa4f6-139">Description</span><span class="sxs-lookup"><span data-stu-id="aa4f6-139">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="aa4f6-140">**SAPParameter()**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-140">**SAPParameter()**</span></span>|<span data-ttu-id="aa4f6-141">Instancia de parámetro SAP.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-141">SAP parameter instance.</span></span>|  
|<span data-ttu-id="aa4f6-142">**SAPParameter(string)**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-142">**SAPParameter(string)**</span></span>|<span data-ttu-id="aa4f6-143">Parámetro SAP con el nombre de parámetro SAP.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-143">SAP parameter with SAP parameter name.</span></span>|  
|<span data-ttu-id="aa4f6-144">**SAPParameter (string, DbType)**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-144">**SAPParameter(string, DbType)**</span></span>|<span data-ttu-id="aa4f6-145">Parámetro SAP con el nombre del parámetro SAP y DbType.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-145">SAP parameter with SAP parameter name and DbType.</span></span>|  
|<span data-ttu-id="aa4f6-146">**SAPParameter (string, object)**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-146">**SAPParameter(string, object)**</span></span>|<span data-ttu-id="aa4f6-147">Parámetro SAP con el nombre del parámetro SAP y el valor.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-147">SAP parameter with SAP parameter name and value.</span></span> <span data-ttu-id="aa4f6-148">Tipos complejos tienen el valor de tipo DataTable y cadena XML.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-148">Complex types have value of type DataTable and XML string.</span></span>|  
|<span data-ttu-id="aa4f6-149">**SAPParameter (string, ParameterDirection)**</span><span class="sxs-lookup"><span data-stu-id="aa4f6-149">**SAPParameter(string, ParameterDirection)**</span></span>|<span data-ttu-id="aa4f6-150">Parámetro SAP con la dirección de parámetro y nombre del parámetro SAP.</span><span class="sxs-lookup"><span data-stu-id="aa4f6-150">SAP parameter with SAP parameter name and parameter direction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa4f6-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa4f6-151">See Also</span></span>  
 [<span data-ttu-id="aa4f6-152">Extender Interfaces de ADO.NET con el adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="aa4f6-152">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)