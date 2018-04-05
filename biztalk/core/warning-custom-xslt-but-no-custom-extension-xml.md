---
title: 'Advertencia: XSLT personalizado pero no hay XML de extensión personalizada | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.customXsltButNoCustomExtensionXML
ms.assetid: af008ac2-e9ae-4753-a5ba-bf4dbb711a4e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b67591e0e0dbb6b3ecac9aee1566c3245c9969a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="warning---custom-xslt-but-no-custom-extension-xml"></a><span data-ttu-id="988eb-102">Advertencia: XSLT personalizado pero no hay XML de extensión personalizada</span><span class="sxs-lookup"><span data-stu-id="988eb-102">Warning - Custom XSLT but No Custom Extension XML</span></span>
<span data-ttu-id="988eb-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="988eb-103">**Error Code**</span></span>  
  
 <span data-ttu-id="988eb-104">btm1034</span><span class="sxs-lookup"><span data-stu-id="988eb-104">btm1034</span></span>  
  
 <span data-ttu-id="988eb-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="988eb-105">**Explanation**</span></span>  
  
 <span data-ttu-id="988eb-106">El **ruta de XSLT personalizada** ha reemplazado la propiedad sin el **XML de extensión personalizada** que se reemplazara propiedad.</span><span class="sxs-lookup"><span data-stu-id="988eb-106">The **Custom XSLT Path** property has been overridden without the **Custom Extension XML** property being overridden.</span></span> <span data-ttu-id="988eb-107">Si esto sucede de forma intencionada, puede pasar por alto esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="988eb-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="988eb-108">El asignador de BizTalk utilizará el XSLT especificado por el **ruta de XSLT personalizada** propiedad y generar un archivo de asignación de XML de extensión ficticio.</span><span class="sxs-lookup"><span data-stu-id="988eb-108">BizTalk Mapper will use the XSLT specified by the **Custom XSLT Path** property and generate a dummy Extension XML mapping file.</span></span> <span data-ttu-id="988eb-109">Si realiza llamadas a ensamblados externos desde el XSLT personalizado proporcionado, debe especificar un archivo mediante la **XML de extensión personalizada** propiedad que contiene el prefijo de asignación de nombre de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="988eb-109">If you make calls to external assemblies from within the provided custom XSLT, you must specify a file using the **Custom Extension XML** property that contains the prefix to assembly name mapping.</span></span>  
  
 <span data-ttu-id="988eb-110">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="988eb-110">**User Action**</span></span>  
  
 <span data-ttu-id="988eb-111">Si la condición indicada por esta advertencia no era intencionada, escriba un valor compatible para la **XML de extensión personalizada** propiedad o quite la invalidación del valor para el **ruta de XSLT personalizada** propiedad.</span><span class="sxs-lookup"><span data-stu-id="988eb-111">If the condition indicated by this warning was not intentional, either provide a compatible value for the **Custom Extension XML** property or remove the override value for the **Custom XSLT Path** property.</span></span>