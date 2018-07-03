---
title: El nombre de propiedad no es una cadena válida | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a0641e4-1267-44a0-8777-bd6e2baf1088
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 944d9a4722f0c97ab09b66159bc04fc4715e01ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989861"
---
# <a name="the-property-name-is-not-a-valid-string"></a><span data-ttu-id="cebcc-102">El nombre de propiedad no es una cadena válida.</span><span class="sxs-lookup"><span data-stu-id="cebcc-102">The property name is not a valid string</span></span>
## <a name="details"></a><span data-ttu-id="cebcc-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cebcc-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="cebcc-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="cebcc-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="cebcc-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="cebcc-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="cebcc-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="cebcc-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="cebcc-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="cebcc-107">Event Source</span></span>   | <span data-ttu-id="cebcc-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cebcc-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="cebcc-109">Componente</span><span class="sxs-lookup"><span data-stu-id="cebcc-109">Component</span></span>    |                                    <span data-ttu-id="cebcc-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="cebcc-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="cebcc-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cebcc-111">Symbolic Name</span></span>  |                                  <span data-ttu-id="cebcc-112">InvalidPropertyName</span><span class="sxs-lookup"><span data-stu-id="cebcc-112">InvalidPropertyName</span></span>                                   |
|  <span data-ttu-id="cebcc-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cebcc-113">Message Text</span></span>   |                        <span data-ttu-id="cebcc-114">El nombre de propiedad no es una cadena válida.</span><span class="sxs-lookup"><span data-stu-id="cebcc-114">The property name is not a valid string</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="cebcc-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="cebcc-115">Explanation</span></span>  
 <span data-ttu-id="cebcc-116">Este evento de error indica que un nombre especificado para una propiedad en el cuadro de diálogo Filtro por lotes no era válido porque el nombre de la propiedad no era una cadena, como se requería.</span><span class="sxs-lookup"><span data-stu-id="cebcc-116">This Error/Warning/Information event indicates that the name entered for a property in the Batch Filter dialog box was invalid, because the property name was not a string, as required.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cebcc-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cebcc-117">User Action</span></span>  
 <span data-ttu-id="cebcc-118">Para resolver este error, abra el cuadro de diálogo Filtro por lotes de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="cebcc-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="cebcc-119">Asegúrese de que todos los nombres de propiedades son cadenas.</span><span class="sxs-lookup"><span data-stu-id="cebcc-119">Make sure that all property names are strings.</span></span>