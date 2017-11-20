---
title: Control de cadena Values2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- string values, configuring
- formatting strings
- strings, formatting
- left-justified string values
- jdearglist.txt
- strings, left-justified
- right-justified string values
- strings, right-justified
ms.assetid: 23d54731-b2b9-4610-a533-e041237e0bb3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 024663faa56d92361d861a61a0d64a4608839aa6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="handling-string-values"></a><span data-ttu-id="291df-102">Control de valores de cadena</span><span class="sxs-lookup"><span data-stu-id="291df-102">Handling String Values</span></span>
<span data-ttu-id="291df-103">En este tema se describe cómo configurar ciertos argumentos de cadena como justificado a la derecha (y relleno a la izquierda).</span><span class="sxs-lookup"><span data-stu-id="291df-103">This topic describes how to configure certain string arguments as right-justified (and left padded).</span></span>  
  
## <a name="types-of-string-values"></a><span data-ttu-id="291df-104">Tipos de valores de cadena</span><span class="sxs-lookup"><span data-stu-id="291df-104">Types of String Values</span></span>  
 <span data-ttu-id="291df-105">JD Edwards EnterpriseOne expone dos tipos de valores de cadena a través de su capa de interoperabilidad:</span><span class="sxs-lookup"><span data-stu-id="291df-105">JD Edwards EnterpriseOne exposes two kinds of string values through its interoperability layer:</span></span>  
  
-   <span data-ttu-id="291df-106">Char: un único carácter</span><span class="sxs-lookup"><span data-stu-id="291df-106">char: a single character</span></span>  
  
-   <span data-ttu-id="291df-107">cadena de longitud máxima</span><span class="sxs-lookup"><span data-stu-id="291df-107">maximum length string</span></span>  
  
 <span data-ttu-id="291df-108">JD Edwards EnterpriseOne usa la notación en húngaro para asignar nombre a los argumentos de estos tipos en las funciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="291df-108">JD Edwards EnterpriseOne uses Hungarian notation to name the arguments of these types in the business functions.</span></span> <span data-ttu-id="291df-109">Por ejemplo, los argumentos de estos tipos de comenzar con:</span><span class="sxs-lookup"><span data-stu-id="291df-109">For example, arguments of these types begin with:</span></span>  
  
-   <span data-ttu-id="291df-110">c</span><span class="sxs-lookup"><span data-stu-id="291df-110">c</span></span>  
  
-   <span data-ttu-id="291df-111">sz</span><span class="sxs-lookup"><span data-stu-id="291df-111">sz</span></span>  
  
### <a name="left-justified-values"></a><span data-ttu-id="291df-112">Valores justificados a la izquierda</span><span class="sxs-lookup"><span data-stu-id="291df-112">Left-Justified Values</span></span>  
 <span data-ttu-id="291df-113">Para la mayoría de argumentos de tipo sz, la cadena de longitud máxima o la matriz char, JD Edwards EnterpriseOne espera un valor justificado a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="291df-113">For a majority of sz-type arguments, maximum length string or char array, JD Edwards EnterpriseOne expects a left-justified value.</span></span> <span data-ttu-id="291df-114">Por ejemplo, para una línea de dirección postal, que tiene una longitud máxima de 40, JD Edwards EnterpriseOne espera (por ejemplo):</span><span class="sxs-lookup"><span data-stu-id="291df-114">For examples, for a street address line, which is of maximum length 40, JD Edwards EnterpriseOne expects (for example):</span></span>  
  
 <span data-ttu-id="291df-115">"4567 Main St.       "</span><span class="sxs-lookup"><span data-stu-id="291df-115">"4567 Main St.    "</span></span>  
  
 <span data-ttu-id="291df-116">relleno hasta completar la longitud 40 con espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="291df-116">padded to length 40 with blanks.</span></span> <span data-ttu-id="291df-117">No es necesario que escriba el relleno porque el Adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne lo proporciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="291df-117">It is not necessary for you to enter the padding because Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides this for you.</span></span> <span data-ttu-id="291df-118">solo tiene que escribir "4567 Main St" en el código del cliente.</span><span class="sxs-lookup"><span data-stu-id="291df-118">You only need to enter "4567 Main St ", in your client code.</span></span>  
  
