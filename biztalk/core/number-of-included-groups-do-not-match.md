---
title: Número de grupos incluidos no coincide. | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d61ac17-92cd-4a5e-81e6-e2c6fc4085bb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf61012de6ba864d6f0ff4e553b4c74e1d501c20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988173"
---
# <a name="number-of-included-groups-do-not-match"></a><span data-ttu-id="ff344-102">El número de grupos incluidos no coincide</span><span class="sxs-lookup"><span data-stu-id="ff344-102">Number of included groups do not match</span></span>
## <a name="details"></a><span data-ttu-id="ff344-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ff344-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ff344-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="ff344-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ff344-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="ff344-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ff344-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="ff344-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ff344-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="ff344-107">Event Source</span></span>   | <span data-ttu-id="ff344-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff344-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="ff344-109">Componente</span><span class="sxs-lookup"><span data-stu-id="ff344-109">Component</span></span>    |                                       <span data-ttu-id="ff344-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="ff344-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="ff344-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ff344-111">Symbolic Name</span></span>  |                     <span data-ttu-id="ff344-112">X12Ta1InvalidNumberOfIncludedGroupsDescription</span><span class="sxs-lookup"><span data-stu-id="ff344-112">X12Ta1InvalidNumberOfIncludedGroupsDescription</span></span>                     |
|  <span data-ttu-id="ff344-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ff344-113">Message Text</span></span>   |                         <span data-ttu-id="ff344-114">Número de grupos incluidos no coinciden</span><span class="sxs-lookup"><span data-stu-id="ff344-114">Number Of included groups do not match</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="ff344-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="ff344-115">Explanation</span></span>  
 <span data-ttu-id="ff344-116">Este evento de error,  indica que el número de grupos del intercambio no es igual al número del finalizador de intercambio (campo IEA01).</span><span class="sxs-lookup"><span data-stu-id="ff344-116">This Error/Warning/Information event indicates that the number of groups in the interchange does not equal the number in the interchange trailer (IEA01 field).</span></span> <span data-ttu-id="ff344-117">Esto tiene lugar cuando el intercambio se conserva y se suspende al producirse un error.</span><span class="sxs-lookup"><span data-stu-id="ff344-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span> <span data-ttu-id="ff344-118">(El mensaje de error no se envía si el intercambio se conserva y los conjuntos de transacciones se suspenden al producirse un error o bien si el intercambio se divide.)</span><span class="sxs-lookup"><span data-stu-id="ff344-118">(The error message is not posted if the interchange is preserved and the transaction sets are suspended on an error, or if the interchange is split.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ff344-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ff344-119">User Action</span></span>  
 <span data-ttu-id="ff344-120">Para resolver este error, asegúrese de que el número que aparece en el campo IEA01 del finalizador de intercambio es el mismo que el número de grupos del intercambio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="ff344-120">To resolve this error, make sure that the number in the IEA01 field of the interchange trailer is the same as the number of groups in the interchange, and then resend the interchange.</span></span>