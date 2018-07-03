---
title: 'Error durante la generación de instancias: campo puede repetirse, pero no se definió el delimitador de repetición | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7a6783c-cb35-4ce8-9164-ec34ae500de1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6e5ed96162adac55de0bda042a12d45b4243eef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971149"
---
# <a name="error-encountered-during-instance-generation--field-can-repeat-but-repetition-delimiter-has-not-been-defined"></a><span data-ttu-id="2af6b-102">Error detectado durante la generación de instancias: el campo puede repetirse, pero el delimitador de repeticiones no se ha definido</span><span class="sxs-lookup"><span data-stu-id="2af6b-102">Error encountered during instance generation--field can repeat but repetition delimiter has not been defined</span></span>
## <a name="details"></a><span data-ttu-id="2af6b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2af6b-103">Details</span></span>  
  
|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2af6b-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="2af6b-104">Product Name</span></span>   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                   |
| <span data-ttu-id="2af6b-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="2af6b-105">Product Version</span></span> |                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                               |
|    <span data-ttu-id="2af6b-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="2af6b-106">Event ID</span></span>     |                                                           -                                                           |
|  <span data-ttu-id="2af6b-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="2af6b-107">Event Source</span></span>   |                <span data-ttu-id="2af6b-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2af6b-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                 |
|    <span data-ttu-id="2af6b-109">Componente</span><span class="sxs-lookup"><span data-stu-id="2af6b-109">Component</span></span>    |                                                      <span data-ttu-id="2af6b-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="2af6b-110">EDI Engine</span></span>                                                       |
|  <span data-ttu-id="2af6b-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2af6b-111">Symbolic Name</span></span>  |                                                           -                                                           |
|  <span data-ttu-id="2af6b-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2af6b-112">Message Text</span></span>   | <span data-ttu-id="2af6b-113">Error detectado durante la generación de instancias.</span><span class="sxs-lookup"><span data-stu-id="2af6b-113">Error encountered during instance generation.</span></span> <span data-ttu-id="2af6b-114">El campo {0} puede repetirse, pero no se definió el delimitador de repeticiones.</span><span class="sxs-lookup"><span data-stu-id="2af6b-114">The field {0} can repeat but repetition delimiter has not been defined.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2af6b-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="2af6b-115">Explanation</span></span>  
 <span data-ttu-id="2af6b-116">Este evento de error,  indica que BizTalk Server no pudo generar una instancia de mensaje X12 porque el campo indicado se puede repetir (según especifica el esquema) pero no se ha definido ningún separador de repetición.</span><span class="sxs-lookup"><span data-stu-id="2af6b-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an X12 message instance because the indicated field can repeat (as specified by the schema), but no repetition separator has been defined.</span></span> <span data-ttu-id="2af6b-117">Esto tiene lugar cuando un campo del esquema tiene minOccurs igual o superior a 1, pero se ha definido un identificador estándar en lugar de un separador de repetición.</span><span class="sxs-lookup"><span data-stu-id="2af6b-117">This occurs when a field in the schema has minOccurs equal to more than 1, but a Standard identifier has been defined, rather than a Repetition separator.</span></span> <span data-ttu-id="2af6b-118">(Para intercambios EDIFACT, de manera predeterminada se define un separador de repetición).</span><span class="sxs-lookup"><span data-stu-id="2af6b-118">(For EDIFACT interchanges, a repetition separator is defined by default.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2af6b-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2af6b-119">User Action</span></span>  
 <span data-ttu-id="2af6b-120">Para resolver este error, seleccione un separador de repetición en lugar de un identificador estándar para ISA11 en la página Definición de segmento ISA para la entidad como receptor de intercambio y especifique un carácter como separador.</span><span class="sxs-lookup"><span data-stu-id="2af6b-120">To resolve this error, select Repetition separator rather than Standard identifier for ISA11 in the ISA Segment Definition page for the party as interchange receiver, and enter a character for the separator.</span></span> <span data-ttu-id="2af6b-121">Si no se ha resuelto ninguna entidad para el intercambio, defina el separador de repetición en la página Definición de segmento ISA de las propiedades globales (para intercambios X12).</span><span class="sxs-lookup"><span data-stu-id="2af6b-121">If no party has been resolved for the interchange, define the repetition separator in the ISA Segment Definition page of the global properties (for X12 interchanges).</span></span>