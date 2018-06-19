---
title: Migrar registros de archivo sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75cd5fbc-66c1-4c8b-b81a-1d028e9647b4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddd43c231077f4e23efca374edbda5bf152f1415
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710823"
---
# <a name="migrate-flat-file-records"></a><span data-ttu-id="475cd-102">Migrar registros de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="475cd-102">Migrate Flat File Records</span></span>

## <a name="overview"></a><span data-ttu-id="475cd-103">Información general</span><span class="sxs-lookup"><span data-stu-id="475cd-103">Overview</span></span>
<span data-ttu-id="475cd-104">Microsoft BizTalk Server es compatible con varios caracteres delimitadores, aunque admite solo un tipo de delimitador: delimitador secundario.</span><span class="sxs-lookup"><span data-stu-id="475cd-104">Microsoft BizTalk Server supports multi-character delimiters, although it supports only one type of delimiter—child delimiter.</span></span> 
  
 <span data-ttu-id="475cd-105">Tres anotaciones de esquema controlan el tratamiento de delimitadores en BizTalk Server: dos para el análisis (**skip_CR**, **skip_LF**) y uno para la serialización (**append_newline**).</span><span class="sxs-lookup"><span data-stu-id="475cd-105">Three schema annotations control delimiter handling in BizTalk Server: two for parsing (**skip_CR**, **skip_LF**), and one for serializing (**append_newline**).</span></span> <span data-ttu-id="475cd-106">BizTalk Server interpreta estas anotaciones al migrar los siguientes registros:</span><span class="sxs-lookup"><span data-stu-id="475cd-106">BizTalk Server interprets these annotations as follows when migrating records:</span></span>  
  
-   <span data-ttu-id="475cd-107">Si el **skip_CR** anotación tiene un valor de **true** y el delimitador actual no es un retorno de carro (0x0D), BizTalk Server agrega un retorno de carro al delimitador actual.</span><span class="sxs-lookup"><span data-stu-id="475cd-107">If the **skip_CR** annotation has a value of **true** and the current delimiter is not carriage return (0x0D), BizTalk Server adds a carriage return to the current delimiter.</span></span> <span data-ttu-id="475cd-108">Por ejemplo, si el delimitador actual fuese el símbolo de canalización (0x7C), el delimitador resultante sería un símbolo de canalización seguido de un retorno de carro (0x7C 0x0D).</span><span class="sxs-lookup"><span data-stu-id="475cd-108">For example, if the current delimiter were the pipe symbol (0x7C), the resulting delimiter is a pipe symbol followed by a carriage return (0x7C 0x0D).</span></span> <span data-ttu-id="475cd-109">Si el delimitador actual es un retorno de carro, permanece como un solo retorno de carro, el valor de **skip_CR**.</span><span class="sxs-lookup"><span data-stu-id="475cd-109">If the current delimiter is carriage return, it remains as a single carriage return regardless of the value of **skip_CR**.</span></span>  
  
-   <span data-ttu-id="475cd-110">Si el **skip_LF** anotación tiene un valor de **true**, BizTalk Server agrega un salto de línea de caracteres (0x0A) al delimitador actual.</span><span class="sxs-lookup"><span data-stu-id="475cd-110">If the **skip_LF** annotation has a value of **true**, BizTalk Server adds a linefeed character (0x0A) to the current delimiter.</span></span> <span data-ttu-id="475cd-111">Observe que en el caso anterior donde el delimitador actual es el símbolo de canalización (0x7C), se produce un delimitador de tres caracteres (0x7C 0x0D 0x0A) si ambos **skip_CR** y **skip_LF** son **true**.</span><span class="sxs-lookup"><span data-stu-id="475cd-111">Notice that in the preceding case where the current delimiter is the pipe symbol (0x7C), a three character delimiter results (0x7C 0x0D 0x0A) if both **skip_CR** and **skip_LF** are **true**.</span></span>  
  
-   <span data-ttu-id="475cd-112">BizTalk Server pasa por alto la configuración de la **append_newline** anotación.</span><span class="sxs-lookup"><span data-stu-id="475cd-112">BizTalk Server ignores the setting of the **append_newline** annotation.</span></span>  
  
 <span data-ttu-id="475cd-113">Mientras que estas interpretaciones de las anotaciones garantizan una migración sin problemas en la mayoría de casos, hay algunos casos en los que se producen errores.</span><span class="sxs-lookup"><span data-stu-id="475cd-113">While these interpretations of the annotations ensure the majority of cases migrate without difficulty, there are some cases where migration fails.</span></span> <span data-ttu-id="475cd-114">Por ejemplo, si **skip_CR** y **skip_LF** son **true** y el delimitador actual es el símbolo de canalización (0x7C), BizTalk Server acepta todas las opciones siguientes como válidos delimitadores en un único conjunto de registros: 0x7C 0x0D 0x0A, 0x7C 0x0D, 0x7C 0x0A y 0x7C.</span><span class="sxs-lookup"><span data-stu-id="475cd-114">For example, if **skip_CR** and **skip_LF** are both **true** and the current delimiter is the pipe symbol (0x7C), BizTalk Server accepts all of the following as valid delimiters within a single set of records: 0x7C 0x0D 0x0A, 0x7C 0x0D, 0x7C 0x0A, and 0x7C.</span></span> <span data-ttu-id="475cd-115">Los registros mediante estos conjuntos de delimitadores no se pueden migrar y necesitan un código de analizador personalizado en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="475cd-115">Records using such sets of delimiters cannot be migrated and require custom parser code in BizTalk Server.</span></span>  
  
 <span data-ttu-id="475cd-116">Aunque BizTalk Server tiene un único tipo de delimitador, interpreta las anotaciones antiguas para que los registros se migren fácilmente.</span><span class="sxs-lookup"><span data-stu-id="475cd-116">Although BizTalk Server has only one type of delimiter, it interprets the old annotations so that records migrate easily.</span></span> <span data-ttu-id="475cd-117">Si un esquema de BizTalk Server tiene valores para **def_record_delimdef_field_delim**, **def_field_delim**, y estos se hace referencia en **delimiter_type** como **inherit_record**, y así sucesivamente, BizTalk Server recupera el valor correspondiente y lo almacena localmente.</span><span class="sxs-lookup"><span data-stu-id="475cd-117">If a BizTalk Server schema has values for **def_record_delimdef_field_delim**, **def_subfield_delim**, and these are referenced in **delimiter_type** as **inherit_record**, and so on, BizTalk Server retrieves the corresponding value and stores it locally.</span></span>  
  
 <span data-ttu-id="475cd-118">Además, BizTalk Server agrega campos para registros posicionales etiquetados sin elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="475cd-118">In addition, BizTalk Server adds fields for tagged positional records without children.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="475cd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="475cd-119">See Also</span></span>  
 [<span data-ttu-id="475cd-120">Problemas conocidos relacionados con la generación y validación de esquemas</span><span class="sxs-lookup"><span data-stu-id="475cd-120">Known Issues with Schema Generation and Validation</span></span>](../core/known-issues-with-schema-generation-and-validation.md)