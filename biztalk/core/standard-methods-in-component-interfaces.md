---
title: Métodos estándar en Interfaces de componentes | Microsoft Docs
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
ms.openlocfilehash: eecb56f262a56e6567b44b146c631542cb1ceda6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994829"
---
# <a name="standard-methods-in-component-interfaces"></a><span data-ttu-id="adc4a-102">Métodos estándar en Interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="adc4a-102">Standard Methods in Component Interfaces</span></span>
<span data-ttu-id="adc4a-103">Los métodos estándar para la interfaz de componente son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="adc4a-103">The standard methods for the component interface are as follows:</span></span>  
  
- `Create`  
  
- `Find`  
  
- `Get`  
  
- `Save`  
  
  <span data-ttu-id="adc4a-104">Solo esos métodos del componente subyacente están disponibles.</span><span class="sxs-lookup"><span data-stu-id="adc4a-104">Only those methods in the underlying component are available.</span></span> <span data-ttu-id="adc4a-105">Por ejemplo, si el componente subyacente no contiene capacidades `Add`, `Create` no está disponible.</span><span class="sxs-lookup"><span data-stu-id="adc4a-105">For example, if the underlying component does not contain `Add` capabilities, `Create` is unavailable.</span></span>  
  
## <a name="viewing-or-changing-available-methods"></a><span data-ttu-id="adc4a-106">Ver o cambiar los métodos disponibles</span><span class="sxs-lookup"><span data-stu-id="adc4a-106">Viewing or Changing Available Methods</span></span>  
  
#### <a name="to-view-or-change-available-methods"></a><span data-ttu-id="adc4a-107">Para ver o cambiar los métodos disponibles</span><span class="sxs-lookup"><span data-stu-id="adc4a-107">To view or change available methods</span></span>  
  
1.  <span data-ttu-id="adc4a-108">Abra la interfaz de componente **propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="adc4a-108">Open the component interface **Properties** dialog box.</span></span>  
  
     <span data-ttu-id="adc4a-109">![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")</span><span class="sxs-lookup"><span data-stu-id="adc4a-109">![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")</span></span>  
  
2.  <span data-ttu-id="adc4a-110">Haga clic en el **métodos estándar** ficha.</span><span class="sxs-lookup"><span data-stu-id="adc4a-110">Click the **Standard Methods** tab.</span></span>  
  
3.  <span data-ttu-id="adc4a-111">Seleccione los métodos deseados y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="adc4a-111">Select the desired methods, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc4a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="adc4a-112">See Also</span></span>  
 <span data-ttu-id="adc4a-113">[Cómo crear Interfaces de componentes](../core/how-to-create-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="adc4a-113">[How to Create Component Interfaces](../core/how-to-create-component-interfaces.md) </span></span>  
 [<span data-ttu-id="adc4a-114">Apéndice C: Uso de interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="adc4a-114">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)