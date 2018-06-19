---
title: Métodos estándar en Interfaces de componentes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, standard methods
- methods, viewing
- methods, component interfaces
- methods, changing
ms.assetid: 2273d946-3fc8-4b2d-a6a1-9e4f0da74d5b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f44b3977a3921d92b1f3f83dd3e744f14b5709fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278052"
---
# <a name="standard-methods-in-component-interfaces"></a><span data-ttu-id="f3368-102">Métodos estándar en Interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="f3368-102">Standard Methods in Component Interfaces</span></span>
<span data-ttu-id="f3368-103">Los métodos estándar para la interfaz de componente son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3368-103">The standard methods for the component interface are as follows:</span></span>  
  
-   `Create`  
  
-   `Find`  
  
-   `Get`  
  
-   `Save`  
  
 <span data-ttu-id="f3368-104">Solo esos métodos del componente subyacente están disponibles.</span><span class="sxs-lookup"><span data-stu-id="f3368-104">Only those methods in the underlying component are available.</span></span> <span data-ttu-id="f3368-105">Por ejemplo, si el componente subyacente no contiene capacidades `Add`, `Create` no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f3368-105">For example, if the underlying component does not contain `Add` capabilities, `Create` is unavailable.</span></span>  
  
## <a name="viewing-or-changing-available-methods"></a><span data-ttu-id="f3368-106">Ver o cambiar los métodos disponibles</span><span class="sxs-lookup"><span data-stu-id="f3368-106">Viewing or Changing Available Methods</span></span>  
  
#### <a name="to-view-or-change-available-methods"></a><span data-ttu-id="f3368-107">Para ver o cambiar los métodos disponibles</span><span class="sxs-lookup"><span data-stu-id="f3368-107">To view or change available methods</span></span>  
  
1.  <span data-ttu-id="f3368-108">Abra la interfaz de componentes **propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f3368-108">Open the component interface **Properties** dialog box.</span></span>  
  
     ![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")  
  
2.  <span data-ttu-id="f3368-109">Haga clic en el **métodos estándar** ficha.</span><span class="sxs-lookup"><span data-stu-id="f3368-109">Click the **Standard Methods** tab.</span></span>  
  
3.  <span data-ttu-id="f3368-110">Seleccione los métodos deseados y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f3368-110">Select the desired methods, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3368-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3368-111">See Also</span></span>  
 <span data-ttu-id="f3368-112">[Cómo crear Interfaces de componentes](../core/how-to-create-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="f3368-112">[How to Create Component Interfaces](../core/how-to-create-component-interfaces.md) </span></span>  
 [<span data-ttu-id="f3368-113">Apéndice C: usar Interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="f3368-113">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)