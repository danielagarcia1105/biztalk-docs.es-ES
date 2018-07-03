---
title: Componente de canalización de mensajes desconocidos en el desensamblador XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Allow Unrecognized Messages property
- XMLNorm.AllowUnrecognizedMessage property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], unrecognized messages
ms.assetid: 5a6be3a8-0bac-426a-bf0b-5091191091de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c7df0ea8abe05f866d5cb4f9fb86d85083e1690
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987669"
---
# <a name="unrecognized-messages-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="8e174-102">Mensajes desconocidos en el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="8e174-102">Unrecognized Messages in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="8e174-103">El componente de canalización de desensamblador XML puede controlar un mensaje como "desconocido" en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="8e174-103">The XML Disassembler component may handle a message as "unrecognized" in the following cases:</span></span>  
  
- <span data-ttu-id="8e174-104">Se recibe un mensaje XML sin cuerpo, con el cuerpo vacío o con datos vacíos en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8e174-104">An XML message is received with no body, an empty body, or empty data in the body.</span></span>  
  
- <span data-ttu-id="8e174-105">Se recibe un mensaje XML pero no se ha implementado ningún esquema para él.</span><span class="sxs-lookup"><span data-stu-id="8e174-105">An XML message is received but no schema is deployed for it.</span></span>  
  
  <span data-ttu-id="8e174-106">Un mensaje desconocido se realiza según la **permitir mensaje desconocido** propiedad (o en el **XMLNorm.AllowUnrecognizedMessage** propiedad en el contexto del mensaje).</span><span class="sxs-lookup"><span data-stu-id="8e174-106">An unrecognized message is handled based on the **Allow Unrecognized Messages** property (or on the **XMLNorm.AllowUnrecognizedMessage** property on the message context).</span></span>  
  
  <span data-ttu-id="8e174-107">Si **permitir mensaje desconocido** está establecido en **True**, ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e174-107">If **Allow Unrecognized Messages** is set to **True**, the following occurs:</span></span>  
  
- <span data-ttu-id="8e174-108">Un mensaje sin cuerpo, con el cuerpo vacío/nulo o con datos vacíos/nulos en el cuerpo pasa sin ningún cambio a través del desensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="8e174-108">A message with no body, an empty/null body, or with empty/null data in the body passes unchanged through the XML Disassembler.</span></span>  
  
- <span data-ttu-id="8e174-109">Un documento XML sin ningún esquema implementado asociado pasa sin cambios a través del desensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="8e174-109">An XML document with no associated deployed schema passes unchanged through the XML Disassembler.</span></span>  
  
- <span data-ttu-id="8e174-110">El desensamblador XML procesa un documento XML que tiene un esquema implementado asociado independientemente de si se hace referencia explícita al esquema en una propiedad del componente o si se ha encontrado durante el proceso de resolución del esquema.</span><span class="sxs-lookup"><span data-stu-id="8e174-110">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
  <span data-ttu-id="8e174-111">Si **permitir mensaje desconocido** está establecido en **False**, ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e174-111">If **Allow Unrecognized Messages** is set to **False**, the following occurs:</span></span>  
  
- <span data-ttu-id="8e174-112">Un mensaje sin cuerpo, con el cuerpo vacío/nulo o con datos vacíos/nulos en el cuerpo no pasa a través del desensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="8e174-112">A message with no body or an empty/null body or with empty/null data in the body is not passed through the XML Disassembler.</span></span>  
  
- <span data-ttu-id="8e174-113">Un documento XML que no tiene un esquema implementado asociado no pasa a través del desensamblador.</span><span class="sxs-lookup"><span data-stu-id="8e174-113">An XML document that does not have a deployed schema associated with it is not passed through the disassembler.</span></span> <span data-ttu-id="8e174-114">Se genera un informe de error y se suspende el mensaje si es posible.</span><span class="sxs-lookup"><span data-stu-id="8e174-114">An error is reported and the message is suspended, if possible.</span></span>  
  
- <span data-ttu-id="8e174-115">El desensamblador XML procesa un documento XML que tiene un esquema implementado asociado independientemente de si se hace referencia explícita al esquema en una propiedad del componente o si se ha encontrado durante el proceso de resolución del esquema.</span><span class="sxs-lookup"><span data-stu-id="8e174-115">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
  <span data-ttu-id="8e174-116">De forma predeterminada, el desensamblador XML no permite mensajes desconocidos.</span><span class="sxs-lookup"><span data-stu-id="8e174-116">By default, the XML Disassembler does not allow unrecognized messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e174-117">No se procesan mensajes XML que no son el Desensamblador de XML sin tener en cuenta la **permitir mensaje desconocido** configuración de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e174-117">Non-XML messages are not processed by the XML Disassembler regardless of the **Allow Unrecognized Messages** property setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e174-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e174-118">See Also</span></span>  
 <span data-ttu-id="8e174-119">[Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="8e174-119">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="8e174-120">Cómo configurar el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="8e174-120">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)