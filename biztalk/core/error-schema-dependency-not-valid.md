---
title: Error - dependencia de esquemas no válida | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.schemaDependencyNotValid
ms.assetid: 431278f0-6cd1-4b3f-8d87-16af4991d354
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36326608f191b520c41cb42890aec029c432fd30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241396"
---
# <a name="error---schema-dependency-not-valid"></a><span data-ttu-id="810bb-102">Error - dependencia de esquemas no válida</span><span class="sxs-lookup"><span data-stu-id="810bb-102">Error - Schema Dependency Not Valid</span></span>
<span data-ttu-id="810bb-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="810bb-103">**Error Code**</span></span>  
  
 <span data-ttu-id="810bb-104">BEC2009</span><span class="sxs-lookup"><span data-stu-id="810bb-104">BEC2009</span></span>  
  
 <span data-ttu-id="810bb-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="810bb-105">**Explanation**</span></span>  
  
 <span data-ttu-id="810bb-106">Todos los esquemas dependientes, como aquellos que se importan, incluyen o redefinen en el esquema en uso, deben agregarse al proyecto de BizTalk o existir en un ensamblado al que haga referencia este proyecto.</span><span class="sxs-lookup"><span data-stu-id="810bb-106">All dependent schemas, such as those that are imported, included, or redefined in the current schema, must be added to this BizTalk project or exist in an assembly referenced by this project.</span></span> <span data-ttu-id="810bb-107">Esquema incluso **importar**, **incluyen**, y **redefinir** directivas que especifican esquemas en un sitio Web remoto deben agregarse a este proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="810bb-107">Even schema **import**, **include**, and **redefine** directives that specify schemas on a remote Web site must be added to this BizTalk project.</span></span>  
  
 <span data-ttu-id="810bb-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="810bb-108">**User Action**</span></span>  
  
 <span data-ttu-id="810bb-109">Use la **Agregar elemento existente** comando el **archivo** menú y el menú contextual para el proyecto de Microsoft® BizTalk® Server para agregar todos los esquemas que depende este esquema al proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="810bb-109">Use the **Add Existing Item** command on the **File** menu and the shortcut menu for the Microsoft® BizTalk® Server project to add all schemas upon which this schema depends to the BizTalk project.</span></span> <span data-ttu-id="810bb-110">Es probable que necesite descargar estos esquemas de un sitio Web en el disco duro local antes de agregarlos al proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="810bb-110">You may need to download such schemas from a Web site to your local hard disk before adding them to the BizTalk project.</span></span>