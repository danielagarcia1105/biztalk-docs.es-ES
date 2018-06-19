---
title: Componente de canalización de mensajes desconocidos en el desensamblador XML | Documentos de Microsoft
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
ms.openlocfilehash: d82396002ff9d35484af5f0000dc3468c8ad37fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286748"
---
# <a name="unrecognized-messages-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="f20dd-102">Mensajes desconocidos en el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="f20dd-102">Unrecognized Messages in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="f20dd-103">El componente de canalización de desensamblador XML puede controlar un mensaje como "desconocido" en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="f20dd-103">The XML Disassembler component may handle a message as "unrecognized" in the following cases:</span></span>  
  
-   <span data-ttu-id="f20dd-104">Se recibe un mensaje XML sin cuerpo, con el cuerpo vacío o con datos vacíos en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="f20dd-104">An XML message is received with no body, an empty body, or empty data in the body.</span></span>  
  
-   <span data-ttu-id="f20dd-105">Se recibe un mensaje XML pero no se ha implementado ningún esquema para él.</span><span class="sxs-lookup"><span data-stu-id="f20dd-105">An XML message is received but no schema is deployed for it.</span></span>  
  
 <span data-ttu-id="f20dd-106">Un mensaje desconocido se controla en función de la **permitir mensaje desconocido** propiedad (o en la **XMLNorm.AllowUnrecognizedMessage** propiedad en el contexto del mensaje).</span><span class="sxs-lookup"><span data-stu-id="f20dd-106">An unrecognized message is handled based on the **Allow Unrecognized Messages** property (or on the **XMLNorm.AllowUnrecognizedMessage** property on the message context).</span></span>  
  
 <span data-ttu-id="f20dd-107">Si **permitir mensaje desconocido** está establecido en **True**, ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f20dd-107">If **Allow Unrecognized Messages** is set to **True**, the following occurs:</span></span>  
  
-   <span data-ttu-id="f20dd-108">Un mensaje sin cuerpo, con el cuerpo vacío/nulo o con datos vacíos/nulos en el cuerpo pasa sin ningún cambio a través del desensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="f20dd-108">A message with no body, an empty/null body, or with empty/null data in the body passes unchanged through the XML Disassembler.</span></span>  
  
-   <span data-ttu-id="f20dd-109">Un documento XML sin ningún esquema implementado asociado pasa sin cambios a través del desensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="f20dd-109">An XML document with no associated deployed schema passes unchanged through the XML Disassembler.</span></span>  
  
-   <span data-ttu-id="f20dd-110">El desensamblador XML procesa un documento XML que tiene un esquema implementado asociado independientemente de si se hace referencia explícita al esquema en una propiedad del componente o si se ha encontrado durante el proceso de resolución del esquema.</span><span class="sxs-lookup"><span data-stu-id="f20dd-110">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
 <span data-ttu-id="f20dd-111">Si **permitir mensaje desconocido** está establecido en **False**, ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f20dd-111">If **Allow Unrecognized Messages** is set to **False**, the following occurs:</span></span>  
  
-   <span data-ttu-id="f20dd-112">Un mensaje sin cuerpo, con el cuerpo vacío/nulo o con datos vacíos/nulos en el cuerpo no pasa a través del desensamblador XML.</span><span class="sxs-lookup"><span data-stu-id="f20dd-112">A message with no body or an empty/null body or with empty/null data in the body is not passed through the XML Disassembler.</span></span>  
  
-   <span data-ttu-id="f20dd-113">Un documento XML que no tiene un esquema implementado asociado no pasa a través del desensamblador.</span><span class="sxs-lookup"><span data-stu-id="f20dd-113">An XML document that does not have a deployed schema associated with it is not passed through the disassembler.</span></span> <span data-ttu-id="f20dd-114">Se genera un informe de error y se suspende el mensaje si es posible.</span><span class="sxs-lookup"><span data-stu-id="f20dd-114">An error is reported and the message is suspended, if possible.</span></span>  
  
-   <span data-ttu-id="f20dd-115">El desensamblador XML procesa un documento XML que tiene un esquema implementado asociado independientemente de si se hace referencia explícita al esquema en una propiedad del componente o si se ha encontrado durante el proceso de resolución del esquema.</span><span class="sxs-lookup"><span data-stu-id="f20dd-115">An XML document that has a deployed schema associated with it is processed by the XML Disassembler regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process.</span></span>  
  
 <span data-ttu-id="f20dd-116">De forma predeterminada, el desensamblador XML no permite mensajes desconocidos.</span><span class="sxs-lookup"><span data-stu-id="f20dd-116">By default, the XML Disassembler does not allow unrecognized messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f20dd-117">No se procesan mensajes que no sean XML el Desensamblador de XML sin tener en cuenta el **permitir mensaje desconocido** configuración de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f20dd-117">Non-XML messages are not processed by the XML Disassembler regardless of the **Allow Unrecognized Messages** property setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f20dd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f20dd-118">See Also</span></span>  
 <span data-ttu-id="f20dd-119">[Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="f20dd-119">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="f20dd-120">Cómo configurar el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="f20dd-120">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)