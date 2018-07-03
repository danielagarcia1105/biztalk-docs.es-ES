---
title: Asignar componentes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper, output
- maps, file type
- maps, file contents
- BizTalk Mapper, file type
- maps, components
ms.assetid: be438d21-80a8-49d8-bd08-d85618ab23de
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1590ad1450453602b4dd5f25b2d52a4364787af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996773"
---
# <a name="map-components"></a><span data-ttu-id="1ed91-102">Componentes de asignaciones</span><span class="sxs-lookup"><span data-stu-id="1ed91-102">Map Components</span></span>
<span data-ttu-id="1ed91-103">Los archivos de asignación (extensión .btm) almacenan la mayoría de los componentes de una asignación.</span><span class="sxs-lookup"><span data-stu-id="1ed91-103">Map files (having a .btm extension) store most of the components of a map.</span></span> <span data-ttu-id="1ed91-104">Los elementos almacenados en el archivo incluyen:</span><span class="sxs-lookup"><span data-stu-id="1ed91-104">Items stored in the file include:</span></span>  
  
- <span data-ttu-id="1ed91-105">Referencias a los esquemas de origen y de destino</span><span class="sxs-lookup"><span data-stu-id="1ed91-105">References to source and destination schemas</span></span>  
  
- <span data-ttu-id="1ed91-106">Vínculos, incluidas las propiedades de vínculos</span><span class="sxs-lookup"><span data-stu-id="1ed91-106">Links, including the link properties</span></span>  
  
- <span data-ttu-id="1ed91-107">Functoids, con sus propiedades, como los parámetros de entrada</span><span class="sxs-lookup"><span data-stu-id="1ed91-107">Functoids with their properties such as input parameters</span></span>  
  
- <span data-ttu-id="1ed91-108">Otras propiedades varias, como las asociadas con la propia asignación y la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="1ed91-108">Other miscellaneous properties such as those associated with the grid and the map itself.</span></span>  
  
  <span data-ttu-id="1ed91-109">Aunque el Asignador de BizTalk compila la asignación del archivo .btm en un archivo de Transformación de lenguaje de hojas de estilo extensible (XSLT), el XSLT no forma parte del archivo.</span><span class="sxs-lookup"><span data-stu-id="1ed91-109">Although BizTalk Mapper compiles the map in the .btm file into an Extensible Stylesheet Transformations (XSLT) file, the XSLT is not part of the file.</span></span> <span data-ttu-id="1ed91-110">El Asignador de BizTalk produce el XSLT para la asignación solo cuando se compila el proyecto o cuando se valida la asignación.</span><span class="sxs-lookup"><span data-stu-id="1ed91-110">BizTalk Mapper produces the XSLT for the map only when you compile the project or when you validate the map.</span></span> <span data-ttu-id="1ed91-111">El Asignador de BizTalk empaqueta el XSLT como parte del ensamblado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1ed91-111">BizTalk Mapper packages the XSLT as part of the project assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed91-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ed91-112">See Also</span></span>  
 <span data-ttu-id="1ed91-113">[Mapas](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="1ed91-113">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="1ed91-114">Creación de mapas con el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="1ed91-114">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)