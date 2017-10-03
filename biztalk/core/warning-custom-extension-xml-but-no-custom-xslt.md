---
title: "Advertencia: XML de extensión personalizada pero no hay XSLT personalizado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.warning.customExtensionXmlButNoCustomXSLT
ms.assetid: 3219c73c-2e58-4fe2-bc6e-2d60348d2415
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b626f8ede3231c04ae74dc0097cbdf524c90522
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="warning---custom-extension-xml-but-no-custom-xslt"></a><span data-ttu-id="c95bc-102">Advertencia: XML de extensión personalizada pero no hay XSLT personalizado</span><span class="sxs-lookup"><span data-stu-id="c95bc-102">Warning - Custom Extension XML But No Custom XSLT</span></span>
<span data-ttu-id="c95bc-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="c95bc-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c95bc-104">btm1033</span><span class="sxs-lookup"><span data-stu-id="c95bc-104">btm1033</span></span>  
  
 <span data-ttu-id="c95bc-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="c95bc-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c95bc-106">El **XML de extensión personalizada** ha reemplazado la propiedad sin el **ruta de XSLT personalizada** que se reemplazara propiedad.</span><span class="sxs-lookup"><span data-stu-id="c95bc-106">The **Custom Extension XML** property has been overridden without the **Custom XSLT Path** property being overridden.</span></span> <span data-ttu-id="c95bc-107">Si esto sucede de forma intencionada, puede pasar por alto esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="c95bc-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="c95bc-108">El Asignador de BizTalk utilizará el XSLT generado mediante la compilación de la asignación y también generará el XML de extensión y lo anexará al XML de extensión personalizada especificado por la propiedad reemplazada.</span><span class="sxs-lookup"><span data-stu-id="c95bc-108">BizTalk Mapper will use the XSLT produced by compiling the map and will also generate the Extension XML and append it to the custom Extension XML specified by the overridden property.</span></span> <span data-ttu-id="c95bc-109">Esto puede resultar útil si la asignación contiene **secuencias de comandos** plantillas que realicen llamadas a uno o más métodos de los ensamblados externos de llamadas de functoids que utilicen XSLT en línea o XSLT en línea.</span><span class="sxs-lookup"><span data-stu-id="c95bc-109">This can be useful when the map contains **Scripting** functoids that use inline XSLT or inline XSLT call templates that make calls to one or more methods in external assemblies.</span></span> <span data-ttu-id="c95bc-110">En tales casos, el usuario, a continuación, puede especificar el prefijo de asignación de nombre de ensamblado en el **XML de extensión personalizada** propiedad.</span><span class="sxs-lookup"><span data-stu-id="c95bc-110">In such cases, the user can then specify the prefix to assembly name mapping in the **Custom Extension XML** property.</span></span>  
  
 <span data-ttu-id="c95bc-111">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="c95bc-111">**User Action**</span></span>  
  
 <span data-ttu-id="c95bc-112">Si la condición indicada por esta advertencia no era intencionada, escriba un valor compatible para la **ruta de XSLT personalizada** propiedad o quite la invalidación del valor para el **XML de extensión personalizada** propiedad.</span><span class="sxs-lookup"><span data-stu-id="c95bc-112">If the condition indicated by this warning was not intentional, either provide a compatible value for the **Custom XSLT Path** property or remove the override value for the **Custom Extension XML** property.</span></span>