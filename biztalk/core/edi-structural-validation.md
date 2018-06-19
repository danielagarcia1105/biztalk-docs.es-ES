---
title: Validación estructural de EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87086614-5616-441d-915c-2979c63c6e2f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505b9ac55eff0b6adb249d11788308f03902f1d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239596"
---
# <a name="edi-structural-validation"></a><span data-ttu-id="96497-102">Validación estructural de EDI</span><span class="sxs-lookup"><span data-stu-id="96497-102">EDI Structural Validation</span></span>
<span data-ttu-id="96497-103">Las especificaciones EDI de las codificaciones X12 y EDIFACT definen las reglas y convenciones específicas de la estructura de los intercambios EDI.</span><span class="sxs-lookup"><span data-stu-id="96497-103">EDI specifications for both X12 and EDIFACT encoding define specific rules and conventions for the structure of EDI interchanges.</span></span> <span data-ttu-id="96497-104">El desensamblador EDI de EDIReceivePipeline comprueba que el sobre de cada mensaje recibido cumple con estas reglas estructurales.</span><span class="sxs-lookup"><span data-stu-id="96497-104">The EDI Disassembler in the EDIReceivePipeline verifies that the envelope of each received message complies with these structural rules.</span></span> <span data-ttu-id="96497-105">EDISendPipeline genera cada mensaje que se va a enviar según estas reglas y valida el sobre antes de enviarlo.</span><span class="sxs-lookup"><span data-stu-id="96497-105">The EDISendPipeline builds each message to be sent in accordance with these rules and validates the envelope before sending.</span></span>  
  
 <span data-ttu-id="96497-106">La validación estructural garantiza que están presentes los encabezados y los finalizadores necesarios.</span><span class="sxs-lookup"><span data-stu-id="96497-106">The structural validation ensures that the required headers and trailers are present.</span></span> <span data-ttu-id="96497-107">Las comprobaciones de integridad estructural incluyen comprobaciones de número y orden de bucle.</span><span class="sxs-lookup"><span data-stu-id="96497-107">The structural integrity checks include segment and loop ordering and count checks.</span></span> <span data-ttu-id="96497-108">Estas comprobaciones siempre se llevan a cabo para asegurarse de que el documento se analizará o serializará correctamente.</span><span class="sxs-lookup"><span data-stu-id="96497-108">These checks are always performed to ensure that the document will parse or serialize correctly.</span></span> <span data-ttu-id="96497-109">Se realiza la validación incluso si la **validación de tipo EDI** o **validación extendida** opciones están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="96497-109">This validation is performed even if the **EDI Type Validation** and/or **Extended Validation** options are disabled.</span></span> <span data-ttu-id="96497-110">Un intercambio que se produce un error en las validaciones estructurales básicas se suspenderá, incluso si la **validación de tipo EDI** o **validación extendida** opciones están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="96497-110">An interchange that fails the basic structural validations will be suspended, even if the **EDI Type Validation** and/or **Extended Validation** options are disabled.</span></span>  
  
 <span data-ttu-id="96497-111">Los valores de los elementos de datos de los encabezados y finalizadores y el modo en que se separan los encabezados/finalizadores y los elementos de datos vienen determinados en el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="96497-111">The values of the data elements within the headers and trailers, and how the headers/trailers and data elements are separated, are determined by the agreement.</span></span> <span data-ttu-id="96497-112">Se validan mediante la validación del esquema.</span><span class="sxs-lookup"><span data-stu-id="96497-112">These are validated through schema validation.</span></span>  
  
 <span data-ttu-id="96497-113">Para obtener más información acerca sobre y el contenido de cada conjunto de encabezados y finalizadores, vea [estructura de mensaje EDI](../core/edi-message-structure.md).</span><span class="sxs-lookup"><span data-stu-id="96497-113">For more information about the envelope and the contents within each set of headers and trailers, see [EDI Message Structure](../core/edi-message-structure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96497-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="96497-114">See Also</span></span>  
 [<span data-ttu-id="96497-115">Validación del mensaje EDI</span><span class="sxs-lookup"><span data-stu-id="96497-115">EDI Message Validation</span></span>](../core/edi-message-validation.md)