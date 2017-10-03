---
title: 'Error: no existe el archivo de entrada | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.inputFileDoesNotExist
ms.assetid: 6cd2f076-6c3e-46e3-8be4-dad2d9b95d37
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a14221857ebb567020a52c2ff0939b506d28937
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---input-file-does-not-exist"></a><span data-ttu-id="a6e81-102">Error: no existe el archivo de entrada</span><span class="sxs-lookup"><span data-stu-id="a6e81-102">Error - Input File Does Not Exist</span></span>
<span data-ttu-id="a6e81-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="a6e81-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a6e81-104">btm1037</span><span class="sxs-lookup"><span data-stu-id="a6e81-104">btm1037</span></span>  
  
 <span data-ttu-id="a6e81-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="a6e81-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a6e81-106">El archivo de mensaje de instancia de entrada especificado para la operación Comprobar asignación no existe y el tipo de la entrada de comprobar asignación no se establece en **generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="a6e81-106">The input instance message file specified for the Test Map operation does not exist, and the type of the Test Map input is not set to **Generate Instance**.</span></span> <span data-ttu-id="a6e81-107">Cuando el valor de la **entrada de comprobar asignación** asignar la propiedad no está establecida en **generar instancia**, debe especificar un archivo de mensaje de instancia existente para la **instancia de entrada de comprobar asignación** asignar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a6e81-107">When the value of the **TestMap Input** map property is not set to **Generate Instance**, you must specify an existing instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="a6e81-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="a6e81-108">**User Action**</span></span>  
  
 <span data-ttu-id="a6e81-109">Según resulte necesario, establezca una u otra de las propiedades de asignación siguientes:</span><span class="sxs-lookup"><span data-stu-id="a6e81-109">As appropriate, set one or the other of the following map properties:</span></span>  
  
-   <span data-ttu-id="a6e81-110">**Instancia de entrada de comprobar asignación.**</span><span class="sxs-lookup"><span data-stu-id="a6e81-110">**TestMap Input Instance.**</span></span> <span data-ttu-id="a6e81-111">Haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña en el **páginas de propiedades** cuadro de diálogo para la asignación, haga clic en los puntos suspensivos () **...** ) botón en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="a6e81-111">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="a6e81-112">Mediante el **Seleccionar archivo de entrada** cuadro de diálogo, seleccione el archivo que se ajusta al esquema de origen del mapa de mensajes de una instancia existente.</span><span class="sxs-lookup"><span data-stu-id="a6e81-112">Using the **Select Input File** dialog box, select an existing instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="a6e81-113">Como alternativa, puede escribir la ruta de acceso de este archivo directamente en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="a6e81-113">Alternatively, you can type the path of this file directly into the value field of the **TestMap Input Instance** property.</span></span>  
  
-   <span data-ttu-id="a6e81-114">**Entrada de comprobar asignación.**</span><span class="sxs-lookup"><span data-stu-id="a6e81-114">**TestMap Input.**</span></span> <span data-ttu-id="a6e81-115">Para evitar especificar un archivo de mensaje de instancia de entrada, haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña de la **páginas de propiedades**cuadro de diálogo para la asignación, use la lista desplegable lista en el campo de valor de la **entrada de comprobar asignación** propiedad para seleccionar **generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="a6e81-115">To avoid specifying an input instance message file, right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab of the **Property Pages** dialog box for the map, use the drop-down list in the value field of the **TestMap Input** property to select **Generate Instance**.</span></span> <span data-ttu-id="a6e81-116">En este caso, no necesitan especificar un archivo para el **instancia de entrada de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="a6e81-116">In this case, you need not specify a file for the **TestMap Input Instance** property.</span></span>