### <a name="right-justified-values"></a><span data-ttu-id="291df-119">Valores justificados a la derecha</span><span class="sxs-lookup"><span data-stu-id="291df-119">Right-Justified Values</span></span>  
 <span data-ttu-id="291df-120">Para algunos subconjuntos de valores para este tipo, JD Edwards EnterpriseOne espera valores que están justificados a la derecha con relleno en la izquierda.</span><span class="sxs-lookup"><span data-stu-id="291df-120">For some subset of values for this type, JD Edwards EnterpriseOne expects values that are right justified with padding on the left.</span></span> <span data-ttu-id="291df-121">Por ejemplo, para las funciones de negocio en el módulo de origen B4200310, el argumento szBusinessUnit es de longitud 12.</span><span class="sxs-lookup"><span data-stu-id="291df-121">For example, for business functions in the B4200310 source module, the argument szBusinessUnit is of length 12.</span></span> <span data-ttu-id="291df-122">Este argumento representa una planta, como una instalación de producción.</span><span class="sxs-lookup"><span data-stu-id="291df-122">This argument represents a plant, such as a production facility.</span></span> <span data-ttu-id="291df-123">Para un número de plantas de 30, JD Edwards EnterpriseOne espera un valor de:</span><span class="sxs-lookup"><span data-stu-id="291df-123">For a plant number of 30, JD Edwards EnterpriseOne expects a value of:</span></span>  
  
 <span data-ttu-id="291df-124">"           30"</span><span class="sxs-lookup"><span data-stu-id="291df-124">"           30"</span></span>  
  
 <span data-ttu-id="291df-125">Para especificar un valor que estará justificado a la derecha, debe especificar el parámetro en un archivo denominado jdearglist.txt.</span><span class="sxs-lookup"><span data-stu-id="291df-125">To enter a value that will be right-justified, you must enter the parameter in a file called jdearglist.txt.</span></span> <span data-ttu-id="291df-126">El archivo jdearglist.txt se lee al generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="291df-126">The jdearglist.txt is read when you generate the schema.</span></span> <span data-ttu-id="291df-127">Cualquier valor de este archivo de texto se convierte automáticamente en un valor justificado a la derecha y relleno a la izquierda con espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="291df-127">Any value in this text file is automatically converted to a right-justified value and padded on the left with blanks.</span></span>  
  
 <span data-ttu-id="291df-128">Debe crear jdearglist.txt usando un editor de texto, con entradas que describen estos parámetros, y guardarlo en la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="291df-128">You must create jdearglist.txt using a text editor, with entries describing these parameters, and save it in the following folder:</span></span>  
  
 <span data-ttu-id="291df-129">C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config</span><span class="sxs-lookup"><span data-stu-id="291df-129">C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config</span></span>  
  
 <span data-ttu-id="291df-130">Si este archivo no existe o está vacío, aparecerá un mensaje informativo en el registro del Adaptador de BizTalk para JD Edwards EnterpriseOne la primera vez que se abre el adaptador.</span><span class="sxs-lookup"><span data-stu-id="291df-130">If this file does not exist or is empty, an informational message appears in BizTalk Adapter for JD Edwards EnterpriseOne log when the adapter first opens.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="291df-131">Si cambia este archivo después de la generación del esquema, deberá volver a generar el esquema para actualizar los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="291df-131">If you change this file after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="291df-132">Para verificar que está usando la información más reciente de este archivo, puede usar el Administrador de tareas para detener el proceso browsingagent.exe antes de regenerar el esquema; no obstante, esto no debería ser necesario.</span><span class="sxs-lookup"><span data-stu-id="291df-132">To verify that you are using the latest information in this file, you can use the Task Manager to stop the browsingagent.exe process before regenerating your schema; however, this should not be necessary.</span></span>  
  
 <span data-ttu-id="291df-133">A continuación  se muestra un ejemplo del formato para entradas del archivo jdearglist.txt:</span><span class="sxs-lookup"><span data-stu-id="291df-133">The following is an example of the format for entries in the jdearglist.txt file:</span></span>  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
  
```  
  
 <span data-ttu-id="291df-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="291df-134">For example:</span></span>  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 <span data-ttu-id="291df-135">Para un conjunto de funciones empresariales que pertenezcan al mismo módulo empresarial, los argumentos con nombre similar (del mismo tipo) se comparten entre algunas o todas las funciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="291df-135">For a set of business functions belonging to the same business module, like-named arguments (of the same type) are shared across some or all of the business functions.</span></span> <span data-ttu-id="291df-136">Puede usar el carácter comodín (*) en lugar del nombre de la función empresarial.</span><span class="sxs-lookup"><span data-stu-id="291df-136">You can use the wildcard character (*) instead of the business function name.</span></span> <span data-ttu-id="291df-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="291df-137">For example:</span></span>  
  
```  
B4200310.*.szBusinessUnit  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="291df-138">Al importar un proceso empresarial de JD Edwards EnterpriseOne a otro equipo, debe copiar manualmente jdearglist.txt.</span><span class="sxs-lookup"><span data-stu-id="291df-138">When importing a JD Edwards EnterpriseOne business process to another computer, you must copy jdearglist.txt manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="291df-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="291df-139">See Also</span></span>  
 [<span data-ttu-id="291df-140">Apéndice B: tipos de datos</span><span class="sxs-lookup"><span data-stu-id="291df-140">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)