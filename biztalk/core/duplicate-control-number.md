---
title: Número de Control duplicado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 331ad173-29b3-427c-8104-60d80c580a5a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcfd1a10b836ec593b6aa94a87d8145d6e2ebaaf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967893"
---
# <a name="duplicate-control-number"></a><span data-ttu-id="c7c6e-102">Número de control duplicado.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-102">Duplicate Control Number</span></span>
## <a name="details"></a><span data-ttu-id="c7c6e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c7c6e-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c7c6e-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c7c6e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c7c6e-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c7c6e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c7c6e-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c7c6e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c7c6e-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c7c6e-107">Event Source</span></span>   | <span data-ttu-id="c7c6e-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7c6e-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="c7c6e-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c7c6e-109">Component</span></span>    |                                       <span data-ttu-id="c7c6e-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c7c6e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c7c6e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c7c6e-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="c7c6e-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c7c6e-112">Message Text</span></span>   |                                <span data-ttu-id="c7c6e-113">Número de control duplicado.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-113">Duplicate Control Number</span></span>                                |

## <a name="explanation"></a><span data-ttu-id="c7c6e-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="c7c6e-114">Explanation</span></span>  
 <span data-ttu-id="c7c6e-115">Este evento de error,  indica que la canalización de recepción EDI no pudo procesar un intercambio entrante porque tenía el mismo número de control de intercambio, grupo o conjunto de transacciones que un intercambio recibido previamente.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming interchange because it had the same interchange, group, or transaction set control number as a previously received interchange.</span></span> <span data-ttu-id="c7c6e-116">Esto provocará un error siempre que estén habilitadas las correspondientes comprobaciones de números de control duplicados.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-116">This will result in a failure as long as the appropriate duplicate control number checks are enabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c7c6e-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c7c6e-117">User Action</span></span>  
 <span data-ttu-id="c7c6e-118">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c7c6e-118">To resolve this error, do one of the following:</span></span>  

- <span data-ttu-id="c7c6e-119">Asegúrese de que el intercambio enviado a BizTalk Server no tiene el mismo número de control de intercambio, grupo o conjunto de transacciones que un intercambio previo, si está habilitada la correspondiente comprobación de número de control duplicado.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-119">Ensure that the interchange sent to BizTalk Server does not have the same interchange, group, or transaction set control number as a previous interchange, if the corresponding duplicate control number check is enabled.</span></span>  

- <span data-ttu-id="c7c6e-120">Deshabilitar la comprobación de número de control duplicados.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-120">Disable the duplicate control number check.</span></span> <span data-ttu-id="c7c6e-121">En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], haga clic con el botón secundario en la entidad correspondiente y abra el cuadro de diálogo Propiedades de procesamiento de intercambio EDIFACT o bien Propiedades de procesamiento de intercambio X12 para la entidad como remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-121">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the appropriate party, and open either the EDIFACT Interchange Processing Properties or the X12 Interchange Processing Properties dialog box for the party as an interchange sender.</span></span> <span data-ttu-id="c7c6e-122">Para deshabilitar una comprobación para un intercambio EDIFACT, desactive la propiedad Comprobar si hay duplicado de UNB5 (número de control de intercambio), Comprobar si hay duplicado de Número de control de grupo (UNG5) en el intercambio o Comprobar si hay duplicado de Número de control de conjunto de transacciones (UNH1) en el grupo.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-122">To disable a check for an EDIFACT interchange, clear the Check for duplicate UNB5 (Interchange control number), Check for duplicate UNG5 (Group control number) in interchange, or Check for duplicate UNH1 (Transaction set reference number) in group property.</span></span> <span data-ttu-id="c7c6e-123">Para deshabilitar una comprobación para un intercambio X12, desactive la propiedad Comprobar si hay duplicado de número de control de intercambio (ISA13), Comprobar si hay duplicado de Número de control de grupo (GS6) en el intercambio o Comprobar si hay duplicado de Número de control de conjunto de transacciones (ST2) en el grupo.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-123">To disable a check for an X12 interchange, clear the Check for duplicate ISA13 (Interchange control number), Check for duplicate GS6 (Group control number) in interchange, or Check for duplicate ST2 (Transaction set control number) in group property.</span></span>
