---
title: "Types1 básica | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, data types
- JD Edwards OneWorld adapters, business functions
- .NET Framework, mapping [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], data types
- adapters [JD Edwards OneWorld adapters], .NET Framework
- JD Edwards OneWorld adapters, .NET Framework
- adapters [JD Edwards OneWorld adapters], business functions
ms.assetid: d306ea1b-fb74-4fa3-9681-405252928df1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90cda6259567adf5236d0c28e576900d8b25271
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="basic-types"></a><span data-ttu-id="34931-102">Tipos básicos</span><span class="sxs-lookup"><span data-stu-id="34931-102">Basic Types</span></span>
<span data-ttu-id="34931-103">El adaptador de Microsoft BizTalk para JD Edwards OneWorld únicamente proporciona acceso a las funciones de negocio JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="34931-103">Microsoft BizTalk Adapter for JD Edwards OneWorld provides access only to JD Edwards OneWorld business functions.</span></span> <span data-ttu-id="34931-104">Los metadatos de función de negocio se leen mediante una interfaz de funciones de negocio y se usa para buscar una lista de funciones de negocio y estructuras de datos asociadas.</span><span class="sxs-lookup"><span data-stu-id="34931-104">Business function metadata is read using a business function interface and used to find a list of business functions and associated data structures.</span></span> <span data-ttu-id="34931-105">Los metadatos se establecen de forma inflexible en todos los casos para todos los métodos de la función de negocio.</span><span class="sxs-lookup"><span data-stu-id="34931-105">Metadata is strongly typed in all cases for all business function methods.</span></span>  
  
 <span data-ttu-id="34931-106">Todos los métodos de la función de negocio tienen la misma convención de llamada: tres parámetros que se derivan del sistema y un puntero a una estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="34931-106">All business function methods have the same calling convention: three parameters that are system derived, and a pointer to a data structure.</span></span> <span data-ttu-id="34931-107">La tabla siguiente muestra cómo se representan los tipos de datos de la función de negocio.</span><span class="sxs-lookup"><span data-stu-id="34931-107">The following table shows how the business function data types are represented.</span></span>  
  
 <span data-ttu-id="34931-108">**Tipos de datos de función de negocio**</span><span class="sxs-lookup"><span data-stu-id="34931-108">**Business function data types**</span></span>  
  
|<span data-ttu-id="34931-109">Tipo de datos de OneWorld JD Edwards</span><span class="sxs-lookup"><span data-stu-id="34931-109">JD Edwards OneWorld Data Type</span></span>|<span data-ttu-id="34931-110">Description</span><span class="sxs-lookup"><span data-stu-id="34931-110">Description</span></span>|<span data-ttu-id="34931-111">Conversión de WDSL</span><span class="sxs-lookup"><span data-stu-id="34931-111">WDSL Conversion</span></span>|  
|-----------------------------------|-----------------|---------------------|  
|<span data-ttu-id="34931-112">char</span><span class="sxs-lookup"><span data-stu-id="34931-112">char</span></span>|<span data-ttu-id="34931-113">Cadena de caracteres.</span><span class="sxs-lookup"><span data-stu-id="34931-113">Character string.</span></span>|<span data-ttu-id="34931-114">xsd:cadena de 1</span><span class="sxs-lookup"><span data-stu-id="34931-114">xsd:string of 1</span></span>|  
|<span data-ttu-id="34931-115">int</span><span class="sxs-lookup"><span data-stu-id="34931-115">int</span></span>|<span data-ttu-id="34931-116">Entero corto.</span><span class="sxs-lookup"><span data-stu-id="34931-116">Short integer.</span></span>|<span data-ttu-id="34931-117">xsd:short</span><span class="sxs-lookup"><span data-stu-id="34931-117">xsd:short</span></span>|  
|<span data-ttu-id="34931-118">long</span><span class="sxs-lookup"><span data-stu-id="34931-118">long</span></span>|<span data-ttu-id="34931-119">Entero largo.</span><span class="sxs-lookup"><span data-stu-id="34931-119">Long integer.</span></span>|<span data-ttu-id="34931-120">xsd:short</span><span class="sxs-lookup"><span data-stu-id="34931-120">xsd:short</span></span>|  
|<span data-ttu-id="34931-121">String</span><span class="sxs-lookup"><span data-stu-id="34931-121">String</span></span>|<span data-ttu-id="34931-122">Vea [controlar los valores de cadena](../core/handling-string-values1.md).</span><span class="sxs-lookup"><span data-stu-id="34931-122">See [Handling String Values](../core/handling-string-values1.md).</span></span>|<span data-ttu-id="34931-123">xsd:cadena</span><span class="sxs-lookup"><span data-stu-id="34931-123">xsd:string</span></span>|  
|<span data-ttu-id="34931-124">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="34931-124">JDEDATE</span></span>|<span data-ttu-id="34931-125">Implementación especial de fechas.</span><span class="sxs-lookup"><span data-stu-id="34931-125">Special implementation of dates.</span></span>|<span data-ttu-id="34931-126">xsd:fecha</span><span class="sxs-lookup"><span data-stu-id="34931-126">xsd:date</span></span>|  
|<span data-ttu-id="34931-127">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="34931-127">MATH_NUMERIC</span></span>|<span data-ttu-id="34931-128">Implementación especial de números de coma flotante, incluidos los valores de moneda.</span><span class="sxs-lookup"><span data-stu-id="34931-128">Special implementation of floating point numbers, including currency values.</span></span>|<span data-ttu-id="34931-129">xsd: String de 32</span><span class="sxs-lookup"><span data-stu-id="34931-129">xsd:string of 32</span></span>|  
|<span data-ttu-id="34931-130">Byte</span><span class="sxs-lookup"><span data-stu-id="34931-130">Byte</span></span>|<span data-ttu-id="34931-131">Único carácter sin signo.</span><span class="sxs-lookup"><span data-stu-id="34931-131">Single unsigned character.</span></span>|<span data-ttu-id="34931-132">xsd:cadena de 1</span><span class="sxs-lookup"><span data-stu-id="34931-132">xsd:string of 1</span></span>|  
  
 <span data-ttu-id="34931-133">La tabla siguiente contiene la lista de tipos básicos en JD Edwards OneWorld y cómo se asignan a Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="34931-133">The following table contains the list of basic types in JD Edwards OneWorld and how they map to the Microsoft .NET Framework.</span></span>  
  
 <span data-ttu-id="34931-134">**Tipos básicos y cómo se asignan a Microsoft .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="34931-134">**Basic types and how they map to the Microsoft .NET Framework**</span></span>  
  
