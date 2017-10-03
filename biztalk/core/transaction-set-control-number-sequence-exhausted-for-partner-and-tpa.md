---
title: "Conjunto control número secuencia de transacciones agotada para el socio y TPA | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67f194ca-3e0f-4ad4-8bc8-88aa7e5193a7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40d87b1f2681bb07816721971cfbd17d2c3a0b91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-set-control-number-sequence-exhausted-for-partner-and-tpa"></a><span data-ttu-id="f8a24-102">Secuencia de número de control del conjunto de transacciones agotada para el socio y TPA</span><span class="sxs-lookup"><span data-stu-id="f8a24-102">Transaction set control number sequence exhausted for Partner and TPA</span></span>
## <a name="details"></a><span data-ttu-id="f8a24-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f8a24-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f8a24-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f8a24-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f8a24-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f8a24-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f8a24-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f8a24-106">Event ID</span></span>|-|  
|<span data-ttu-id="f8a24-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f8a24-107">Event Source</span></span>|<span data-ttu-id="f8a24-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8a24-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="f8a24-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f8a24-109">Component</span></span>|<span data-ttu-id="f8a24-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="f8a24-110">EDI Engine</span></span>|  
|<span data-ttu-id="f8a24-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f8a24-111">Symbolic Name</span></span>|<span data-ttu-id="f8a24-112">EdiControlNumberExhaustedForParty</span><span class="sxs-lookup"><span data-stu-id="f8a24-112">EdiControlNumberExhaustedForParty</span></span>|  
|<span data-ttu-id="f8a24-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f8a24-113">Message Text</span></span>|<span data-ttu-id="f8a24-114">Secuencia conjunto de transacciones control número agotada para el socio '{1}' del TPA '{2}'.</span><span class="sxs-lookup"><span data-stu-id="f8a24-114">Transaction set control number sequence exhausted for Partner '{1}' for the TPA '{2}'.</span></span> <span data-ttu-id="f8a24-115">Restablezca la secuencia en {2} - propiedades de EDI mediante administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f8a24-115">Reset the sequence in {2} - EDI Properties using BizTalk Server Administration.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f8a24-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="f8a24-116">Explanation</span></span>  
 <span data-ttu-id="f8a24-117">Este evento de Error, advertencia o información indica que BizTalk Server no se pueda procesar que el documento porque el intervalo de control del conjunto de transacciones se ha agotado para el acuerdo en {2}.</span><span class="sxs-lookup"><span data-stu-id="f8a24-117">This Error/Warning/Information event indicates BizTalk Server was not able to process the document because the Transaction set control range has been used up for the agreement in {2}.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f8a24-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f8a24-118">User Action</span></span>  
 <span data-ttu-id="f8a24-119">Para resolver este error, active la casilla de verificación para restablecer el número de control para el acuerdo de {2} o aumentar el intervalo de números de control o pulse el botón Restablecer contra la especificación de intervalo de número de control en el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="f8a24-119">To resolve this error, please tick the checkbox to reset the control number for the {2} agreement or increase the control number range or hit the reset button against the control number range specification in the agreement.</span></span>