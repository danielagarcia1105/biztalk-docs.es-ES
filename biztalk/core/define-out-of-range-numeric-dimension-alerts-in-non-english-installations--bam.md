---
title: "Cómo definir alertas fuera de intervalo numérico dimensión en instalaciones que no sean en inglés | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f1e0373-eadf-4c6d-9a38-a34d847f310f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea63008680c026eded843e32a7b2c6ff26dc0bf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-define-out-of-range-numeric-dimension-alerts-in-non-english-installations"></a><span data-ttu-id="a1605-102">Cómo definir alertas de dimensiones numéricas fuera de rango en instalaciones cuyo idioma no sea el inglés</span><span class="sxs-lookup"><span data-stu-id="a1605-102">How to Define Out-of-Range Numeric Dimension Alerts In Non-English Installations</span></span>
<span data-ttu-id="a1605-103">Al establecer alertas que incluyan una condición para un valor que está fuera de la dimensión de rango numérico en instalaciones que no sean en inglés, debe modificar manualmente la definición de BAM con la versión localizada de la cadena **fuera del intervalo**.</span><span class="sxs-lookup"><span data-stu-id="a1605-103">When setting alerts that include a condition for a value that is outside the defined numeric range dimension on non-English installations, you must manually modify the BAM definition with the localized version of the string **out of range**.</span></span>  
  
 <span data-ttu-id="a1605-104">En la siguiente tabla se enumeran ejemplos de valores fuera de rango localizados.</span><span class="sxs-lookup"><span data-stu-id="a1605-104">The following table lists examples of localized out-of-range values.</span></span>  
  
|<span data-ttu-id="a1605-105">Código de lenguaje</span><span class="sxs-lookup"><span data-stu-id="a1605-105">Language code</span></span>|<span data-ttu-id="a1605-106">Cadena localizada</span><span class="sxs-lookup"><span data-stu-id="a1605-106">Localized string</span></span>|  
|-------------------|----------------------|  
|<span data-ttu-id="a1605-107">CN</span><span class="sxs-lookup"><span data-stu-id="a1605-107">CN</span></span>|<span data-ttu-id="a1605-108">超出范围</span><span class="sxs-lookup"><span data-stu-id="a1605-108">超出范围</span></span>|  
|<span data-ttu-id="a1605-109">DE</span><span class="sxs-lookup"><span data-stu-id="a1605-109">DE</span></span>|<span data-ttu-id="a1605-110">Außerhalb des gültigen Bereichs</span><span class="sxs-lookup"><span data-stu-id="a1605-110">Außerhalb des gültigen Bereichs</span></span>|  
|<span data-ttu-id="a1605-111">ES</span><span class="sxs-lookup"><span data-stu-id="a1605-111">ES</span></span>|<span data-ttu-id="a1605-112">Fuera de rango</span><span class="sxs-lookup"><span data-stu-id="a1605-112">Fuera de rango</span></span>|  
|<span data-ttu-id="a1605-113">FR</span><span class="sxs-lookup"><span data-stu-id="a1605-113">FR</span></span>|<span data-ttu-id="a1605-114">hors limites</span><span class="sxs-lookup"><span data-stu-id="a1605-114">hors limites</span></span>|  
|<span data-ttu-id="a1605-115">IT</span><span class="sxs-lookup"><span data-stu-id="a1605-115">IT</span></span>|<span data-ttu-id="a1605-116">Fuori intervallo</span><span class="sxs-lookup"><span data-stu-id="a1605-116">Fuori intervallo</span></span>|  
|<span data-ttu-id="a1605-117">JA</span><span class="sxs-lookup"><span data-stu-id="a1605-117">JA</span></span>|<span data-ttu-id="a1605-118">範囲外</span><span class="sxs-lookup"><span data-stu-id="a1605-118">範囲外</span></span>|  
|<span data-ttu-id="a1605-119">KO</span><span class="sxs-lookup"><span data-stu-id="a1605-119">KO</span></span>|<span data-ttu-id="a1605-120">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="a1605-120">범위를 벗어남</span></span>|  
|<span data-ttu-id="a1605-121">TW</span><span class="sxs-lookup"><span data-stu-id="a1605-121">TW</span></span>|<span data-ttu-id="a1605-122">超過範圍</span><span class="sxs-lookup"><span data-stu-id="a1605-122">超過範圍</span></span>|  
  
### <a name="to-define-out-of-range-alerts-in-non-english-installations"></a><span data-ttu-id="a1605-123">Para definir alertas fuera de rango en instalaciones que no estén en inglés</span><span class="sxs-lookup"><span data-stu-id="a1605-123">To define out-of-range alerts in non-English installations</span></span>  
  
1.  <span data-ttu-id="a1605-124">Desplácese hasta la carpeta que contenga el archivo xml de la definición de BAM.</span><span class="sxs-lookup"><span data-stu-id="a1605-124">Navigate to the folder containing your BAM definition xml file.</span></span>  
  
2.  <span data-ttu-id="a1605-125">Abra el archivo de la definición de BAM mediante un editor de texto o un editor XML.</span><span class="sxs-lookup"><span data-stu-id="a1605-125">Using a text editor or an XML editor, open the BAM definition file.</span></span>  
  
3.  <span data-ttu-id="a1605-126">Localice la dimensión de filtro para la dimensión numérica.</span><span class="sxs-lookup"><span data-stu-id="a1605-126">Locate the slicer dimension for the numeric dimension.</span></span> <span data-ttu-id="a1605-127">Por ejemplo, si la dimensión se denomina **Alerts_NumDim**, debería buscar el siguiente nodo:</span><span class="sxs-lookup"><span data-stu-id="a1605-127">For example, if your slicer dimension is named **Alerts_NumDim**, you would locate the following node:</span></span>  
  
    ```  
    <SlicerDimension Name="Alerts_NumDim">  
    <Level Name="(Out of Range)" />  
    </SlicerDimension>  
    ```  
  
4.  <span data-ttu-id="a1605-128">Cambiar el **fuera del intervalo** valor de cadena a la correspondiente cadena traducida.</span><span class="sxs-lookup"><span data-stu-id="a1605-128">Change the **Out of Range** string value to the appropriate localized string.</span></span>  
  
5.  <span data-ttu-id="a1605-129">Guarde el archivo e implemente la definición.</span><span class="sxs-lookup"><span data-stu-id="a1605-129">Save the file and deploy the definition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1605-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1605-130">See Also</span></span>  
 <span data-ttu-id="a1605-131">[¿Qué es un esquema de definición de BAM?](../core/what-is-a-bam-definition-schema.md) </span><span class="sxs-lookup"><span data-stu-id="a1605-131">[What Is a BAM Definition Schema?](../core/what-is-a-bam-definition-schema.md) </span></span>  
 [<span data-ttu-id="a1605-132">Cómo implementar definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="a1605-132">How to Deploy BAM Definitions</span></span>](../core/how-to-deploy-bam-definitions.md)