|<span data-ttu-id="34931-135">JD Edwards OneWorld XE</span><span class="sxs-lookup"><span data-stu-id="34931-135">JD Edwards OneWorld XE</span></span>|<span data-ttu-id="34931-136">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="34931-136">.NET Framework</span></span>|  
|----------------------------|--------------------|  
|<span data-ttu-id="34931-137">char</span><span class="sxs-lookup"><span data-stu-id="34931-137">char</span></span>|<span data-ttu-id="34931-138">String</span><span class="sxs-lookup"><span data-stu-id="34931-138">String</span></span>|  
|<span data-ttu-id="34931-139">int</span><span class="sxs-lookup"><span data-stu-id="34931-139">int</span></span>|<span data-ttu-id="34931-140">Short</span><span class="sxs-lookup"><span data-stu-id="34931-140">Short</span></span>|  
|<span data-ttu-id="34931-141">long</span><span class="sxs-lookup"><span data-stu-id="34931-141">long</span></span>|<span data-ttu-id="34931-142">Short</span><span class="sxs-lookup"><span data-stu-id="34931-142">Short</span></span>|  
|<span data-ttu-id="34931-143">String</span><span class="sxs-lookup"><span data-stu-id="34931-143">String</span></span>|<span data-ttu-id="34931-144">String</span><span class="sxs-lookup"><span data-stu-id="34931-144">String</span></span>|  
|<span data-ttu-id="34931-145">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="34931-145">JDEDATE</span></span>|<span data-ttu-id="34931-146">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="34931-146">System.DateTime</span></span>|  
|<span data-ttu-id="34931-147">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="34931-147">MATH_NUMERIC</span></span>|<span data-ttu-id="34931-148">String</span><span class="sxs-lookup"><span data-stu-id="34931-148">String</span></span>|  
|<span data-ttu-id="34931-149">Byte</span><span class="sxs-lookup"><span data-stu-id="34931-149">Byte</span></span>|<span data-ttu-id="34931-150">String</span><span class="sxs-lookup"><span data-stu-id="34931-150">String</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="34931-151">Si solo hay un argumento, y el argumento de devolución es nulo, el marcador se reemplaza por la clase y la porción de salida se convierte en el valor de devolución.</span><span class="sxs-lookup"><span data-stu-id="34931-151">If there is only one argument, and the return argument is void, the holder is replaced by the class, and the out portion becomes the return value.</span></span> <span data-ttu-id="34931-152">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="34931-152">For example:</span></span>  
  
```  
org.apache.axis.holders.DateHolder becomes a java.util.Date.   
```  
  
 <span data-ttu-id="34931-153">A continuación se muestra un ejemplo de firmas de método:</span><span class="sxs-lookup"><span data-stu-id="34931-153">The following is an example of method signatures:</span></span>  
  
```  
void testDate1(org.apache.axis.holders.DateHolder date1  
        org.apache.axis.holders.DateHolder date2);  
  
java.util.Date testDate2(java.util.Date date);  
```  
  
## <a name="character-limited-strings"></a><span data-ttu-id="34931-154">Cadenas con limitación de caracteres</span><span class="sxs-lookup"><span data-stu-id="34931-154">Character-Limited Strings</span></span>  
 <span data-ttu-id="34931-155">En JD Edwards OneWorld, algunas cadenas tienen los caracteres limitados.</span><span class="sxs-lookup"><span data-stu-id="34931-155">In JD Edwards OneWorld, some strings are character-limited.</span></span> <span data-ttu-id="34931-156">Cualquier carácter adicional produce un error.</span><span class="sxs-lookup"><span data-stu-id="34931-156">Any extra character causes an error.</span></span> <span data-ttu-id="34931-157">Para ver el límite de caracteres de las cadenas, puede usarse el asistente para adaptadores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34931-157">To see the limit of characters in the strings, you can use the Microsoft Adapter Wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34931-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="34931-158">See Also</span></span>  
 <span data-ttu-id="34931-159">[Uso del tipo MATH_NUMERIC](../core/using-the-math-numeric-type2.md) </span><span class="sxs-lookup"><span data-stu-id="34931-159">[Using the MATH_NUMERIC Type](../core/using-the-math-numeric-type2.md) </span></span>  
 <span data-ttu-id="34931-160">[Control de valores de cadena](../core/handling-string-values1.md) </span><span class="sxs-lookup"><span data-stu-id="34931-160">[Handling String Values](../core/handling-string-values1.md) </span></span>  
 [<span data-ttu-id="34931-161">Apéndice A: tipos de datos</span><span class="sxs-lookup"><span data-stu-id="34931-161">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)