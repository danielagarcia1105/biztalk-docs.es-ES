---
title: Clase SiebelParameter en el adaptador de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SiebelParameter
- Data Provider for Siebel, SiebelParameter
- SiebelParameter, supported properties and methods
ms.assetid: 1dcb72c7-a470-4609-8aba-a5c8ad5f3ac9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27df4b207b23cd04f7d29a2a18ec4ab032836e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="siebelparameter-class-in-the-siebel-adapter"></a><span data-ttu-id="36d86-102">Clase SiebelParameter en el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="36d86-102">SiebelParameter class in the Siebel adapter</span></span>
<span data-ttu-id="36d86-103">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] proporciona un `DbParameter` implementación para permitir que un cliente ADO.NET especificar los parámetros de un comando concreto.</span><span class="sxs-lookup"><span data-stu-id="36d86-103">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] provides a `DbParameter` implementation to enable an ADO.NET client to specify parameters for a particular command.</span></span> <span data-ttu-id="36d86-104">Mediante una instancia de la `System.Data.Common.DbCommand` clase de la [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], un programa cliente puede obtener una instancia de la `System.Data.Common.DbParameter` clase.</span><span class="sxs-lookup"><span data-stu-id="36d86-104">Using an instance of the `System.Data.Common.DbCommand` class of the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], a client program can obtain an instance of the `System.Data.Common.DbParameter` class.</span></span>  
  
```  
//In this example, command is an instance of DbCommand  
DbParameter param = command.CreateParameter();  
```  
  
 <span data-ttu-id="36d86-105">También se puede usar el siguiente método:</span><span class="sxs-lookup"><span data-stu-id="36d86-105">Alternatively, the following approach can be used:</span></span>  
  
```  
  
//Here command is an instance of SiebelCommand  
SiebelParameter param = (SiebelParameter) command.CreateParameter();                  
param.ParameterName = "@Time";  
```  
  
 <span data-ttu-id="36d86-106">El `SiebelParameter` clase hereda de `DbParameter`.</span><span class="sxs-lookup"><span data-stu-id="36d86-106">The `SiebelParameter` class inherits from `DbParameter`.</span></span>  <span data-ttu-id="36d86-107">Se encuentra en el espacio de nombres `Microsoft.Data.SiebelClient`.</span><span class="sxs-lookup"><span data-stu-id="36d86-107">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="36d86-108">Propiedades admitidas</span><span class="sxs-lookup"><span data-stu-id="36d86-108">Supported Properties</span></span>  
 <span data-ttu-id="36d86-109">El `SiebelParameter` clase admite las siguientes `DbParameter` *público* propiedades:</span><span class="sxs-lookup"><span data-stu-id="36d86-109">The `SiebelParameter` class supports the following `DbParameter`*public* properties:</span></span>  
  
|<span data-ttu-id="36d86-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="36d86-110">Name</span></span>|<span data-ttu-id="36d86-111">Get/Set.</span><span class="sxs-lookup"><span data-stu-id="36d86-111">Get/Set</span></span>|<span data-ttu-id="36d86-112">Description</span><span class="sxs-lookup"><span data-stu-id="36d86-112">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="36d86-113">**DbType**</span><span class="sxs-lookup"><span data-stu-id="36d86-113">**DbType**</span></span>|<span data-ttu-id="36d86-114">Get y Set</span><span class="sxs-lookup"><span data-stu-id="36d86-114">Get and Set</span></span>|<span data-ttu-id="36d86-115">Tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="36d86-115">Data type of the parameter.</span></span> <span data-ttu-id="36d86-116">Vea [tipos de datos básicos de Siebel](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="36d86-116">See [Basic Siebel Data Types](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span></span>|  
|<span data-ttu-id="36d86-117">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="36d86-117">**Direction**</span></span>|<span data-ttu-id="36d86-118">Get y Set</span><span class="sxs-lookup"><span data-stu-id="36d86-118">Get and Set</span></span>|<span data-ttu-id="36d86-119">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="36d86-119">The following values are supported:</span></span><br /><br /> -                     `ParameterDirection.Input`<br /><br /> -                     `ParameterDirection.Output`<br /><br /> -                     `ParameterDirection.InputOutput`|  
|<span data-ttu-id="36d86-120">**IsNullable**</span><span class="sxs-lookup"><span data-stu-id="36d86-120">**IsNullable**</span></span>|<span data-ttu-id="36d86-121">Get y Set</span><span class="sxs-lookup"><span data-stu-id="36d86-121">Get and Set</span></span>|<span data-ttu-id="36d86-122">La propiedad no se admite e iniciará una excepción si se llama.</span><span class="sxs-lookup"><span data-stu-id="36d86-122">The property is not supported, and will throw an exception if called.</span></span>|  
|<span data-ttu-id="36d86-123">**ParameterName**</span><span class="sxs-lookup"><span data-stu-id="36d86-123">**ParameterName**</span></span>|<span data-ttu-id="36d86-124">Get y Set</span><span class="sxs-lookup"><span data-stu-id="36d86-124">Get and Set</span></span>|<span data-ttu-id="36d86-125">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] es compatible con esta propiedad para un cliente ADO.NET especificar el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="36d86-125">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports this property for an ADO.NET client to specify the parameter name.</span></span>|  
|<span data-ttu-id="36d86-126">**Valor**</span><span class="sxs-lookup"><span data-stu-id="36d86-126">**Value**</span></span>|<span data-ttu-id="36d86-127">Get y Set</span><span class="sxs-lookup"><span data-stu-id="36d86-127">Get and Set</span></span>|<span data-ttu-id="36d86-128">El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] representa valores de parámetro como cadenas.</span><span class="sxs-lookup"><span data-stu-id="36d86-128">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] represents parameter values as strings.</span></span>|  
  
