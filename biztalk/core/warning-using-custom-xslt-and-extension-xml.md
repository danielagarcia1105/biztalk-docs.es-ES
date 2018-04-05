---
title: 'Advertencia: utilizando XSLT personalizado y la extensión XML | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.usingCustomXsltAndExtensionXML
ms.assetid: b86da5fb-6435-4e3b-89b6-d9d036b5152b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90644aec738345e3a36286cc62aaa7a355e04348
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="warning---using-custom-xslt-and-extension-xml"></a><span data-ttu-id="d1d1c-102">Advertencia: se está utilizando XSLT personalizado y XML de extensión</span><span class="sxs-lookup"><span data-stu-id="d1d1c-102">Warning - Using Custom XSLT and Extension XML</span></span>
<span data-ttu-id="d1d1c-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="d1d1c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d1d1c-104">btm1035</span><span class="sxs-lookup"><span data-stu-id="d1d1c-104">btm1035</span></span>  
  
 <span data-ttu-id="d1d1c-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="d1d1c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d1d1c-106">Los valores de la presencia de invalidación para el **ruta de XSLT personalizada** y **XML de extensión personalizada** controla los mensajes de instancia de salida generados por esta asignación, omite por completo las asignaciones de propiedades especificar entre los esquemas de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="d1d1c-106">The presence of override values for the **Custom XSLT Path** and **Custom Extension XML** properties is controlling the output instance messages produced by this map, completely ignoring any mappings specified between the source and destination schemas.</span></span> <span data-ttu-id="d1d1c-107">Si esto sucede de forma intencionada, puede pasar por alto esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="d1d1c-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="d1d1c-108">Un escenario en que esto es válido consiste en utilizar el asignador de BizTalk para generar un XSLT preliminar para la asignación, modifique el XSLT manualmente para que cumpla requisitos adicionales específicos y, a continuación, especifique el archivo modificado como valor de la **ruta de XSLT personalizada** propiedad, con lo que se reemplaza el XSLT preliminar durante las operaciones de asignación posteriores.</span><span class="sxs-lookup"><span data-stu-id="d1d1c-108">One scenario in which this is valid is to use BizTalk Mapper to generate preliminary XSLT for the mapping, modify this XSLT by hand to meet specific additional requirements, and then specify the modified file as the value of the **Custom XSLT Path** property, thereby overriding the preliminary XSLT during subsequent mapping operations.</span></span>  
  
 <span data-ttu-id="d1d1c-109">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="d1d1c-109">**User Action**</span></span>  
  
 <span data-ttu-id="d1d1c-110">Si no desea reemplazar la asignación especificada en esta asignación, quite los valores de invalidación para el **ruta de XSLT personalizada** propiedad y el **XML de extensión personalizada** propiedad, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="d1d1c-110">If you do not intend to override the mapping specified within this map, remove the override values for the **Custom XSLT Path** property and the **Custom Extension XML** property, as appropriate.</span></span>