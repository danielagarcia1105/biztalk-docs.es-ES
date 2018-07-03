---
title: El elemento por lotes ha excedido el recuento de caracteres máximo configurado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ad12733-295a-43ba-8147-34c8716c2d37
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 689ba342affa3ed4f246e9aa963f8ea4e22704af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992421"
---
# <a name="the-batch-element-exceeded-the-maximum-configured-character-count"></a><span data-ttu-id="61ad0-102">El elemento por lotes ha excedido el recuento de caracteres máximo configurado.</span><span class="sxs-lookup"><span data-stu-id="61ad0-102">The batch element exceeded the maximum configured character count</span></span>
## <a name="details"></a><span data-ttu-id="61ad0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="61ad0-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="61ad0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="61ad0-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="61ad0-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="61ad0-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="61ad0-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="61ad0-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="61ad0-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="61ad0-107">Event Source</span></span>   | <span data-ttu-id="61ad0-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61ad0-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="61ad0-109">Componente</span><span class="sxs-lookup"><span data-stu-id="61ad0-109">Component</span></span>    |                                    <span data-ttu-id="61ad0-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="61ad0-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="61ad0-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="61ad0-111">Symbolic Name</span></span>  |                             <span data-ttu-id="61ad0-112">MessageExceededCharacterCount</span><span class="sxs-lookup"><span data-stu-id="61ad0-112">MessageExceededCharacterCount</span></span>                              |
|  <span data-ttu-id="61ad0-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="61ad0-113">Message Text</span></span>   |           <span data-ttu-id="61ad0-114">El elemento por lotes ha excedido el recuento de caracteres máximo configurado.</span><span class="sxs-lookup"><span data-stu-id="61ad0-114">The batch element exceeded the maximum configured character count</span></span>            |
  
## <a name="explanation"></a><span data-ttu-id="61ad0-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="61ad0-115">Explanation</span></span>  
 <span data-ttu-id="61ad0-116">Este evento de error,  indica que la orquestación por lotes no pudo generar el intercambio por lotes porque el número de caracteres de un elemento de lote seleccionado por la orquestación de lote supera el número de caracteres especificado por la propiedad "Número máximo de caracteres de un intercambio" de los criterios de lanzamiento de lote.</span><span class="sxs-lookup"><span data-stu-id="61ad0-116">This Error/Warning/Information event indicates that the batching orchestration could not generate the batched interchange because the number of characters in a batch element picked up by the batching orchestration exceeds the number of characters specified by the "Maximum number of characters in an interchange" property of the batch release criteria.</span></span> <span data-ttu-id="61ad0-117">El elemento de lote que genera este mensaje de error no será el primero seleccionado para un lote, sino uno después del primer elemento que ya se haya procesado por lotes.</span><span class="sxs-lookup"><span data-stu-id="61ad0-117">The batch element that generates this error message will not be the first batch element picked up for a batch, but a batch element after the first element has already been batched.</span></span> <span data-ttu-id="61ad0-118">Tenga en cuenta que el número de caracteres comparado con el máximo no incluye el número de caracteres del sobre.</span><span class="sxs-lookup"><span data-stu-id="61ad0-118">Note that the number of characters compared to the maximum does not include the number of characters in the envelope.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="61ad0-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="61ad0-119">User Action</span></span>  
 <span data-ttu-id="61ad0-120">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="61ad0-120">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="61ad0-121">Aumente la propiedad "Número máximo de caracteres de un intercambio" de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI para la entidad como receptor de intercambio.</span><span class="sxs-lookup"><span data-stu-id="61ad0-121">Increase the "Maximum number of characters in an interchange" property in the Interchange Batch Creation Settings Page of the EDI Properties dialog box for the party as interchange receiver.</span></span> <span data-ttu-id="61ad0-122">Para ello, debe detener la instancia de orquestación, aumentar el número máximo de caracteres en la propiedad y, a continuación, reiniciar la instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="61ad0-122">To do so, you must stop the orchestration instance, increase the maximum number of characters in the property, and then restart the orchestration instance.</span></span>  
  
2.  <span data-ttu-id="61ad0-123">Pida al remitente que envíe conjuntos de transacciones con menos caracteres que el número máximo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="61ad0-123">Have the sender send transaction sets that have fewer characters than the maximum number of characters.</span></span>