---
title: 'Error: el archivo de esquema no está en compilación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.schemaFileNotInBuild
ms.assetid: 9190868d-a1ae-48bf-ac85-510086805887
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3b5d6d11bec6b9f263e2f204f004a9a162de471
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---schema-file-not-in-build"></a><span data-ttu-id="1a174-102">Error: el archivo de esquema no está en compilación</span><span class="sxs-lookup"><span data-stu-id="1a174-102">Error - Schema File Not In Build</span></span>
<span data-ttu-id="1a174-103">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="1a174-103">**Explanation**</span></span>  
  
 <span data-ttu-id="1a174-104">El comando (**Validar instancia**, **generar instancia**, o **Validar esquema**) no se pudo realizar porque el **acción de compilación** propiedad del archivo de esquema se establece en **ninguno**, impide que este esquema utilizar estos comandos.</span><span class="sxs-lookup"><span data-stu-id="1a174-104">The command (**Validate Instance**, **Generate Instance**, or **Validate Schema**) could not be performed because the **Build Action** property of the schema file is set to **None**, preventing this schema from participating in these commands.</span></span>  
  
 <span data-ttu-id="1a174-105">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="1a174-105">**User Action**</span></span>  
  
 <span data-ttu-id="1a174-106">Seleccione el archivo de esquema correspondiente en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones y, a continuación, en la ventana Propiedades, cambie la **acción de compilación** propiedad a una **compilar**.</span><span class="sxs-lookup"><span data-stu-id="1a174-106">Select the relevant schema file in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Build Action** property to a **Compile**.</span></span> <span data-ttu-id="1a174-107">A continuación, intente la **Validar instancia**, **generar instancia**, o **Validar esquema** comando nuevo.</span><span class="sxs-lookup"><span data-stu-id="1a174-107">Then attempt the **Validate Instance**, **Generate Instance**, or **Validate Schema** command again.</span></span>