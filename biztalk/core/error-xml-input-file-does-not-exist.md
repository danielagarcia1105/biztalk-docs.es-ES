---
title: 'Error: no existe el archivo de entrada de XML | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.xmlInputFileDoesNotExist
ms.assetid: d222e615-60c8-46f5-a8de-fc59650978c7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4b70e749565bcf33f99c39faa0653c7fd952e9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---xml-input-file-does-not-exist"></a><span data-ttu-id="73b61-102">Error: no existe el archivo de entrada de XML</span><span class="sxs-lookup"><span data-stu-id="73b61-102">Error - XML Input File Does Not Exist</span></span>
<span data-ttu-id="73b61-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="73b61-103">**Error Code**</span></span>  
  
 <span data-ttu-id="73b61-104">btm1039</span><span class="sxs-lookup"><span data-stu-id="73b61-104">btm1039</span></span>  
  
 <span data-ttu-id="73b61-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="73b61-105">**Explanation**</span></span>  
  
 <span data-ttu-id="73b61-106">El archivo de mensaje de instancia de entrada XML especificado para la operación Comprobar asignación no existe.</span><span class="sxs-lookup"><span data-stu-id="73b61-106">The XML input instance message file specified for the Test Map operation does not exist.</span></span> <span data-ttu-id="73b61-107">Cuando el valor de la **entrada de comprobar asignación** asignar la propiedad se establece en XML, debe especificar un archivo de mensaje de instancia XML existente para la **instancia de entrada de comprobar asignación** asignar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="73b61-107">When the value of the **TestMap Input** map property is set to XML, you must specify an existing XML instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="73b61-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="73b61-108">**User Action**</span></span>  
  
 <span data-ttu-id="73b61-109">Haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña en el **páginas de propiedades** cuadro de diálogo para la asignación, haga clic en los puntos suspensivos () **...** ) botón en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="73b61-109">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="73b61-110">Mediante el **Seleccionar archivo de entrada** cuadro de diálogo, seleccione archivo de mensaje que se ajusta al esquema de origen del mapa de la instancia de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="73b61-110">Using the **Select Input File** dialog box, select an existing XML instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="73b61-111">Como alternativa, puede escribir la ruta de acceso de este archivo XML directamente en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="73b61-111">Alternatively, you can type the path of this XML file directly into the value field of the **TestMap Input Instance** property.</span></span>