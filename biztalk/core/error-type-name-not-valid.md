---
title: 'Error: nombre de tipo no válido | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.typeNameNotValid
ms.assetid: 4c9bceeb-b009-4279-ad16-19af09e6b091
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dac6d85d3b16ec691a4cc73b179515b70686791
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---type-name-not-valid"></a><span data-ttu-id="b2927-102">Error: nombre de tipo no válido</span><span class="sxs-lookup"><span data-stu-id="b2927-102">Error - Type Name Not Valid</span></span>
<span data-ttu-id="b2927-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="b2927-103">**Error Code**</span></span>  
  
 <span data-ttu-id="b2927-104">BEC2011</span><span class="sxs-lookup"><span data-stu-id="b2927-104">BEC2011</span></span>  
  
 <span data-ttu-id="b2927-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="b2927-105">**Explanation**</span></span>  
  
 <span data-ttu-id="b2927-106">El **nombre de tipo** propiedad de este archivo de esquema no es válida.</span><span class="sxs-lookup"><span data-stu-id="b2927-106">The **Type Name** property of this schema file is not valid.</span></span> <span data-ttu-id="b2927-107">Dado que el valor de la **nombre de tipo** propiedad se utiliza como el nombre de un nombre de clase de C# generado automáticamente, debe ser un identificador C# válido y no puede ser una palabra clave de BizTalk reservada.</span><span class="sxs-lookup"><span data-stu-id="b2927-107">Because the value of the **Type Name** property is used as the name of an automatically generated C# class name, it must be a valid C# identifier and cannot be a reserved BizTalk keyword.</span></span>  
  
 <span data-ttu-id="b2927-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="b2927-108">**User Action**</span></span>  
  
 <span data-ttu-id="b2927-109">Seleccione el archivo de esquema correspondiente en Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones y, a continuación, en la ventana Propiedades, cambie la **nombre de tipo** propiedad en un valor que es un identificador válido de C# y no es una palabra clave de BizTalk reservada.</span><span class="sxs-lookup"><span data-stu-id="b2927-109">Select the relevant schema file in Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Type Name** property to a value that is a valid C# identifier and is not a reserved BizTalk keyword.</span></span>