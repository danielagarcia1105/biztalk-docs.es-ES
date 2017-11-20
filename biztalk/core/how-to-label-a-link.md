---
title: "Cómo etiquetar un vínculo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fb81763-8b50-4334-88a8-efad1c5d82d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0e47a776fdbc8eccbc1037b3c73b069d810eee0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-label-a-link"></a><span data-ttu-id="f320e-102">Creación de etiqueta para un vínculo</span><span class="sxs-lookup"><span data-stu-id="f320e-102">How to Label a Link</span></span>
<span data-ttu-id="f320e-103">Las etiquetas resultan útiles para documentar la finalidad de un functoid o vínculo en una asignación.</span><span class="sxs-lookup"><span data-stu-id="f320e-103">Labels are helpful to document the purpose of a functoid or a link in a map.</span></span> <span data-ttu-id="f320e-104">Puede usar el **etiqueta** propiedad para el nombre de un vínculo.</span><span class="sxs-lookup"><span data-stu-id="f320e-104">You can use the **Label** property to name a link.</span></span> <span data-ttu-id="f320e-105">Esto resulta útil si la asignación contiene estructuras de esquemas grandes y la identificación de los vínculos de entradas y salidas a un functoid resulta complicada.</span><span class="sxs-lookup"><span data-stu-id="f320e-105">This is useful when your map contains big schema structures and identifying the inputs and output links to a functoid becomes difficult.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f320e-106">Para obtener información sobre cómo etiquetar y comentar functoids, consulte [cómo etiquetar y comentar un Functoid](../core/how-to-label-and-comment-a-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="f320e-106">For information on how to label and comment functoids, see [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
 <span data-ttu-id="f320e-107">La figura siguiente muestra una etiqueta de vínculo.</span><span class="sxs-lookup"><span data-stu-id="f320e-107">The following figure shows a link label.</span></span>  
  
 <span data-ttu-id="f320e-108">![Etiquetado de un vínculo](../core/media/new-labelling-link.gif "New_Labelling_link")</span><span class="sxs-lookup"><span data-stu-id="f320e-108">![Labelling a link](../core/media/new-labelling-link.gif "New_Labelling_link")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f320e-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f320e-109">Prerequisites</span></span>  
 <span data-ttu-id="f320e-110">Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f320e-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-add-a-label-to-a-link"></a><span data-ttu-id="f320e-111">Procedimiento para agregar una etiqueta a un vínculo</span><span class="sxs-lookup"><span data-stu-id="f320e-111">To add a label to a link</span></span>  
  
1.  <span data-ttu-id="f320e-112">Seleccione el vínculo que desea etiquetar.</span><span class="sxs-lookup"><span data-stu-id="f320e-112">Select the link you want to label.</span></span>  
  
2.  <span data-ttu-id="f320e-113">En el **propiedades** ventana, especifique el nuevo nombre en el **etiqueta** campo.</span><span class="sxs-lookup"><span data-stu-id="f320e-113">In the **Properties** window, provide the new name in the **Label** field.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f320e-114">El número máximo de caracteres permitido es 256.</span><span class="sxs-lookup"><span data-stu-id="f320e-114">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="f320e-115">Si se especifica una cadena con más de 256 caracteres, se aceptan los primeros 256 caracteres y el resto se descartan.</span><span class="sxs-lookup"><span data-stu-id="f320e-115">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
     <span data-ttu-id="f320e-116">![Propiedades de la etiqueta de vínculo](../core/media/new-to-label-link.gif "New_To_Label_Link")</span><span class="sxs-lookup"><span data-stu-id="f320e-116">![Link label properties](../core/media/new-to-label-link.gif "New_To_Label_Link")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f320e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f320e-117">See Also</span></span>  
 [<span data-ttu-id="f320e-118">Utilizar vínculos para especificar el registro y las asignaciones de campos</span><span class="sxs-lookup"><span data-stu-id="f320e-118">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)