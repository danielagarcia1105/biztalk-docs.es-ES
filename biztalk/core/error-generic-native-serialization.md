---
title: 'Error: serialización nativa genérica | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericNativeSerialize
ms.assetid: 3728727d-7d99-432d-844e-c956cc4635e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d2eacfae17d72dbb17786a1d924cfdf14be20ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241004"
---
# <a name="error---generic-native-serialization"></a><span data-ttu-id="790e7-102">Error: serialización nativa genérica</span><span class="sxs-lookup"><span data-stu-id="790e7-102">Error - Generic Native Serialization</span></span>
<span data-ttu-id="790e7-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="790e7-103">**Error Code**</span></span>  
  
 <span data-ttu-id="790e7-104">btm1049</span><span class="sxs-lookup"><span data-stu-id="790e7-104">btm1049</span></span>  
  
 <span data-ttu-id="790e7-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="790e7-105">**Explanation**</span></span>  
  
 <span data-ttu-id="790e7-106">El mensaje de instancia de salida XML generado por la transformación que especificó la asignación no se pudo convertir al formato nativo especificado por el esquema de destino debido a un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="790e7-106">The XML output instance message produced by the transformation specified by the map could not be converted to the native format specified by the destination schema due to an unspecified error.</span></span>  
  
 <span data-ttu-id="790e7-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="790e7-107">**User Action**</span></span>  
  
 <span data-ttu-id="790e7-108">Abra el esquema de destino en el Editor de BizTalk y utilice la **Validar esquema**, **Validar instancia**, y **generar instancia** comandos, que aparecen cuando hace clic en un esquema en el Explorador de soluciones, para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="790e7-108">Open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, to isolate the problem.</span></span>