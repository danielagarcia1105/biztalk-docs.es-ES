---
title: Error de serialización Xml de intercambio EDIFACT debido a una estructura no válida, sin FunctionalGroup o ServiceSchema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 530faadd-e301-4743-b4b3-b04ba7578f1d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 370b9844faaa46955f6e45bfcea78f6eba0f8cf9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003160"
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-functionalgroup-or-serviceschema"></a><span data-ttu-id="e9efc-102">Error de serialización Xml de intercambio Edifact debido a una estructura no válida, sin FunctionalGroup o ServiceSchema</span><span class="sxs-lookup"><span data-stu-id="e9efc-102">Edifact interchange Xml serialization failed due to invalid structure, no FunctionalGroup or ServiceSchema</span></span>
## <a name="details"></a><span data-ttu-id="e9efc-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e9efc-103">Details</span></span>  
  
|                 |                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e9efc-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="e9efc-104">Product Name</span></span>   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| <span data-ttu-id="e9efc-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="e9efc-105">Product Version</span></span> |                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    <span data-ttu-id="e9efc-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="e9efc-106">Event ID</span></span>     |                                                                      -                                                                       |
|  <span data-ttu-id="e9efc-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="e9efc-107">Event Source</span></span>   |                            <span data-ttu-id="e9efc-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9efc-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                            |
|    <span data-ttu-id="e9efc-109">Componente</span><span class="sxs-lookup"><span data-stu-id="e9efc-109">Component</span></span>    |                                                                  <span data-ttu-id="e9efc-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="e9efc-110">EDI Engine</span></span>                                                                  |
|  <span data-ttu-id="e9efc-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e9efc-111">Symbolic Name</span></span>  |                                                                      -                                                                       |
|  <span data-ttu-id="e9efc-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e9efc-112">Message Text</span></span>   | <span data-ttu-id="e9efc-113">Error de serialización Xml de intercambio Edifact debido a una estructura no válida.</span><span class="sxs-lookup"><span data-stu-id="e9efc-113">Edifact interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="e9efc-114">Se busca FunctionalGroup o ServiceSchema para UNZ, pero no se encuentra ninguno.</span><span class="sxs-lookup"><span data-stu-id="e9efc-114">Looking for FunctionalGroup or ServiceSchema for UNZ, but none found.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e9efc-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="e9efc-115">Explanation</span></span>  
 <span data-ttu-id="e9efc-116">Este evento de error,  indica que la canalización de envío no pudo procesar un intercambio EDIFACT procesado por lotes y conservado porque las etiquetas TransactionSetGroup o FunctionalGroup no se incluyeron en el archivo XML de intercambio.</span><span class="sxs-lookup"><span data-stu-id="e9efc-116">This Error/Warning/Information event indicates that the send pipeline could not process an EDIFACT batched interchange that was preserved because the TransactionSetGroup or FunctionalGroup tags were not included in the interchange XML file.</span></span>  
  
 <span data-ttu-id="e9efc-117">Cuando BizTalk procesa un intercambio por lotes conservado, se asigna una etiqueta XML a un grupo de conjuntos de transacciones o a un grupo de los grupos del archivo XML del intercambio.</span><span class="sxs-lookup"><span data-stu-id="e9efc-117">When BizTalk processes a batched interchange that is preserved, a group of transaction sets or a group of groups in the interchange's XML file are given an XML tag.</span></span> <span data-ttu-id="e9efc-118">A un grupo de grupos se le asigna la etiqueta FunctionalGroup.</span><span class="sxs-lookup"><span data-stu-id="e9efc-118">A group of groups is given the FunctionalGroup tag.</span></span> <span data-ttu-id="e9efc-119">El indicador ServiceSchema indica el esquema de control usado para el intercambio de lotes conservados.</span><span class="sxs-lookup"><span data-stu-id="e9efc-119">The ServiceSchema flag indicates the control schema used for the preserved-batch interchange.</span></span> <span data-ttu-id="e9efc-120">Esta condición de error tiene lugar si configura un lote conservado mediante una canalización de recepción y una canalización de envío de transmisión de atravesar.</span><span class="sxs-lookup"><span data-stu-id="e9efc-120">This error condition occurs if you set up a preserved batch using a receive pipeline and a passthrough transmit send pipeline.</span></span> <span data-ttu-id="e9efc-121">La canalización de recepción configura las etiquetas y la de envío las elimina.</span><span class="sxs-lookup"><span data-stu-id="e9efc-121">The tags are set by the receive pipeline and stripped out by the send pipeline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e9efc-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e9efc-122">User Action</span></span>  
 <span data-ttu-id="e9efc-123">Para resolver este error, asegúrese de que el archivo XML generado para el lote conservado tiene una estructura XML bien formada con la etiqueta FunctionalGroup (para varios grupos) o ServiceSchema (para el esquema de control usado para el intercambio por lotes conservado).</span><span class="sxs-lookup"><span data-stu-id="e9efc-123">To resolve this error, ensure that the XML file generated for the preserved batch has a well-formed XML structure with the FunctionalGroup tag (for multiple groups) and/or the ServiceSchema tag (for the control schema used for the preserved-batch interchange).</span></span>