---
title: 'Error: error de coincidencia de entrada fija de Functoid | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.functoidFixedInputMismatch
ms.assetid: d235e7c3-efcf-4128-aef7-cdfdf1f317be
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8de4020105f357905e510be1694c0cf95a4af6c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="error---functoid-fixed-input-mismatch"></a><span data-ttu-id="d552b-102">Error: error de coincidencia de entrada fija de Functoid</span><span class="sxs-lookup"><span data-stu-id="d552b-102">Error - Functoid Fixed Input Mismatch</span></span>
<span data-ttu-id="d552b-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="d552b-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d552b-104">btm1010</span><span class="sxs-lookup"><span data-stu-id="d552b-104">btm1010</span></span>  
  
 <span data-ttu-id="d552b-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="d552b-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d552b-106">El functoid indicado no tiene el número correcto de parámetros de entrada especificados.</span><span class="sxs-lookup"><span data-stu-id="d552b-106">The indicated functoid does not have the correct number of input parameters specified.</span></span> <span data-ttu-id="d552b-107">El número de parámetros de entrada debe ser exactamente el especificado.</span><span class="sxs-lookup"><span data-stu-id="d552b-107">The number of input parameters must be exactly as specified.</span></span>  
  
 <span data-ttu-id="d552b-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="d552b-108">**User Action**</span></span>  
  
 <span data-ttu-id="d552b-109">Utilice uno o más de los siguientes métodos para proporcionar el número indicado de parámetros de entrada al functoid indicado y preste especial atención al orden de parámetros de entrada esperado:</span><span class="sxs-lookup"><span data-stu-id="d552b-109">Use one or more of the following methods to provide the indicated number of input parameters to the indicated functoid, paying particular attention to the expected order of input parameters:</span></span>  
  
-   <span data-ttu-id="d552b-110">Para crear vínculos adicionales, arrastre para crear vínculos entre el functoid indicado y los nodos del esquema de origen o la salida de otros functoids situados a la izquierda del functoid indicado en una página de cuadrícula de asignación.</span><span class="sxs-lookup"><span data-stu-id="d552b-110">To create additional links, drag to create links between the indicated functoid and either nodes in the source schema or the output of other functoids that are located to the left of the indicated functoid in a map grid page.</span></span>  
  
-   <span data-ttu-id="d552b-111">Para crear vínculos adicionales, seleccione el functoid indicado, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **parámetros de entrada** propiedad en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, a continuación, configure y reorganice el orden de los parámetros de entrada en el **configurar \<Functoid\> Functoid** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d552b-111">To create additional links, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then configure and rearrange the order of the input parameters in the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="d552b-112">Se pueden crear parámetros de entrada, dados los valores, y se pueden poner en el orden correcto en relación con otros parámetros de entrada de este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d552b-112">Constant input parameters can be created, given values, and put in the proper order relative to the other input parameters in this dialog box.</span></span>  
  
-   <span data-ttu-id="d552b-113">Para eliminar vínculos existentes, para cada vínculo conectado al lado izquierdo del functoid indicado, haga clic en el vínculo y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d552b-113">To remove existing links, for each link connected to the left side of the indicated functoid, right-click the link and then click **Delete**.</span></span>  
  
-   <span data-ttu-id="d552b-114">Para eliminar vínculos existentes, seleccione el functoid indicado, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **parámetros de entrada** propiedad en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, a continuación, en la **configurar \<Functoid\> Functoid**cuadro de diálogo, elimine todos los parámetros de entrada seleccionando y haciendo clic en el ![ ] (../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") botón para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="d552b-114">To remove existing links, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, delete all input parameters by selecting and clicking the ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") button for each of them.</span></span> <span data-ttu-id="d552b-115">Utilice este método para eliminar parámetros de entrada constantes.</span><span class="sxs-lookup"><span data-stu-id="d552b-115">You must use this method to delete constant input parameters.</span></span>