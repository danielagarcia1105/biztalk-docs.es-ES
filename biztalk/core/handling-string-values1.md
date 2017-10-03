---
title: Control de cadena Values1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, configuring strings
- strings, left-justified
- strings, configuring
- strings, right-justified
ms.assetid: a180b818-1009-45f5-a503-d10ed7dd27fc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f32b29b9a8688fe8402730c1db8f12e42a67bab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="handling-string-values"></a><span data-ttu-id="309a1-102">Control de valores de cadena</span><span class="sxs-lookup"><span data-stu-id="309a1-102">Handling String Values</span></span>
<span data-ttu-id="309a1-103">En este tema se describe cómo configurar ciertos argumentos de cadena como justificado a la derecha (y relleno a la izquierda).</span><span class="sxs-lookup"><span data-stu-id="309a1-103">This topic describes how to configure certain string arguments as right-justified (and left padded).</span></span>  
  
## <a name="types-of-string-values"></a><span data-ttu-id="309a1-104">Tipos de valores de cadena</span><span class="sxs-lookup"><span data-stu-id="309a1-104">Types of String Values</span></span>  
 <span data-ttu-id="309a1-105">JD Edwards OneWorld muestra dos clases de valores de cadena en su capa de interoperabilidad:</span><span class="sxs-lookup"><span data-stu-id="309a1-105">JD Edwards OneWorld exposes two kinds of string values through its interoperability layer:</span></span>  
  
-   <span data-ttu-id="309a1-106">Char: un único carácter</span><span class="sxs-lookup"><span data-stu-id="309a1-106">Char: a single character</span></span>  
  
-   <span data-ttu-id="309a1-107">cadena de longitud máxima</span><span class="sxs-lookup"><span data-stu-id="309a1-107">maximum length string</span></span>  
  
 <span data-ttu-id="309a1-108">JD Edwards OneWorld usa la notación húngara para nombrar los argumentos de estos tipos en las funciones de negocio.</span><span class="sxs-lookup"><span data-stu-id="309a1-108">JD Edwards OneWorld uses Hungarian notation to name the arguments of these types in the business functions.</span></span> <span data-ttu-id="309a1-109">Por ejemplo, los argumentos de estos tipos de comenzar con:</span><span class="sxs-lookup"><span data-stu-id="309a1-109">For example, arguments of these types begin with:</span></span>  
  
-   <span data-ttu-id="309a1-110">c</span><span class="sxs-lookup"><span data-stu-id="309a1-110">c</span></span>  
  
-   <span data-ttu-id="309a1-111">sz</span><span class="sxs-lookup"><span data-stu-id="309a1-111">sz</span></span>  
  
### <a name="left-justified-values"></a><span data-ttu-id="309a1-112">Valores justificados a la izquierda</span><span class="sxs-lookup"><span data-stu-id="309a1-112">Left-Justified Values</span></span>  
 <span data-ttu-id="309a1-113">Para una mayoría de argumentos de tipo sz, cadena de longitud máxima o matriz de caracteres, JD Edwards OneWorld espera un valor justificado a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="309a1-113">For a majority of sz-type arguments, maximum length string or char array, JD Edwards OneWorld expects a left-justified value.</span></span> <span data-ttu-id="309a1-114">Para una línea de dirección de calle, cuya longitud máxima es 40, JD Edwards OneWorld espera (por ejemplo):</span><span class="sxs-lookup"><span data-stu-id="309a1-114">For a street address line, which is of maximum length 40, JD Edwards OneWorld expects (for example):</span></span>  
  
 <span data-ttu-id="309a1-115">"4567 Main St."</span><span class="sxs-lookup"><span data-stu-id="309a1-115">"4567 Main St.       "</span></span>  
  
 <span data-ttu-id="309a1-116">relleno hasta completar la longitud 40 con espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="309a1-116">padded to length 40 with blanks.</span></span> <span data-ttu-id="309a1-117">No es necesario que especifique el relleno porque Microsoft BizTalk Adapter para JD Edwards OneWorld lo proporciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="309a1-117">It is not necessary for you to enter the padding because Microsoft BizTalk Adapter for JD Edwards OneWorld provides this for you.</span></span> <span data-ttu-id="309a1-118">Únicamente debe escribir "4567 Main St.", en el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="309a1-118">You only need to enter "4567 Main St.", in your client code.</span></span>  
  
