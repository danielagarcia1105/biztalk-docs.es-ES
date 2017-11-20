---
title: Esquema Validation1 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 599f1bbb-2af5-4278-8b0f-0e5a6517e8e3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20224a77530139a97647d91b0b46f9384d6c2753
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schema-validation"></a><span data-ttu-id="0846e-102">Validación de esquemas</span><span class="sxs-lookup"><span data-stu-id="0846e-102">Schema Validation</span></span>
<span data-ttu-id="0846e-103">Si una extensión del Editor de BizTalk proporciona un **ISchemaValidator** de objeto, el marco de trabajo invocará **ISchemaValidator.ValidateSchema** cuando el usuario invoca el **Validar esquema** comando, o durante la compilación cuando el usuario compila el proyecto de BizTalk que contiene el esquema.</span><span class="sxs-lookup"><span data-stu-id="0846e-103">If a BizTalk Editor extension provides an **ISchemaValidator** object, the framework will invoke **ISchemaValidator.ValidateSchema** when the user invokes the **Validate Schema** command, or during compilation when the user builds the BizTalk project containing the schema.</span></span> <span data-ttu-id="0846e-104">La extensión normalmente valida las propiedades personalizadas y puede devolver mensajes de error como una matriz de **IValidationInfo** objetos.</span><span class="sxs-lookup"><span data-stu-id="0846e-104">The extension usually validates the custom properties, and can return error messages as an array of **IValidationInfo** objects.</span></span> <span data-ttu-id="0846e-105">Los mensajes de error se muestran en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Lista de tareas, junto con los errores devueltos por el compilador del Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0846e-105">The error messages are displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Task List window, along with errors returned from BizTalk Editor compiler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0846e-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="0846e-106">See Also</span></span>  
 [<span data-ttu-id="0846e-107">Extender el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="0846e-107">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)