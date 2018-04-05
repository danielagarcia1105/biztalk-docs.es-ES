---
title: 'Error: estructura de esquema de propiedad no es válido | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.propSchemaStructNotValid<
ms.assetid: c5fd81a7-fa5a-4ec2-b895-00b280aca227
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b96634dc3a0b72b56f33107fc596d3bd29e40c7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---property-schema-structure-not-valid"></a><span data-ttu-id="a3861-102">Error: estructura de esquema de propiedad no es válido</span><span class="sxs-lookup"><span data-stu-id="a3861-102">Error - Property Schema Structure Not Valid</span></span>
<span data-ttu-id="a3861-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="a3861-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a3861-104">BEC2007</span><span class="sxs-lookup"><span data-stu-id="a3861-104">BEC2007</span></span>  
  
 <span data-ttu-id="a3861-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="a3861-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a3861-106">Se ha detectado que este esquema de propiedades tiene una estructura que no es válida.</span><span class="sxs-lookup"><span data-stu-id="a3861-106">This property schema was found to have a structure that is not valid.</span></span> <span data-ttu-id="a3861-107">La estructura de esquemas de propiedades se limita a uno o varios **elemento de campo** nodos como elementos secundarios de la **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="a3861-107">The structure of property schemas is limited to one or more **Field Element** nodes as children of the **Schema** node.</span></span>  
  
 <span data-ttu-id="a3861-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="a3861-108">**User Action**</span></span>  
  
 <span data-ttu-id="a3861-109">Corrija la estructura de este esquema de propiedad para que la **esquema** nodo solo tiene **elemento de campo** nodos como elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="a3861-109">Correct the structure of this property schema so that the **Schema** node only has **Field Element** nodes as children.</span></span>