---
title: Anidar registros delimitados y posicionales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1688f04-d3c7-492c-82f7-a734bec0e409
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3896eb41a52ee356021a6fcf7e7621267f8764f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971221"
---
# <a name="nested-positional-and-delimited-records"></a><span data-ttu-id="0a80a-102">Registros delimitados y posicionales anidados</span><span class="sxs-lookup"><span data-stu-id="0a80a-102">Nested Positional and Delimited Records</span></span>
<span data-ttu-id="0a80a-103">En los formatos de archivo sin formato compatibles con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se permiten algunas combinaciones de registros delimitados y posicionales y otras no.</span><span class="sxs-lookup"><span data-stu-id="0a80a-103">In the flat file formats supported by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some combinations of positional and delimited records are allowed and others are disallowed.</span></span> <span data-ttu-id="0a80a-104">Se permiten las siguientes combinaciones:</span><span class="sxs-lookup"><span data-stu-id="0a80a-104">The following combinations are allowed:</span></span>  
  
- <span data-ttu-id="0a80a-105">Los archivos sin formato en los que se usan delimitadores para determinar los límites entre todos los registros y los registros subordinados entre sí, y en los que se utilizan delimitadores (probablemente diferentes) para separar los campos dentro de estos registros.</span><span class="sxs-lookup"><span data-stu-id="0a80a-105">Flat files in which delimiters are used to determine the boundaries between all records and their subordinate records from each other, and in which (possibly different) delimiters are used to separate the fields within those records.</span></span>  
  
- <span data-ttu-id="0a80a-106">Los archivos sin formato en los que los límites entre todos los registros, los registros subordinados y los campos se determinan en función de la posición que ocupan dentro del archivo según longitudes predefinidas de registro y campo.</span><span class="sxs-lookup"><span data-stu-id="0a80a-106">Flat files in which the boundaries between all records, their subordinate records, and their fields are determined based on their position within the file according to predefined record and field lengths.</span></span>  
  
- <span data-ttu-id="0a80a-107">Los archivos sin formato en los que se usan delimitadores para determinar los límites entre, como mínimo, el conjunto de registros más externo del archivo y en los que se utiliza una combinación de registros delimitados y posicionales subordinados.</span><span class="sxs-lookup"><span data-stu-id="0a80a-107">Flat files in which delimiters are used to determine the boundaries between at least the outermost set of records in the file, and in which a mix of delimited and positional subordinate records are used.</span></span> <span data-ttu-id="0a80a-108">Los límites entre los campos de un registro delimitado o posicional subordinado se determinan mediante delimitadores o longitudes de campo fijas, respectivamente</span><span class="sxs-lookup"><span data-stu-id="0a80a-108">Boundaries between the fields within a delimited or positional subordinate record are determined using either delimiters or fixed field lengths, respectively.</span></span> <span data-ttu-id="0a80a-109">Los registros subordinados de un registro posicional (subordinado) también deben ser posicionales; es decir, una vez que una parte del archivo cambia de registros delimitados a posicionales, toda la parte subordinada del archivo debe ser posicional.</span><span class="sxs-lookup"><span data-stu-id="0a80a-109">The subordinate records of a positional (subordinate) record must also be positional; in other words, once a portion of the file switches from delimited to positional records, that entire subordinate portion of the file must be positional.</span></span>  
  
  <span data-ttu-id="0a80a-110">Debido a las ambigüedades de análisis que podrían resultar, los registros posicionales no pueden contener registros subordinados delimitados, con independencia de dónde aparezcan.</span><span class="sxs-lookup"><span data-stu-id="0a80a-110">Due to the parsing ambiguities that would result, positional records, wherever they occur, are prohibited from containing delimited subordinate records.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a80a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a80a-111">See Also</span></span>  
 [<span data-ttu-id="0a80a-112">Consideraciones al crear esquemas de mensajes de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="0a80a-112">Considerations When Creating Flat File Message Schemas</span></span>](../core/considerations-when-creating-flat-file-message-schemas.md)