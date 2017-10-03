---
title: "Types2 básica | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, data types
- adapters [JD Edwards EnterpriseOne adapters], data types
- data types, JD Edwards EnterpriseOne adapters
ms.assetid: 96a70f0d-f7f8-4e3b-9511-59b330910ead
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7e5c47d8760e9743ec11a62598581d9d20b3e53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="basic-types"></a><span data-ttu-id="5c873-102">Tipos básicos</span><span class="sxs-lookup"><span data-stu-id="5c873-102">Basic Types</span></span>
<span data-ttu-id="5c873-103">Microsoft BizTalk Adapter para JD Edwards EnterpriseOne proporciona acceso únicamente a funciones de negocio de JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="5c873-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides access only to JD Edwards EnterpriseOne business functions.</span></span> <span data-ttu-id="5c873-104">Los metadatos de función de negocio se leen mediante una interfaz de funciones de negocio y se usa para buscar una lista de funciones de negocio y estructuras de datos asociadas.</span><span class="sxs-lookup"><span data-stu-id="5c873-104">Business function metadata is read using a business function interface and used to find a list of business functions and associated data structures.</span></span> <span data-ttu-id="5c873-105">Los metadatos se establecen de forma inflexible en todos los casos para todos los métodos de la función de negocio.</span><span class="sxs-lookup"><span data-stu-id="5c873-105">Metadata is strongly typed in all cases for all business function methods.</span></span>  
  
 <span data-ttu-id="5c873-106">Todos los métodos de la función de negocio tienen la misma convención de llamada: tres parámetros que se derivan del sistema y un puntero a una estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="5c873-106">All business function methods have the same calling convention: three parameters that are system derived, and a pointer to a data structure.</span></span> <span data-ttu-id="5c873-107">La tabla siguiente muestra cómo se representan los tipos de datos de función de negocio.</span><span class="sxs-lookup"><span data-stu-id="5c873-107">The following table shows how business function data types are represented.</span></span>  
  
|<span data-ttu-id="5c873-108">Tipo de datos de JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="5c873-108">JD Edwards EnterpriseOne Data Type</span></span>|<span data-ttu-id="5c873-109">Description</span><span class="sxs-lookup"><span data-stu-id="5c873-109">Description</span></span>|<span data-ttu-id="5c873-110">Conversión de WDSL</span><span class="sxs-lookup"><span data-stu-id="5c873-110">WDSL Conversion</span></span>|  
|----------------------------------------|-----------------|---------------------|  
|<span data-ttu-id="5c873-111">char</span><span class="sxs-lookup"><span data-stu-id="5c873-111">char</span></span>|<span data-ttu-id="5c873-112">Cadena de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5c873-112">Character string.</span></span>|<span data-ttu-id="5c873-113">xsd:cadena de 1</span><span class="sxs-lookup"><span data-stu-id="5c873-113">xsd:string of 1</span></span>|  
|<span data-ttu-id="5c873-114">int</span><span class="sxs-lookup"><span data-stu-id="5c873-114">int</span></span>|<span data-ttu-id="5c873-115">Entero corto.</span><span class="sxs-lookup"><span data-stu-id="5c873-115">Short integer.</span></span>|<span data-ttu-id="5c873-116">xsd:short</span><span class="sxs-lookup"><span data-stu-id="5c873-116">xsd:short</span></span>|  
|<span data-ttu-id="5c873-117">long</span><span class="sxs-lookup"><span data-stu-id="5c873-117">long</span></span>|<span data-ttu-id="5c873-118">Entero largo.</span><span class="sxs-lookup"><span data-stu-id="5c873-118">Long integer.</span></span>|<span data-ttu-id="5c873-119">xsd:short</span><span class="sxs-lookup"><span data-stu-id="5c873-119">xsd:short</span></span>|  
|<span data-ttu-id="5c873-120">String</span><span class="sxs-lookup"><span data-stu-id="5c873-120">String</span></span>|<span data-ttu-id="5c873-121">Vea [controlar los valores de cadena](../core/handling-string-values2.md).</span><span class="sxs-lookup"><span data-stu-id="5c873-121">See [Handling String Values](../core/handling-string-values2.md).</span></span>|<span data-ttu-id="5c873-122">xsd:cadena</span><span class="sxs-lookup"><span data-stu-id="5c873-122">xsd:string</span></span>|  
|<span data-ttu-id="5c873-123">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="5c873-123">JDEDATE</span></span>|<span data-ttu-id="5c873-124">Implementación especial de fechas.</span><span class="sxs-lookup"><span data-stu-id="5c873-124">Special implementation of dates.</span></span>|<span data-ttu-id="5c873-125">xsd:fecha</span><span class="sxs-lookup"><span data-stu-id="5c873-125">xsd:date</span></span>|  
|<span data-ttu-id="5c873-126">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="5c873-126">MATH_NUMERIC</span></span>|<span data-ttu-id="5c873-127">Implementación especial de números de coma flotante, incluidos los valores de moneda.</span><span class="sxs-lookup"><span data-stu-id="5c873-127">Special implementation of floating point numbers, including currency values.</span></span>|<span data-ttu-id="5c873-128">xsd: String de 32</span><span class="sxs-lookup"><span data-stu-id="5c873-128">xsd:string of 32</span></span>|  
|<span data-ttu-id="5c873-129">Byte</span><span class="sxs-lookup"><span data-stu-id="5c873-129">Byte</span></span>|<span data-ttu-id="5c873-130">Único carácter sin signo.</span><span class="sxs-lookup"><span data-stu-id="5c873-130">Single unsigned character.</span></span>|<span data-ttu-id="5c873-131">xsd:cadena de 1</span><span class="sxs-lookup"><span data-stu-id="5c873-131">xsd:string of 1</span></span>|  
|<span data-ttu-id="5c873-132">JDEUTIME</span><span class="sxs-lookup"><span data-stu-id="5c873-132">JDEUTIME</span></span>|<span data-ttu-id="5c873-133">Incluye tanto el componente de fecha como el de hora.</span><span class="sxs-lookup"><span data-stu-id="5c873-133">Includes both date and time components.</span></span><br /><br /> <span data-ttu-id="5c873-134">El tipo de datos almacena todas las fechas y horas y realiza todos los cálculos de fecha y hora en la hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="5c873-134">The data type stores all dates/times and performs all date/time calculations in Coordinated Universal Time (UTC).</span></span>|<span data-ttu-id="5c873-135">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="5c873-135">xsd:dateTime</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c873-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c873-136">See Also</span></span>  
 <span data-ttu-id="5c873-137">[Uso del tipo MATH_NUMERIC](../core/using-the-math-numeric-type1.md) </span><span class="sxs-lookup"><span data-stu-id="5c873-137">[Using the MATH_NUMERIC Type](../core/using-the-math-numeric-type1.md) </span></span>  
 <span data-ttu-id="5c873-138">[Control de valores de cadena](../core/handling-string-values2.md) </span><span class="sxs-lookup"><span data-stu-id="5c873-138">[Handling String Values](../core/handling-string-values2.md) </span></span>  
 [<span data-ttu-id="5c873-139">Apéndice B: tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5c873-139">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)