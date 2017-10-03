---
title: "Advertencia: no se encontró el XPath de campo distintivo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.distingFieldXPathNotFound
ms.assetid: a925c39c-9ae1-4334-b329-aa2f5afd97ce
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9df2e34c27fe3e5e3540ac384443f86143bf741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="warning---distinguished-field-xpath-not-found"></a><span data-ttu-id="d5355-102">Advertencia: XPath de campo distintivo no encontrado</span><span class="sxs-lookup"><span data-stu-id="d5355-102">Warning - Distinguished Field XPath Not Found</span></span>
<span data-ttu-id="d5355-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="d5355-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d5355-104">BEC1006</span><span class="sxs-lookup"><span data-stu-id="d5355-104">BEC1006</span></span>  
  
 <span data-ttu-id="d5355-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="d5355-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d5355-106">El nodo correspondiente a la promoción del campo distintivo indicado es posible que no exista en el esquema.</span><span class="sxs-lookup"><span data-stu-id="d5355-106">The node corresponding to the indicated Distinguished Field promotion may not exist in the schema.</span></span> <span data-ttu-id="d5355-107">El Editor de BizTalk no se puede resolver especificaciones de XPath complejas, y si editó el XPath de la propiedad promocionada en el **Editar XPath de instancia** cuadro de diálogo, puede o no puede identificar correctamente el nodo que pretendía promocionar.</span><span class="sxs-lookup"><span data-stu-id="d5355-107">BizTalk Editor cannot resolve complex XPath specifications, and if you edited the promoted property XPath in the **Edit Instance XPath** dialog box, it may or may not correctly identify the node you intended to promote.</span></span>  
  
 <span data-ttu-id="d5355-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="d5355-108">**User Action**</span></span>  
  
 <span data-ttu-id="d5355-109">Puede evitar esta advertencia siga apareciendo cambiando el XPath de la propiedad promocionada en el **Editar XPath de instancia** cuadro de diálogo que se puede acceder desde las celdas de la **ruta del nodo** columna de la tabla en el **Campos distintivos** pestaña en el **promocionar propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d5355-109">You can keep this warning from appearing by changing the XPath for the promoted property in the **Edit Instance XPath** dialog box, which you can access from cells in the **Node Path** column of the table on the **Distinguished Fields** tab in the **Promote Properties** dialog box.</span></span> <span data-ttu-id="d5355-110">Puede tener acceso a la **promocionar propiedades** cuadro de diálogo desde el **promocionar propiedades** propiedad de la **esquema** nodo en el Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="d5355-110">You can access the **Promote Properties** dialog box from the **Promote Properties** property of the **Schema** node in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>