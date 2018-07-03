---
title: Se encontró el número de control duplicados de conjunto de transacciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b2779a0-b365-4c4b-81c7-8f9284748b6e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6b9b55dc5cd61bc4c8c806f2dc42259cadf2f69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977712"
---
# <a name="transaction-set-duplicate-control-number-found"></a><span data-ttu-id="26755-102">Se ha encontrado un número de control de conjunto de transacciones duplicado</span><span class="sxs-lookup"><span data-stu-id="26755-102">Transaction Set duplicate control number found</span></span>
## <a name="details"></a><span data-ttu-id="26755-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="26755-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="26755-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="26755-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="26755-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="26755-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="26755-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="26755-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="26755-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="26755-107">Event Source</span></span>   | <span data-ttu-id="26755-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26755-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="26755-109">Componente</span><span class="sxs-lookup"><span data-stu-id="26755-109">Component</span></span>    |                                       <span data-ttu-id="26755-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="26755-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="26755-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="26755-111">Symbolic Name</span></span>  |                          <span data-ttu-id="26755-112">X12TsDuplicateNumberFoundDescription</span><span class="sxs-lookup"><span data-stu-id="26755-112">X12TsDuplicateNumberFoundDescription</span></span>                          |
|  <span data-ttu-id="26755-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="26755-113">Message Text</span></span>   |                     <span data-ttu-id="26755-114">Se ha encontrado un número de control de conjunto de transacciones duplicado</span><span class="sxs-lookup"><span data-stu-id="26755-114">Transaction Set duplicate control number found</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="26755-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="26755-115">Explanation</span></span>  
 <span data-ttu-id="26755-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante porque el número de control del conjunto de transacciones para un conjunto de transacciones de un grupo de dicho intercambio era el mismo que el número de control para otro conjunto de transacciones de dicho grupo.</span><span class="sxs-lookup"><span data-stu-id="26755-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the transaction set control number for a transaction set in a group of that interchange was the same as the control number for another transaction set in that group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="26755-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="26755-117">User Action</span></span>  
 <span data-ttu-id="26755-118">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="26755-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="26755-119">Cambie los números de control de conjunto de transacciones de los conjuntos de transacciones en el intercambio de entrada de modo que no haya números de control duplicados para los conjuntos de transacciones de un grupo.</span><span class="sxs-lookup"><span data-stu-id="26755-119">Change the transaction set control numbers of transaction sets in incoming interchange so there are no duplicate control numbers for transaction sets in a group.</span></span>  
  
-   <span data-ttu-id="26755-120">Deshabilite la comprobación de números de control duplicados para conjuntos de transacciones según se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="26755-120">Disable the check for duplicate transaction set control numbers as follows:</span></span>  
  
    1.  <span data-ttu-id="26755-121">Abra la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="26755-121">Open the BizTalk Server Administration Console.</span></span>  
  
    2.  <span data-ttu-id="26755-122">Abra el cuadro de diálogo Propiedades de EDI correspondiente a la entidad que envió el intercambio.</span><span class="sxs-lookup"><span data-stu-id="26755-122">Open the EDI Properties dialog box for the party that sent the interchange.</span></span>  
  
    3.  <span data-ttu-id="26755-123">Para intercambios X12, desactive "Comprobar si hay duplicado de Número de control de conjunto de transacciones (ST2) en el grupo" en la página Propiedades de procesamiento de intercambio X12 del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="26755-123">For X12 interchanges, clear the "Check for duplicate ST2 (Transaction set control number) in group" in the X12 Interchange Processing Properties Page of the EDI Properties dialog box.</span></span>  
  
    4.  <span data-ttu-id="26755-124">Para intercambios EDIFACT, desactive "Comprobar si hay duplicado de Número de control de conjunto de transacciones (UNH1) en el grupo" en la página Propiedades de procesamiento de intercambio EDIFACT del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="26755-124">For EDIFACT interchanges, clear the "Check for duplicate UNH1 (Transaction set reference number) in group" property in the EDIFACT Interchange Processing Properties Page of the EDI Properties dialog box.</span></span>