---
title: 'Advertencia: campo XPath promocionado no encontrado | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.promoFieldXPathNotFound
ms.assetid: 21b8c240-5d6f-499d-8211-6e3f2ce2a79c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07f45bd1539817f010864226d07b76ca2feee8b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288532"
---
# <a name="warning---promoted-field-xpath-not-found"></a><span data-ttu-id="d67cb-102">Advertencia: campo XPath promocionado no encontrado</span><span class="sxs-lookup"><span data-stu-id="d67cb-102">Warning - Promoted Field XPath Not Found</span></span>
<span data-ttu-id="d67cb-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="d67cb-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d67cb-104">BEC1005</span><span class="sxs-lookup"><span data-stu-id="d67cb-104">BEC1005</span></span>  
  
 <span data-ttu-id="d67cb-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="d67cb-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d67cb-106">El nodo correspondiente a la promoción de campos de propiedades indicado es posible que no exista en el esquema.</span><span class="sxs-lookup"><span data-stu-id="d67cb-106">The node corresponding to the indicated property field promotion may not exist in the schema.</span></span> <span data-ttu-id="d67cb-107">El Editor de BizTalk no se puede resolver especificaciones de XPath complejas, y si editó el XPath de la propiedad promocionada en el **Editar XPath de instancia** cuadro de diálogo, puede o no puede identificar correctamente el nodo que pretendía promocionar.</span><span class="sxs-lookup"><span data-stu-id="d67cb-107">BizTalk Editor cannot resolve complex XPath specifications, and if you edited the promoted property XPath in the **Edit Instance XPath** dialog box, it may or may not correctly identify the node you intended to promote.</span></span>  
  
 <span data-ttu-id="d67cb-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="d67cb-108">**User Action**</span></span>  
  
 <span data-ttu-id="d67cb-109">Puede evitar esta advertencia siga apareciendo cambiando el XPath de la propiedad promocionada en el **Editar XPath de instancia** cuadro de diálogo que se puede acceder desde las celdas de la **ruta del nodo** columna de la **Lista de campos de propiedad** de tabla en la **campos de propiedades** pestaña en el **promocionar propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d67cb-109">You can keep this warning from appearing by changing the XPath for the promoted property in the **Edit Instance XPath** dialog box, which you can access from cells in the **Node Path** column of the **Property Field List** table on the **Property Fields** tab in the **Promote Properties** dialog box.</span></span> <span data-ttu-id="d67cb-110">Puede tener acceso a la **promocionar propiedades** cuadro de diálogo desde el **promocionar propiedades** propiedad de la **esquema** nodo en el Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="d67cb-110">You can access the **Promote Properties** dialog box from the **Promote Properties** property of the **Schema** node in the Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>