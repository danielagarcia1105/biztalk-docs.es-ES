---
title: X12 juego de caracteres EDI | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76e7b327-b0bd-4f16-8bfe-6c0184059f2b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bd501c81b92f4fa7824009a949fd6c7e58eaf3b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023106"
---
# <a name="x12-edi-character-set"></a><span data-ttu-id="8bdbb-102">Juego de caracteres X12 de EDI</span><span class="sxs-lookup"><span data-stu-id="8bdbb-102">X12 EDI Character Set</span></span>
<span data-ttu-id="8bdbb-103">Al usar el carácter Ñ o un acento grave (\`), especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8bdbb-103">When using the Ñ character or a grave accent (\`), specify the following:</span></span>  


|                                                                   |                                  <span data-ttu-id="8bdbb-104">Juego de caracteres</span><span class="sxs-lookup"><span data-stu-id="8bdbb-104">Character Set</span></span>                                   |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------|
|             <span data-ttu-id="8bdbb-105">Solo el carácter Ñ en el documento EDI</span><span class="sxs-lookup"><span data-stu-id="8bdbb-105">Only the Ñ character in the EDI document</span></span>              |                            <span data-ttu-id="8bdbb-106">Usar el juego de caracteres ampliado</span><span class="sxs-lookup"><span data-stu-id="8bdbb-106">Use Extended Character Set</span></span>                            |
|           <span data-ttu-id="8bdbb-107">Solo un acento grave (\`) en el documento EDI</span><span class="sxs-lookup"><span data-stu-id="8bdbb-107">Only a grave accent (\`) in the EDI document</span></span>            |                              <span data-ttu-id="8bdbb-108">Usar el juego de caracteres UTF8</span><span class="sxs-lookup"><span data-stu-id="8bdbb-108">Use UTF8 Character Set</span></span>                              |
| <span data-ttu-id="8bdbb-109">El carácter Ñ **y** un acento grave (\`) en el mismo documento:</span><span class="sxs-lookup"><span data-stu-id="8bdbb-109">The Ñ character **and** a grave accent (\`) in the same document:</span></span> | <span data-ttu-id="8bdbb-110">-El documento de entrada debe tener codificación UTF8</span><span class="sxs-lookup"><span data-stu-id="8bdbb-110">-   The inbound document must have UTF8 encoding</span></span><br /><span data-ttu-id="8bdbb-111">-Use el juego de caracteres UTF8</span><span class="sxs-lookup"><span data-stu-id="8bdbb-111">-   Use UTF8 Character Set</span></span> |

 <span data-ttu-id="8bdbb-112">Los siguientes vínculos proporcionan más información sobre los juegos de caracteres EDI:</span><span class="sxs-lookup"><span data-stu-id="8bdbb-112">The following links provider more information on EDI Character Sets:</span></span>  

 [<span data-ttu-id="8bdbb-113">Juegos de caracteres de EDI</span><span class="sxs-lookup"><span data-stu-id="8bdbb-113">EDI Character Sets</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271249)  

 [<span data-ttu-id="8bdbb-114">Compatibilidad de juegos de caracteres de EDI</span><span class="sxs-lookup"><span data-stu-id="8bdbb-114">EDI Character Set Support</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271250)