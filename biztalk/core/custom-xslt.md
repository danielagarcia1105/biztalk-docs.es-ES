---
title: XSLT personalizado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- functoid types, Scripting
- maps, customizing
- functoid types, Looping
- maps, extending
- XSLT, maps
- Scripting functoids
- maps, XSLT
- customizing, maps
- maps, replacing
ms.assetid: e254d16d-4d16-4c23-a3ed-cc98eea9939a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4adf2abe438b3972419184b1297eaff5578c5bde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="custom-xslt"></a><span data-ttu-id="5f4e6-102">XSLT personalizado</span><span class="sxs-lookup"><span data-stu-id="5f4e6-102">Custom XSLT</span></span>
<span data-ttu-id="5f4e6-103">Si está familiarizado con el código Transformación de lenguaje de hojas de estilo extensible (XSLT), puede utilizarlo para personalizar, ampliar o reemplazar las asignaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5f4e6-103">If you are familiar with Extensible Stylesheet Language Transformations (XSLT) code, you can use it to customize, extend, or replace BizTalk maps.</span></span> <span data-ttu-id="5f4e6-104">Es la manera más sencilla de utilizar XSLT con la **secuencias de comandos** functoid.</span><span class="sxs-lookup"><span data-stu-id="5f4e6-104">The simplest way to use XSLT is with the **Scripting** functoid.</span></span> <span data-ttu-id="5f4e6-105">El **secuencias de comandos** functoid acepta secuencias de comandos en muchos. NET lenguajes compatibles, incluido XSLT.</span><span class="sxs-lookup"><span data-stu-id="5f4e6-105">The **Scripting** functoid accepts scripts in many .NET-enabled languages, including XSLT.</span></span> <span data-ttu-id="5f4e6-106">Para obtener más información sobre el uso de XSLT con la **secuencias de comandos** functoid, consulte [secuencias de comandos XSLT en línea utilizando plantillas y XSLT llamar a](../core/scripting-using-inline-xslt-and-xslt-call-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5f4e6-106">For more information about using XSLT with the **Scripting** functoid, see [Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md).</span></span>  
  
 <span data-ttu-id="5f4e6-107">Si dispone del código XSLT que ha utilizado para convertir un mensaje de instancia en otro, puede utilizar este código directamente en vez de una asignación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5f4e6-107">If you have XSLT code that you have been using to convert one instance message into another, you can use that code directly in place of a BizTalk map.</span></span> <span data-ttu-id="5f4e6-108">Para obtener información sobre cómo reemplazar BizTalk se asigna al código XSLT, consulte [cómo crear una asignación sin asignaciones](../core/how-to-create-a-map-without-maps.md).</span><span class="sxs-lookup"><span data-stu-id="5f4e6-108">For information about replacing BizTalk maps with your XSLT code, see [How to Create a Map without Maps](../core/how-to-create-a-map-without-maps.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f4e6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f4e6-109">See Also</span></span>  
 <span data-ttu-id="5f4e6-110">[Mapas](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="5f4e6-110">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="5f4e6-111">Crear asignaciones usando al asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="5f4e6-111">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)