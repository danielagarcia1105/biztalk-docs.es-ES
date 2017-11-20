---
title: 'Error: archivo de entrada nativo no existe | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.nativeInputFileDoesNotExist
ms.assetid: 17713896-8557-4bf1-b5f0-871b905ae15e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 333849007c808a20130f10dfb1f22a756024a4c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---native-input-file-does-not-exist"></a><span data-ttu-id="a99c6-102">Error: archivo de entrada nativo no existe</span><span class="sxs-lookup"><span data-stu-id="a99c6-102">Error - Native Input File Does Not Exist</span></span>
<span data-ttu-id="a99c6-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="a99c6-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a99c6-104">btm1040</span><span class="sxs-lookup"><span data-stu-id="a99c6-104">btm1040</span></span>  
  
 <span data-ttu-id="a99c6-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="a99c6-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a99c6-106">El archivo de mensaje de instancia de entrada nativo especificado para la operación Comprobar asignación no existe.</span><span class="sxs-lookup"><span data-stu-id="a99c6-106">The native input instance message file specified for the Test Map operation does not exist.</span></span> <span data-ttu-id="a99c6-107">Cuando el valor de la **entrada de comprobar asignación** asignar la propiedad se establece en **nativo**, debe especificar un archivo de mensaje de instancia nativo existente para la **instancia de entrada de comprobar asignación** mapa propiedad.</span><span class="sxs-lookup"><span data-stu-id="a99c6-107">When the value of the **TestMap Input** map property is set to **Native**, you must specify an existing native instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="a99c6-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="a99c6-108">**User Action**</span></span>  
  
 <span data-ttu-id="a99c6-109">Haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña en el **páginas de propiedades** cuadro de diálogo para la asignación, haga clic en los puntos suspensivos () **...** ) botón en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="a99c6-109">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="a99c6-110">En el **Seleccionar archivo de entrada** cuadro de diálogo, seleccione archivo de mensaje que se ajusta al esquema de origen del mapa de la instancia de un nativo existente.</span><span class="sxs-lookup"><span data-stu-id="a99c6-110">In the **Select Input File** dialog box, select an existing native instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="a99c6-111">Como alternativa, puede escribir la ruta de acceso del archivo nativo directamente en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="a99c6-111">Alternatively, you can type the path of this native file directly into the value field of the **TestMap Input Instance** property.</span></span>