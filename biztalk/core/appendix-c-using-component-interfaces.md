---
title: 'Apéndice C: mediante Interfaces de componentes | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enterprise Integration Points
- EIP
- component interfaces
ms.assetid: 2e3bc5ef-24ea-4e09-8e95-31feefaf5536
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c482a01de8f6040f31e6563c97b041dedbe9e88
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230268"
---
# <a name="appendix-c-using-component-interfaces"></a><span data-ttu-id="60539-102">Apéndice C: usar Interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="60539-102">Appendix C: Using Component Interfaces</span></span>
<span data-ttu-id="60539-103">Los temas de esta sección describen cómo crear nuevas interfaces de componente y cómo modificar interfaces de componentes existentes, para su uso con Microsoft BizTalk Adapter para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="60539-103">The topics in this section describe how to create new component interfaces—and how to modify existing component interfaces—for use with Microsoft BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="60539-104">También se describe cómo aplicar seguridad a esas interfaces de componentes y cómo comprobarlas.</span><span class="sxs-lookup"><span data-stu-id="60539-104">They also describe how to apply security to those component interfaces and how to test them.</span></span>  
  
 <span data-ttu-id="60539-105">Puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60539-105">You can do the following:</span></span>  
  
-   <span data-ttu-id="60539-106">Use interfaces de componentes proporcionados por PeopleSoft con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="60539-106">Use component interfaces supplied by PeopleSoft with your application.</span></span>  
  
     <span data-ttu-id="60539-107">Las interfaces de componentes también se conocen como puntos de integración de empresas.</span><span class="sxs-lookup"><span data-stu-id="60539-107">Component interfaces also are known as Enterprise Integration Points (EIP).</span></span>  
  
-   <span data-ttu-id="60539-108">Modifique una interfaz de componentes existente.</span><span class="sxs-lookup"><span data-stu-id="60539-108">Modify an existing component interface.</span></span>  
  
-   <span data-ttu-id="60539-109">Cree una nueva interfaz de componentes.</span><span class="sxs-lookup"><span data-stu-id="60539-109">Create a new component interface.</span></span>  
  
 <span data-ttu-id="60539-110">Antes de usar su interfaz de componentes, debe aplicar y probar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="60539-110">Before using your component interface, you must apply and test security.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60539-111">Esta sección es un suplemento útil, pero no sustituye a la documentación de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="60539-111">This section is intended as a helpful supplement; it is not a substitute for PeopleSoft documentation.</span></span> <span data-ttu-id="60539-112">Para obtener información completa y actualizada sobre las interfaces de componentes de PeopleSoft, vea la biblioteca en línea de PeopleSoft (PeopleSoft Online Library).</span><span class="sxs-lookup"><span data-stu-id="60539-112">For complete and up-to-date information about PeopleSoft component interfaces, see the PeopleSoft Online Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60539-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="60539-113">In This Section</span></span>  
  
-   [<span data-ttu-id="60539-114">Cómo crear Interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="60539-114">How to Create Component Interfaces</span></span>](../core/how-to-create-component-interfaces.md)  
  
-   [<span data-ttu-id="60539-115">Métodos estándar en Interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="60539-115">Standard Methods in Component Interfaces</span></span>](../core/standard-methods-in-component-interfaces.md)  
  
-   [<span data-ttu-id="60539-116">Cómo ayudar a proteger las Interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="60539-116">How to Help Secure Component Interfaces</span></span>](../core/how-to-help-secure-component-interfaces.md)  
  
-   [<span data-ttu-id="60539-117">Cómo probar Interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="60539-117">How to Test Component Interfaces</span></span>](../core/how-to-test-component-interfaces.md)