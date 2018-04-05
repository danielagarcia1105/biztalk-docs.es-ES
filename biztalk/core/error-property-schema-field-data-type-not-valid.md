---
title: 'Error: tipo de datos de campo de esquema de propiedad no es válido | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.propSchemaFieldDataTypeNotValid
ms.assetid: eba41c5c-5512-4cc9-ab10-07626cfbd178
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e0019ccb4f8d138245e2bd58174ed22a532ee7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---property-schema-field-data-type-not-valid"></a><span data-ttu-id="c2c86-102">Error: tipo de datos de campo de esquema de propiedad no es válido</span><span class="sxs-lookup"><span data-stu-id="c2c86-102">Error - Property Schema Field Data Type Not Valid</span></span>
<span data-ttu-id="c2c86-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="c2c86-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c2c86-104">BEC2010</span><span class="sxs-lookup"><span data-stu-id="c2c86-104">BEC2010</span></span>  
  
 <span data-ttu-id="c2c86-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="c2c86-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c2c86-106">El **tipo de datos** propiedad de **elemento de campo** nodos en esquemas de propiedad deben establecerse en uno de los tipos de datos indicados.</span><span class="sxs-lookup"><span data-stu-id="c2c86-106">The **Data Type** property of **Field Element** nodes in property schemas must be set to one of the indicated data types.</span></span> <span data-ttu-id="c2c86-107">No puede utilizar otros tipos de datos en esquemas de propiedades porque la promoción de propiedades se limita a los datos de este tipo.</span><span class="sxs-lookup"><span data-stu-id="c2c86-107">Because property promotion is limited to data of these types only, you cannot use other data types in property schemas.</span></span>  
  
 <span data-ttu-id="c2c86-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="c2c86-108">**User Action**</span></span>  
  
 <span data-ttu-id="c2c86-109">Seleccione el functoid **elemento de campo** nodo y, a continuación, en el Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de propiedades, cambiar la **tipo de datos** propiedad en uno de los tipos de datos indicados.</span><span class="sxs-lookup"><span data-stu-id="c2c86-109">Select the indicated **Field Element** node, and then in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change the **Data Type** property to one of the indicated data types.</span></span>