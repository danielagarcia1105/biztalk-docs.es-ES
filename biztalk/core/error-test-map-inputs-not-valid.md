---
title: 'Error: entrada de comprobar asignación no válida | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.testMapInputsNotValid
ms.assetid: d885d366-92a3-4d2a-8e2b-58e06960864f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 912b70bcd74180a20d54da11dffdab79f54fc5b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---test-map-inputs-not-valid"></a><span data-ttu-id="09868-102">Error: entrada de comprobar asignación no válida</span><span class="sxs-lookup"><span data-stu-id="09868-102">Error - Test Map Inputs Not Valid</span></span>
<span data-ttu-id="09868-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="09868-103">**Error Code**</span></span>  
  
 <span data-ttu-id="09868-104">btm1036</span><span class="sxs-lookup"><span data-stu-id="09868-104">btm1036</span></span>  
  
 <span data-ttu-id="09868-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="09868-105">**Explanation**</span></span>  
  
 <span data-ttu-id="09868-106">No se ha especificado ningún archivo de mensaje de instancia de entrada para la operación Comprobar asignación y el tipo de la entrada de comprobar asignación no está establecido en **generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="09868-106">No input instance message file has been specified for the Test Map operation, and the type of the TestMap input is not set to **Generate Instance**.</span></span> <span data-ttu-id="09868-107">Cuando el valor de la **entrada de comprobar asignación** asignar la propiedad no está establecida en **generar instancia**, debe especificar un archivo de mensaje de instancia para la **instancia de entrada de comprobar asignación** mapa propiedad.</span><span class="sxs-lookup"><span data-stu-id="09868-107">When the value of the **TestMap Input** map property is not set to **Generate Instance**, you must specify an instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="09868-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="09868-108">**User Action**</span></span>  
  
 <span data-ttu-id="09868-109">Según resulte necesario, establezca una u otra de las propiedades de asignación siguientes:</span><span class="sxs-lookup"><span data-stu-id="09868-109">As appropriate, set one or the other of the following map properties:</span></span>  
  
-   <span data-ttu-id="09868-110">**Instancia de entrada de comprobar asignación.**</span><span class="sxs-lookup"><span data-stu-id="09868-110">**TestMap Input Instance.**</span></span> <span data-ttu-id="09868-111">Haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña en el **páginas de propiedades** cuadro de diálogo para la asignación, haga clic en los puntos suspensivos () **...** ) botón en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="09868-111">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="09868-112">Mediante el **Seleccionar archivo de entrada** cuadro de diálogo, seleccione una instancia de archivo que se ajuste al esquema de origen del mapa de mensajes.</span><span class="sxs-lookup"><span data-stu-id="09868-112">Using the **Select Input File** dialog box, select an instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="09868-113">Como alternativa, puede escribir la ruta de acceso de este archivo directamente en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="09868-113">Alternatively, you can type the path of this file directly into the value field of the **TestMap Input Instance** property.</span></span>  
  
-   <span data-ttu-id="09868-114">**Entrada de comprobar asignación.**</span><span class="sxs-lookup"><span data-stu-id="09868-114">**TestMap Input.**</span></span> <span data-ttu-id="09868-115">Para evitar especificar un archivo de mensaje de instancia de entrada, haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña en el **páginas de propiedades**cuadro de diálogo para la asignación, use la lista desplegable lista en el campo de valor de la **entrada de comprobar asignación** propiedad para seleccionar **generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="09868-115">To avoid specifying an input instance message file, right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, use the drop-down list in the value field of the **TestMap Input** property to select **Generate Instance**.</span></span> <span data-ttu-id="09868-116">En este caso, no necesitan especificar un archivo para el **instancia de entrada de comprobar asignación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="09868-116">In this case, you need not specify a file for the **TestMap Input Instance** property.</span></span>