### <a name="right-justified-values"></a><span data-ttu-id="309a1-119">Valores justificados a la derecha</span><span class="sxs-lookup"><span data-stu-id="309a1-119">Right-Justified Values</span></span>  
 <span data-ttu-id="309a1-120">Para algunos subconjuntos de valores de este tipo, JD Edwards OneWorld espera valores justificados a la derecha con relleno a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="309a1-120">For some subset of values for this type, JD Edwards OneWorld expects values that are right justified with padding on the left.</span></span> <span data-ttu-id="309a1-121">Por ejemplo, para las funciones de negocio en el módulo de origen B4200310, el argumento szBusinessUnit es de longitud 12.</span><span class="sxs-lookup"><span data-stu-id="309a1-121">For example, for business functions in the B4200310 source module, the argument szBusinessUnit is of length 12.</span></span> <span data-ttu-id="309a1-122">Este argumento representa una planta, como una instalación de producción.</span><span class="sxs-lookup"><span data-stu-id="309a1-122">This argument represents a plant, such as a production facility.</span></span> <span data-ttu-id="309a1-123">Para un número de planta de 30, J.D.</span><span class="sxs-lookup"><span data-stu-id="309a1-123">For a plant number of 30, J.D.</span></span> <span data-ttu-id="309a1-124">Edwards OneWorld XE espera un valor de:</span><span class="sxs-lookup"><span data-stu-id="309a1-124">Edwards OneWorld XE expects a value of:</span></span>  
  
 <span data-ttu-id="309a1-125">"          30"</span><span class="sxs-lookup"><span data-stu-id="309a1-125">"          30"</span></span>  
  
 <span data-ttu-id="309a1-126">Para especificar un valor que estará justificado a la derecha, debe especificar el parámetro en un archivo denominado jdearglist.txt.</span><span class="sxs-lookup"><span data-stu-id="309a1-126">To enter a value that will be right-justified, you must enter the parameter in a file called jdearglist.txt.</span></span> <span data-ttu-id="309a1-127">El archivo jdearglist.txt se lee al generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="309a1-127">The jdearglist.txt is read when you generate the schema.</span></span> <span data-ttu-id="309a1-128">Cualquier valor que se indique en este archivo de texto se convierte automáticamente en un valor justificado a la derecha y rellenado a la izquierda con espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="309a1-128">Any value that is listed in this text file is automatically converted to a right-justified value and padded on the left with blanks.</span></span>  
  
 <span data-ttu-id="309a1-129">Debe crear jdearglist.txt usando un texto de editor, con las entradas que describen estos parámetros y guárdelo en la siguiente carpeta: %BizTalk_Install_Adapter%\config\JDE\\</span><span class="sxs-lookup"><span data-stu-id="309a1-129">You must create jdearglist.txt using a text editor, with entries describing these parameters, and save it in the following folder: %BizTalk_Install_Adapter%\config\JDE\\</span></span>  
  
 <span data-ttu-id="309a1-130">Donde **BizTalk_Install_Adapter %** es el directorio en el que instaló el adaptador de BizTalk para JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="309a1-130">Where **%BizTalk_Install_Adapter%** is the directory in which you installed BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
 <span data-ttu-id="309a1-131">Si este archivo no existe o está vacío, aparece un mensaje informativo en el registro de BizTalk Adapter para JD Edwards OneWorld cuando se abre el adaptador por primera vez.</span><span class="sxs-lookup"><span data-stu-id="309a1-131">If this file does not exist or is empty, an informational message appears in the BizTalk Adapter for JD Edwards OneWorld log when the adapter first opens.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="309a1-132">Si cambia este archivo después de la generación del esquema, deberá volver a generar el esquema para actualizar los datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="309a1-132">If you change this file after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span>  
  
 <span data-ttu-id="309a1-133">Para verificar que está usando la información más reciente de este archivo, puede usar el Administrador de tareas para detener el proceso browsingagent.exe antes de regenerar el esquema; no obstante, esto no debería ser necesario.</span><span class="sxs-lookup"><span data-stu-id="309a1-133">To verify that you are using the latest information in this file, you can use the Task Manager to stop the browsingagent.exe process before regenerating your schema; however, this should not be necessary.</span></span>  
  
 <span data-ttu-id="309a1-134">A continuación  se muestra un ejemplo del formato para entradas del archivo jdearglist.txt:</span><span class="sxs-lookup"><span data-stu-id="309a1-134">The following is an example of the format for entries in the jdearglist.txt file:</span></span>  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
```  
  
 <span data-ttu-id="309a1-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="309a1-135">For example:</span></span>  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 <span data-ttu-id="309a1-136">Para un conjunto de funciones empresariales que pertenezcan al mismo módulo empresarial, los argumentos con nombre similar (del mismo tipo) se comparten entre algunas o todas las funciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="309a1-136">For a set of business functions belonging to the same business module, like-named arguments (of the same type) are shared across some or all of the business functions.</span></span> <span data-ttu-id="309a1-137">Puede usar el carácter comodín (*) en lugar del nombre de la función empresarial.</span><span class="sxs-lookup"><span data-stu-id="309a1-137">You can use the wildcard character (*) instead of the business function name.</span></span> <span data-ttu-id="309a1-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="309a1-138">For example:</span></span>  
  
```  
B4200310.*.szBusinessUnit  
```  
  
> [!NOTE]
>  <span data-ttu-id="309a1-139">Al importar un proceso de negocio de JD Edwards OneWorld a otro equipo, debe copiar jdearglist.txt manualmente.</span><span class="sxs-lookup"><span data-stu-id="309a1-139">When importing a JD Edwards OneWorld business process to another computer, you must copy jdearglist.txt manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="309a1-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="309a1-140">See Also</span></span>  
 <span data-ttu-id="309a1-141">[Configuración de justificación de cadena en Jdearglist](../core/setting-string-justification-in-jdearglist.md) </span><span class="sxs-lookup"><span data-stu-id="309a1-141">[Setting String Justification in Jdearglist](../core/setting-string-justification-in-jdearglist.md) </span></span>  
 [<span data-ttu-id="309a1-142">Apéndice A: tipos de datos</span><span class="sxs-lookup"><span data-stu-id="309a1-142">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)