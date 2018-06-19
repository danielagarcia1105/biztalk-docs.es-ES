---
title: 'Error: error al escribir el archivo Blob de tipo XML (&lt;file:---{0}&gt;). Error: {1} | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb787db4-0919-4e1b-bfe1-ba0e19a08881
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d76ff1a81045d3b764a6a26112a1efd74b284674
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241100"
---
# <a name="error---failure-writing-xml-type-blob-file-ltfile---0gt-error-1"></a><span data-ttu-id="e80ad-103">Error: error al escribir el archivo Blob de tipo XML (&lt;file:---{0}&gt;).</span><span class="sxs-lookup"><span data-stu-id="e80ad-103">Error - Failure writing XML Type Blob file (&lt;file:---{0}&gt;).</span></span> <span data-ttu-id="e80ad-104">Error: {1}</span><span class="sxs-lookup"><span data-stu-id="e80ad-104">Error: {1}</span></span>
<span data-ttu-id="e80ad-105">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="e80ad-105">**Error Code**</span></span>  
  
 <span data-ttu-id="e80ad-106">btm1062</span><span class="sxs-lookup"><span data-stu-id="e80ad-106">btm1062</span></span>  
  
 <span data-ttu-id="e80ad-107">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="e80ad-107">**Explanation**</span></span>  
  
 <span data-ttu-id="e80ad-108">Esto se produce cuando el compilador del asignador no puede crear el archivo blob de tipo xml en la ubicación especificada por la tarea de compilación.</span><span class="sxs-lookup"><span data-stu-id="e80ad-108">This occurs when mapper compiler is not able to create the xml blob file in the location specified by the build task.</span></span>  
  
 <span data-ttu-id="e80ad-109">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="e80ad-109">**User Action**</span></span>  
  
 <span data-ttu-id="e80ad-110">Compruebe el mensaje de error incluido en el mensaje (Error {1})i.</span><span class="sxs-lookup"><span data-stu-id="e80ad-110">Check the error message included in the message (Error {1})i.</span></span> <span data-ttu-id="e80ad-111">Si es una excepción de acceso no autorizado, es posible que no tenga permiso de escritura para la carpeta saliente del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e80ad-111">If it is an UnAuthorised exception, then you may not have write permission for the project output folder.</span></span>