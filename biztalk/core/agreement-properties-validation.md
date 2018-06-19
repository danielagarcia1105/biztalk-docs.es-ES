---
title: Validación de propiedades de acuerdo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d565c26-37ef-4aee-aebb-3152880242a1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20c01ec281005cbeaffda6dcd2349c1153a531b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229876"
---
# <a name="agreement-properties-validation"></a><span data-ttu-id="07621-102">Validación de las propiedades del acuerdo</span><span class="sxs-lookup"><span data-stu-id="07621-102">Agreement Properties Validation</span></span>
<span data-ttu-id="07621-103">Las propiedades de acuerdo incluyen comprobaciones de números de control duplicados en intercambios, grupos o conjuntos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="07621-103">Agreement properties include checks for duplicate control numbers for interchanges, groups, or transaction sets.</span></span> <span data-ttu-id="07621-104">La canalización de recepción de EDI llevará a cabo estas validaciones únicamente si están habilitadas en las propiedades del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="07621-104">The EDI receive pipeline will perform these validations only if they are enabled in agreement properties.</span></span> <span data-ttu-id="07621-105">Estas validaciones incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="07621-105">These validations include:</span></span>  
  
-   <span data-ttu-id="07621-106">Comprobar si existe un número de control de intercambio duplicado (ISA13 en X12 o UNB5 en EDIFACT).</span><span class="sxs-lookup"><span data-stu-id="07621-106">Checking for a duplicate interchange control number (ISA13 in X12 or UNB5 in EDIFACT).</span></span> <span data-ttu-id="07621-107">Especifique un valor de tiempo (en días) para establecer el intervalo de tiempo válido para esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="07621-107">You enter a time value (in days) to establish the valid time range for this check.</span></span>  
  
-   <span data-ttu-id="07621-108">Comprobar si existe un número de control de grupo duplicado en un intercambio (GS6 en X12 o UNG5 en EDIFACT).</span><span class="sxs-lookup"><span data-stu-id="07621-108">Checking for a duplicate group control number in an interchange (GS6 in X12 or UNG5 in EDIFACT)</span></span>  
  
-   <span data-ttu-id="07621-109">Comprobar si existe un número de control del conjunto de transacciones duplicado en un grupo funcional (ST2 en X12 o UNH1 en EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="07621-109">Checking for a duplicate transaction set control number in a functional group (ST2 in X12 or UNH1 in EDIFACT)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07621-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="07621-110">See Also</span></span>  
 [<span data-ttu-id="07621-111">Validación del mensaje EDI</span><span class="sxs-lookup"><span data-stu-id="07621-111">EDI Message Validation</span></span>](../core/edi-message-validation.md)