---
title: No se puede serializar el mensaje ya no se pudo encontrar el esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37897c04-650d-4695-846d-b8ba61365647
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f366fc619ac070d618345ce6bde9996710b1242
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988189"
---
# <a name="message-cannot-be-serialized-as-the-schema-could-not-be-located"></a><span data-ttu-id="fd210-102">No se puede serializar el mensaje ya que el esquema no ha podido localizarse</span><span class="sxs-lookup"><span data-stu-id="fd210-102">Message cannot be serialized as the schema could not be located</span></span>
## <a name="details"></a><span data-ttu-id="fd210-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fd210-103">Details</span></span>  
  
|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fd210-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="fd210-104">Product Name</span></span>   |                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                            |
| <span data-ttu-id="fd210-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="fd210-105">Product Version</span></span> |                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                        |
|    <span data-ttu-id="fd210-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="fd210-106">Event ID</span></span>     |                                                                    -                                                                     |
|  <span data-ttu-id="fd210-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="fd210-107">Event Source</span></span>   |                          <span data-ttu-id="fd210-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd210-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                          |
|    <span data-ttu-id="fd210-109">Componente</span><span class="sxs-lookup"><span data-stu-id="fd210-109">Component</span></span>    |                                                                <span data-ttu-id="fd210-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="fd210-110">EDI Engine</span></span>                                                                |
|  <span data-ttu-id="fd210-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fd210-111">Symbolic Name</span></span>  |                                              <span data-ttu-id="fd210-112">MessageSerializationFailureDueToMissingSchema</span><span class="sxs-lookup"><span data-stu-id="fd210-112">MessageSerializationFailureDueToMissingSchema</span></span>                                               |
|  <span data-ttu-id="fd210-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fd210-113">Message Text</span></span>   | <span data-ttu-id="fd210-114">No se puede serializar el mensaje como el esquema {0} no se pudo encontrar.</span><span class="sxs-lookup"><span data-stu-id="fd210-114">Message can not be serialized as the schema {0} could not be located.</span></span> <span data-ttu-id="fd210-115">El esquema no está implementado o se han implementado varias copias.</span><span class="sxs-lookup"><span data-stu-id="fd210-115">Either the schema is not deployed or multiple copies are deployed.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="fd210-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="fd210-116">Explanation</span></span>  
 <span data-ttu-id="fd210-117">Este evento de error,  indica que la canalización de envío no pudo serializar el intercambio saliente porque la canalización no pudo determinar el esquema que debía usar para serializar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="fd210-117">This Error/Warning/Information event indicates that the send pipeline could not serialize the outgoing interchange because the pipeline could not determine the schema that it needed to use to serialize the interchange.</span></span> <span data-ttu-id="fd210-118">El esquema no está implementado o se han implementado varias copias del esquema.</span><span class="sxs-lookup"><span data-stu-id="fd210-118">The schema was either not deployed or multiple copies of the schema were deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fd210-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fd210-119">User Action</span></span>  
 <span data-ttu-id="fd210-120">Para resolver este error, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="fd210-120">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="fd210-121">Si no se ha implementado el esquema asociado con un intercambio, abra Visual Studio, agregue el esquema a un proyecto de BizTalk y genere e implemente el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fd210-121">If the schema associated with the interchange has not been deployed, open Visual Studio, add the schema to a BizTalk project, and then build and deploy the project.</span></span>  
  
2.  <span data-ttu-id="fd210-122">Si se ha implementado más de una copia del esquema, abra Visual Studio y anule la implementación de todas las copias del esquema asociadas con el intercambio menos una.</span><span class="sxs-lookup"><span data-stu-id="fd210-122">If more than one copy of the schema has been deployed, open Visual Studio, and undeploy all but one of the copies of the schema associated with the interchange.</span></span>