---
title: El esquema no contiene el elemento raíz | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efc33f2b-9e14-4d2e-8c8a-32b7696f80ea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c485ce27fc3a1932d7de47557080712e46b654e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279308"
---
# <a name="the-schema-does-not-contain-the-root-element"></a><span data-ttu-id="d4e38-102">El esquema no contiene el elemento raíz</span><span class="sxs-lookup"><span data-stu-id="d4e38-102">The schema does not contain the root element</span></span>
## <a name="details"></a><span data-ttu-id="d4e38-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d4e38-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4e38-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="d4e38-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d4e38-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d4e38-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d4e38-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="d4e38-106">Event ID</span></span>|-|  
|<span data-ttu-id="d4e38-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="d4e38-107">Event Source</span></span>|<span data-ttu-id="d4e38-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4e38-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="d4e38-109">Componente</span><span class="sxs-lookup"><span data-stu-id="d4e38-109">Component</span></span>|<span data-ttu-id="d4e38-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="d4e38-110">EDI Engine</span></span>|  
|<span data-ttu-id="d4e38-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d4e38-111">Symbolic Name</span></span>|<span data-ttu-id="d4e38-112">SchemaCode102ENullRootElement</span><span class="sxs-lookup"><span data-stu-id="d4e38-112">SchemaCode102ENullRootElement</span></span>|  
|<span data-ttu-id="d4e38-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d4e38-113">Message Text</span></span>|<span data-ttu-id="d4e38-114">El esquema no contiene el elemento raíz {0}.</span><span class="sxs-lookup"><span data-stu-id="d4e38-114">The schema does not contain the root element {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d4e38-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="d4e38-115">Explanation</span></span>  
 <span data-ttu-id="d4e38-116">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el mensaje entrante o que la canalización de envío no pudo procesar el mensaje saliente porque el esquema usado para validar el mensaje no contenía el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="d4e38-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming message or the send pipeline could not process the outgoing message because the schema used to validate the message did not contain the root element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d4e38-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d4e38-117">User Action</span></span>  
 <span data-ttu-id="d4e38-118">Para resolver este error, anule la implementación del esquema del documento, agregue el elemento raíz al esquema y vuelva a implementar el esquema.</span><span class="sxs-lookup"><span data-stu-id="d4e38-118">To resolve this error, undeploy the document schema, add the root element to the schema, and then redeploy the schema.</span></span>