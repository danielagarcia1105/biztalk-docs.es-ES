---
title: Modos de análisis | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- pipeline components [custom], parsing
ms.assetid: b1188720-e5ae-47ae-ab8e-16d7ed08b778
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf8f9b2618b8cafd7813f08217457227a0f21809
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263308"
---
# <a name="parsing-modes"></a><span data-ttu-id="8331c-102">Modos de análisis</span><span class="sxs-lookup"><span data-stu-id="8331c-102">Parsing Modes</span></span>
<span data-ttu-id="8331c-103">El modo de análisis es un atributo en el registro schemaInfo que tiene dos modos: velocidad y complejidad.</span><span class="sxs-lookup"><span data-stu-id="8331c-103">The parsing mode is an attribute on the schemaInfo record, with two modes: speed and complexity.</span></span> <span data-ttu-id="8331c-104">La propiedad Optimización del analizador se puede configurar dentro del Editor de esquemas de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8331c-104">The Parser Optimization property can be configured within the BizTalk Schema Editor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8331c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8331c-105">Example</span></span>  
  
```  
<b:schemaInfo count_positions_by_byte="false" standard="Flat File"   
root_reference="document" parser_optimization="complexity" />.  
```  
  
 <span data-ttu-id="8331c-106">En el modo de velocidad, el analizador intenta ajustar datos conforme éstos aparecen en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="8331c-106">In speed mode, the parser tries to fit data as they appear in the stream.</span></span> <span data-ttu-id="8331c-107">Por ejemplo, dado el esquema siguiente.</span><span class="sxs-lookup"><span data-stu-id="8331c-107">For example, given the following schema.</span></span>  
  
```  
<schema>  
   Root ("," prefix)  
      Field1   opt  
      Field2   opt  
      Field3   opt  
      Field4   opt  
      Record ("," infix)  
            Field5  
            Field6  
</schema>  
```  
  
 <span data-ttu-id="8331c-108">y el mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="8331c-108">and input message.</span></span>  
  
```  
,1,2,3,4  
```  
  
 <span data-ttu-id="8331c-109">con el modo de velocidad se obtiene el siguiente documento XML.</span><span class="sxs-lookup"><span data-stu-id="8331c-109">with speed mode the following XML document is obtained.</span></span>  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
   <Field3>3</Field3>  
   <Field4>4</Field4>  
</Root>  
```  
  
 <span data-ttu-id="8331c-110">Con el modo de complejidad, el mismo esquema produce la siguiente salida.</span><span class="sxs-lookup"><span data-stu-id="8331c-110">With complexity mode, the same schema produces the following output.</span></span>  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
      <Record>  
         <Field5>3</Field5>  
         <Field6>4</Field6>  
      </Record>  
</Root>  
```  
  
 <span data-ttu-id="8331c-111">En el modo de complejidad, el motor de análisis del archivo sin formato utiliza tanto el análisis en orden descendente como ascendente e intenta ajustar datos con más precisión.</span><span class="sxs-lookup"><span data-stu-id="8331c-111">In complexity mode, the flat file parsing engine uses both top-down and bottom-up parsing, and tries to fit data more accurately.</span></span> <span data-ttu-id="8331c-112">En el modo de velocidad, el analizador intenta ajustar datos conforme éstos aparecen en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="8331c-112">In speed mode, the parser tries to fit data as they appear in the stream.</span></span>  
  
 <span data-ttu-id="8331c-113">Si tiene elementos opcionales con elementos necesarios, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8331c-113">If you have optional elements with required elements, for example.</span></span>  
  
```  
<schema>  
   Root  
      Record1 (required)  
  
      Record2 (optional)  
  
      Record3 (required)  
  
```  
  
 <span data-ttu-id="8331c-114">Debe utilizar el modo de complejidad para analizar correctamente los datos, ya que el analizador representa el esquema internamente de la siguiente forma.</span><span class="sxs-lookup"><span data-stu-id="8331c-114">you must use complexity mode to correctly parse the data, because the parser represents the schema internally as.</span></span>  
  
```  
<schema>  
   Root  
      Record1 (required)  
      <sequence> (optional)  
         Record2 (required)  
         Record3 (required)  
```  
  
## <a name="see-also"></a><span data-ttu-id="8331c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8331c-115">See Also</span></span>  
 [<span data-ttu-id="8331c-116">Usar el motor de análisis de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="8331c-116">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)