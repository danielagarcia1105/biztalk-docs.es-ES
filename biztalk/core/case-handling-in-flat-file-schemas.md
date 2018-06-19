---
title: Caso de tratamiento en esquemas de archivo sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f2b56d2-03fa-41e9-ae28-3275b404d4db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2312f00a6dab18fa92c0fed05c5c9fa182d500f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231140"
---
# <a name="case-handling-in-flat-file-schemas"></a><span data-ttu-id="c0f70-102">Caso de control en esquemas de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="c0f70-102">Case Handling in Flat File Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="c0f70-103">Información general</span><span class="sxs-lookup"><span data-stu-id="c0f70-103">Overview</span></span>
<span data-ttu-id="c0f70-104">Puede usar el **caso** propiedad para realizar una conversión de datos de archivo sin formato cuando se traducen desde su formato XML equivalente.</span><span class="sxs-lookup"><span data-stu-id="c0f70-104">You can use the **Case** property to perform case conversion of flat file data when being translated from its equivalent XML format.</span></span> <span data-ttu-id="c0f70-105">Cuando el ensamblador de archivo sin formato traduce un mensaje XML en su formato de archivo sin formato equivalente y el **caso** propiedad está establecida en **mayúsculas** o **minúsculas**, todos los datos regido por el correspondiente esquema se convertirá a mayúsculas o minúsculas, respectivamente, durante la traducción.</span><span class="sxs-lookup"><span data-stu-id="c0f70-105">When the flat file assembler translates an XML message into its equivalent flat file format, and the **Case** property is set to either **Uppercase** or **Lowercase**, all data governed by the corresponding schema will be converted to uppercase or lowercase, respectively, during the translation.</span></span>  
  
 <span data-ttu-id="c0f70-106">Cuando el **caso** propiedad está establecida en **(predeterminado)**, se realiza ninguna conversión de mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="c0f70-106">When the **Case** property is set to **(Default)**, no case conversion is performed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f70-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0f70-107">See Also</span></span>  
 <span data-ttu-id="c0f70-108">**Consideraciones al crear planos esquemas de mensaje de archivo** y **caso (propiedad de nodo de esquemas de archivo sin formato)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c0f70-108">**Considerations When Creating Flat File Message Schemas** and **Case (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>