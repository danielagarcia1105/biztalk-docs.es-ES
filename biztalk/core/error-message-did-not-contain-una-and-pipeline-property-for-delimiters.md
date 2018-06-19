---
title: Mensaje no contenía UNA y propiedad de canalización para delimitadores tenía el formato correcto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b761d820-e09d-4949-bb41-da9e66054c60
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6310c96f897126a498772f2147a20c84f7e926a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241844"
---
# <a name="message-did-not-contain-una-and-pipeline-property-for-delimiters-was-incorrect-format"></a><span data-ttu-id="2915a-102">El mensaje no contenía UNA, y la propiedad de canalización para delimitadores no tenía el formato correcto</span><span class="sxs-lookup"><span data-stu-id="2915a-102">Message did not contain UNA and pipeline property for delimiters was incorrect format</span></span>
## <a name="details"></a><span data-ttu-id="2915a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2915a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2915a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2915a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2915a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2915a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2915a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2915a-106">Event ID</span></span>|-|  
|<span data-ttu-id="2915a-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2915a-107">Event Source</span></span>|<span data-ttu-id="2915a-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2915a-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="2915a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="2915a-109">Component</span></span>|<span data-ttu-id="2915a-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="2915a-110">EDI Engine</span></span>|  
|<span data-ttu-id="2915a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2915a-111">Symbolic Name</span></span>|<span data-ttu-id="2915a-112">EfactDelimiterIncorrectFormat</span><span class="sxs-lookup"><span data-stu-id="2915a-112">EfactDelimiterIncorrectFormat</span></span>|  
|<span data-ttu-id="2915a-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2915a-113">Message Text</span></span>|<span data-ttu-id="2915a-114">El mensaje no contenía UNA, y la propiedad de canalización para delimitadores no tenía el formato correcto '{0}'.</span><span class="sxs-lookup"><span data-stu-id="2915a-114">Message did not contain UNA and pipeline property for delimiters was incorrect format '{0}'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2915a-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="2915a-115">Explanation</span></span>  
 <span data-ttu-id="2915a-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio EDIFACT entrante porque no pudo determinar los separadores requeridos para procesar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="2915a-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange because it could not determine the separators required to process the interchange.</span></span> <span data-ttu-id="2915a-117">Esto puede suceder si el intercambio no tiene un segmento UNA y la propiedad de la canalización EfactDelimiters no define de forma adecuada los separadores.</span><span class="sxs-lookup"><span data-stu-id="2915a-117">This can occur if the interchange does not have a UNA segment and the EfactDelimiters pipeline property does not adequately define the separators.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2915a-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2915a-118">User Action</span></span>  
 <span data-ttu-id="2915a-119">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2915a-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="2915a-120">Asegúrese de que el intercambio tenga un segmento UNA que defina los separadores para el intercambio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="2915a-120">Make sure that the interchange has a UNA segment that defines the separators for the interchange, and then resend the interchange.</span></span>  
  
2.  <span data-ttu-id="2915a-121">Configure la propiedad de la canalización EfactDelimiters para la canalización de envío. Para ello, abra la consola de administración de BizTalk Server, haga clic con el botón secundario en la ubicación de recepción que va a recibir el intercambio, haga clic en Propiedades y en los puntos suspensivos de la canalización y, a continuación, especifique una cadena que contenga los valores de los separadores.</span><span class="sxs-lookup"><span data-stu-id="2915a-121">Set the EfactDelimiters pipeline property for the send pipeline by opening the BizTalk Server Administration Console, right-clicking the receive location that will be receiving the interchange, clicking Properties, clicking the ellipsis for the pipeline, and then entering a string containing the values of the separators.</span></span>