###  <span data-ttu-id="36d86-129"><a name="BKMK_Datatypes"></a>Tipos de datos admitidos</span><span class="sxs-lookup"><span data-stu-id="36d86-129"><a name="BKMK_Datatypes"></a> Supported Data Types</span></span>  
 <span data-ttu-id="36d86-130">En la tabla siguiente se resume los más sencillos tipos de campo de Siebel que [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] admite.</span><span class="sxs-lookup"><span data-stu-id="36d86-130">The following table summarizes the simple Siebel field types that [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports.</span></span> <span data-ttu-id="36d86-131">Para obtener cobertura más detallada, vea [tipos de datos básicos de Siebel](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="36d86-131">For more detailed coverage, see [Basic Siebel Data Types](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span></span>  
  
|<span data-ttu-id="36d86-132">Tipo de campo de Siebel</span><span class="sxs-lookup"><span data-stu-id="36d86-132">Siebel Field Type</span></span>|<span data-ttu-id="36d86-133">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="36d86-133">.NET Type</span></span>|<span data-ttu-id="36d86-134">Tipo de esquema XML</span><span class="sxs-lookup"><span data-stu-id="36d86-134">XML Schema Type</span></span>|  
|-----------------------|---------------|---------------------|  
|<span data-ttu-id="36d86-135">DTYPE_BOOL</span><span class="sxs-lookup"><span data-stu-id="36d86-135">DTYPE_BOOL</span></span>|<span data-ttu-id="36d86-136">Boolean</span><span class="sxs-lookup"><span data-stu-id="36d86-136">Boolean</span></span>|<span data-ttu-id="36d86-137">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="36d86-137">xsd:boolean</span></span>|  
|<span data-ttu-id="36d86-138">DTYPE_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="36d86-138">DTYPE_CURRENCY</span></span>|<span data-ttu-id="36d86-139">Decimal</span><span class="sxs-lookup"><span data-stu-id="36d86-139">Decimal</span></span>|<span data-ttu-id="36d86-140">xsd:decimal</span><span class="sxs-lookup"><span data-stu-id="36d86-140">xsd:decimal</span></span>|  
|<span data-ttu-id="36d86-141">DTYPE_DATE</span><span class="sxs-lookup"><span data-stu-id="36d86-141">DTYPE_DATE</span></span>|<span data-ttu-id="36d86-142">DateTime</span><span class="sxs-lookup"><span data-stu-id="36d86-142">DateTime</span></span>|<span data-ttu-id="36d86-143">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="36d86-143">xsd:dateTime</span></span>|  
|<span data-ttu-id="36d86-144">DTYPE_DATETIME</span><span class="sxs-lookup"><span data-stu-id="36d86-144">DTYPE_DATETIME</span></span>|<span data-ttu-id="36d86-145">DateTime</span><span class="sxs-lookup"><span data-stu-id="36d86-145">DateTime</span></span>|<span data-ttu-id="36d86-146">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="36d86-146">xsd:dateTime</span></span>|  
|<span data-ttu-id="36d86-147">UTCDATETIME DTYPE_</span><span class="sxs-lookup"><span data-stu-id="36d86-147">DTYPE_ UTCDATETIME</span></span>|<span data-ttu-id="36d86-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="36d86-148">DateTime</span></span>|<span data-ttu-id="36d86-149">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="36d86-149">xsd:dateTime</span></span>|  
|<span data-ttu-id="36d86-150">DTYPE_ID</span><span class="sxs-lookup"><span data-stu-id="36d86-150">DTYPE_ID</span></span>|<span data-ttu-id="36d86-151">String</span><span class="sxs-lookup"><span data-stu-id="36d86-151">String</span></span>|<span data-ttu-id="36d86-152">xsd:cadena</span><span class="sxs-lookup"><span data-stu-id="36d86-152">xsd:string</span></span>|  
|<span data-ttu-id="36d86-153">DTYPE_INTEGER</span><span class="sxs-lookup"><span data-stu-id="36d86-153">DTYPE_INTEGER</span></span>|<span data-ttu-id="36d86-154">Integer</span><span class="sxs-lookup"><span data-stu-id="36d86-154">Integer</span></span>|<span data-ttu-id="36d86-155">xsd:int</span><span class="sxs-lookup"><span data-stu-id="36d86-155">xsd:int</span></span>|  
|<span data-ttu-id="36d86-156">DTYPE_NOTE</span><span class="sxs-lookup"><span data-stu-id="36d86-156">DTYPE_NOTE</span></span>|<span data-ttu-id="36d86-157">String</span><span class="sxs-lookup"><span data-stu-id="36d86-157">String</span></span>|<span data-ttu-id="36d86-158">xsd:cadena</span><span class="sxs-lookup"><span data-stu-id="36d86-158">xsd:string</span></span>|  
|<span data-ttu-id="36d86-159">DTYPE_NUMBER</span><span class="sxs-lookup"><span data-stu-id="36d86-159">DTYPE_NUMBER</span></span>|<span data-ttu-id="36d86-160">Decimal</span><span class="sxs-lookup"><span data-stu-id="36d86-160">Decimal</span></span>|<span data-ttu-id="36d86-161">xsd:decimal</span><span class="sxs-lookup"><span data-stu-id="36d86-161">xsd:decimal</span></span>|  
|<span data-ttu-id="36d86-162">DTYPE_PHONE</span><span class="sxs-lookup"><span data-stu-id="36d86-162">DTYPE_PHONE</span></span>|<span data-ttu-id="36d86-163">String</span><span class="sxs-lookup"><span data-stu-id="36d86-163">String</span></span>|<span data-ttu-id="36d86-164">xsd:cadena</span><span class="sxs-lookup"><span data-stu-id="36d86-164">xsd:string</span></span>|  
|<span data-ttu-id="36d86-165">DTYPE_TEXT</span><span class="sxs-lookup"><span data-stu-id="36d86-165">DTYPE_TEXT</span></span>|<span data-ttu-id="36d86-166">String</span><span class="sxs-lookup"><span data-stu-id="36d86-166">String</span></span>|<span data-ttu-id="36d86-167">xsd:cadena</span><span class="sxs-lookup"><span data-stu-id="36d86-167">xsd:string</span></span>|  
|<span data-ttu-id="36d86-168">DTYPE_TIME</span><span class="sxs-lookup"><span data-stu-id="36d86-168">DTYPE_TIME</span></span>|<span data-ttu-id="36d86-169">DateTime</span><span class="sxs-lookup"><span data-stu-id="36d86-169">DateTime</span></span>|<span data-ttu-id="36d86-170">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="36d86-170">xsd:dateTime</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="36d86-171">Métodos admitidos</span><span class="sxs-lookup"><span data-stu-id="36d86-171">Supported Methods</span></span>  
 <span data-ttu-id="36d86-172">El `SiebelParameter` clase no invalida los métodos especiales en `DbParameter`.</span><span class="sxs-lookup"><span data-stu-id="36d86-172">The `SiebelParameter` class does not override any special methods in `DbParameter`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d86-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="36d86-173">See Also</span></span>  
 [<span data-ttu-id="36d86-174">Extender Interfaces de ADO.NET con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="36d86-174">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)