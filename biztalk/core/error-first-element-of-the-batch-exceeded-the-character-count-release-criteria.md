---
title: El primer elemento del lote excedía el conjunto de criterios de versión de recuento de caracteres | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4b06f8f-247d-4e93-8c4e-5e86e4ad70c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 746fbfabb2fe411310735f66c6d8a8398a94a5dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241556"
---
# <a name="the-first-element-of-the-batch-exceeded-the-character-count-release-criteria-set"></a><span data-ttu-id="1bb2a-102">El primer elemento del lote excedía el recuento de caracteres, el criterio de publicación establecido</span><span class="sxs-lookup"><span data-stu-id="1bb2a-102">The first element of the batch exceeded the character count release criteria set</span></span>
## <a name="details"></a><span data-ttu-id="1bb2a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1bb2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1bb2a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="1bb2a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1bb2a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="1bb2a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1bb2a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1bb2a-106">Event ID</span></span>|-|  
|<span data-ttu-id="1bb2a-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="1bb2a-107">Event Source</span></span>|<span data-ttu-id="1bb2a-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bb2a-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="1bb2a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="1bb2a-109">Component</span></span>|<span data-ttu-id="1bb2a-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="1bb2a-110">Batching Engine</span></span>|  
|<span data-ttu-id="1bb2a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1bb2a-111">Symbolic Name</span></span>|<span data-ttu-id="1bb2a-112">FirstElementExceededCharCount</span><span class="sxs-lookup"><span data-stu-id="1bb2a-112">FirstElementExceededCharCount</span></span>|  
|<span data-ttu-id="1bb2a-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1bb2a-113">Message Text</span></span>|<span data-ttu-id="1bb2a-114">El primer elemento del lote excedía el recuento de caracteres, el criterio de publicación establecido.</span><span class="sxs-lookup"><span data-stu-id="1bb2a-114">The first element of the batch exceeded the character count release criteria set.</span></span> <span data-ttu-id="1bb2a-115">Modifique los criterios de lanzamiento de recuento de caracteres para poder procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1bb2a-115">Please change the character count release criteria to be able to process this message.</span></span> <span data-ttu-id="1bb2a-116">Una vez modificada la configuración, el mensaje debe enviarse de nuevo al sistema de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="1bb2a-116">The message will need to be resent to the batching system after the settings are modified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1bb2a-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="1bb2a-117">Explanation</span></span>  
 <span data-ttu-id="1bb2a-118">Este evento de error,  indica que la orquestación por lotes no pudo generar el intercambio por lotes porque el número de caracteres del primer elemento de lote seleccionado por la orquestación de lote superó el número de caracteres especificado por la propiedad "Número máximo de caracteres de un intercambio" de los criterios de lanzamiento de lote.</span><span class="sxs-lookup"><span data-stu-id="1bb2a-118">This Error/Warning/Information event indicates that the batching orchestration could not generate the batched interchange because the number of characters in the first batch element picked up by the batching orchestration exceeded the number of characters specified by the "Maximum number of characters in an interchange" property of the batch release criteria.</span></span> <span data-ttu-id="1bb2a-119">Tenga en cuenta que el número de caracteres comparado con el máximo no incluye el número de caracteres del sobre.</span><span class="sxs-lookup"><span data-stu-id="1bb2a-119">Note that the number of characters compared to the maximum does not include the number of characters in the envelope.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1bb2a-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1bb2a-120">User Action</span></span>  
 <span data-ttu-id="1bb2a-121">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1bb2a-121">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="1bb2a-122">Aumente la propiedad "Número máximo de caracteres de un intercambio" de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI para la entidad como receptor de intercambio.</span><span class="sxs-lookup"><span data-stu-id="1bb2a-122">Increase the "Maximum number of characters in an interchange" property in the Interchange Batch Creation Settings Page of the EDI Properties dialog box for the party as interchange receiver.</span></span> <span data-ttu-id="1bb2a-123">Para ello, debe detener la instancia de orquestación, aumentar el número máximo de caracteres en la propiedad y, a continuación, reiniciar la instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="1bb2a-123">To do so, you must stop the orchestration instance, increase the maximum number of characters in the property, and then restart the orchestration instance.</span></span> <span data-ttu-id="1bb2a-124">Pida al remitente que vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1bb2a-124">Have the sender resend the message.</span></span>  
  
2.  <span data-ttu-id="1bb2a-125">Pida al remitente que envíe conjuntos de transacciones con menos caracteres que el número máximo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1bb2a-125">Have the sender send transaction sets that have fewer characters than the maximum number of characters.</span></span>