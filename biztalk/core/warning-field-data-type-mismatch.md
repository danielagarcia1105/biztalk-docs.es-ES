---
title: 'Advertencia: error de coincidencia de tipo de datos de campo | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.fieldDataTypeMismatch
ms.assetid: 0c15d926-1d05-404b-bb16-a5fe8bc3575d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af42f5c921333e34c9ee219020cdb0fba97a7b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="warning---field-data-type-mismatch"></a><span data-ttu-id="4ec62-102">Advertencia: error de coincidencia de tipo de datos de campo</span><span class="sxs-lookup"><span data-stu-id="4ec62-102">Warning - Field Data Type Mismatch</span></span>
<span data-ttu-id="4ec62-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="4ec62-103">**Error Code**</span></span>  
  
 <span data-ttu-id="4ec62-104">BEC1002</span><span class="sxs-lookup"><span data-stu-id="4ec62-104">BEC1002</span></span>  
  
 <span data-ttu-id="4ec62-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="4ec62-105">**Explanation**</span></span>  
  
 <span data-ttu-id="4ec62-106">El **tipo de datos** se encontró la propiedad del nodo indicado sea diferente de la **tipo de datos** propiedad de la **elemento de campo** nodo al que se está promocionando en el esquema de propiedad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4ec62-106">The **Data Type** property of the indicated node was found to be different than the **Data Type** property of the **Field Element** node to which it is being promoted in the corresponding property schema.</span></span> <span data-ttu-id="4ec62-107">El tipo de datos de un nodo en un esquema debe coincidir con el tipo de datos asignado a la **elemento de campo** nodo se utiliza para su promoción de campos de propiedades o, como mínimo, deben asignar los tipos de datos asignado para el mismo tipo de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4ec62-107">The data type of a node in a schema should match the data type assigned to the **Field Element** node used for its Property Field promotion, or at least, the assigned data types should map to the same common language runtime (CLR) type.</span></span>  
  
 <span data-ttu-id="4ec62-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="4ec62-108">**User Action**</span></span>  
  
 <span data-ttu-id="4ec62-109">Cambiar el **tipo de datos** propiedades del nodo indicado y el **elemento de campo** nodo al que se está promocionando a los mismos datos escribir valor, o al menos para datos de tipo de valores que se asignan al mismo tipo de datos CLR.</span><span class="sxs-lookup"><span data-stu-id="4ec62-109">Change the **Data Type** properties of the indicated node and the **Field Element** node to which it is being promoted to the same data type value, or at least to data type values that map to the same CLR data type.</span></span>