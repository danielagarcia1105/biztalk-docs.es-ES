---
title: "Error: nombre de clase de nodo raíz no válido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.rootNodeClassNameNotValid
ms.assetid: 48b4f7e4-8c20-4e94-86be-1425ea62f8c5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff170609ef37b1d7f2b00a4d4ca3952b89eef9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---root-node-class-name-not-valid"></a><span data-ttu-id="6ae20-102">Error: nombre de clase de nodo raíz no válido</span><span class="sxs-lookup"><span data-stu-id="6ae20-102">Error - Root Node Class Name Not Valid</span></span>
<span data-ttu-id="6ae20-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="6ae20-103">**Error Code**</span></span>  
  
 <span data-ttu-id="6ae20-104">BEC2012</span><span class="sxs-lookup"><span data-stu-id="6ae20-104">BEC2012</span></span>  
  
 <span data-ttu-id="6ae20-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="6ae20-105">**Explanation**</span></span>  
  
 <span data-ttu-id="6ae20-106">El **RootNode TypeName** propiedad de uno de los nodos raíz de este esquema no es válido.</span><span class="sxs-lookup"><span data-stu-id="6ae20-106">The **RootNode TypeName** property of one of the root nodes in this schema is not valid.</span></span> <span data-ttu-id="6ae20-107">Dado que el valor de la **RootNode TypeName** propiedad se utiliza como el nombre de un nombre de clase de C# generado automáticamente, debe ser un identificador C# válido y no puede ser una palabra clave de BizTalk reservada.</span><span class="sxs-lookup"><span data-stu-id="6ae20-107">Because the value of the **RootNode TypeName** property is used as the name of an automatically generated C# class name, it must be a valid C# identifier and cannot be a reserved BizTalk keyword.</span></span>  
  
 <span data-ttu-id="6ae20-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="6ae20-108">**User Action**</span></span>  
  
 <span data-ttu-id="6ae20-109">Seleccione el nodo raíz indicado y, a continuación, en la Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de propiedades, cambiar la **RootNode TypeName** propiedad en un valor que es un identificador válido de C# y no es una palabra clave de BizTalk reservada.</span><span class="sxs-lookup"><span data-stu-id="6ae20-109">Select the indicated root node, and then in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change the **RootNode TypeName** property to a value that is a valid C# identifier and is not a reserved BizTalk keyword.</span></span>