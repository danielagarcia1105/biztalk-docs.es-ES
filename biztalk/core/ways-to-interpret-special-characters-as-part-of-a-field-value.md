---
title: Formas de interpretar los caracteres especiales como parte de un valor de campo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e19a202-4e4d-42e0-ba1e-fddc52792b21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b96a3c7502a47541e8e58ec3df3eccf6098e3abc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288388"
---
# <a name="ways-to-interpret-special-characters-as-part-of-a-field-value"></a><span data-ttu-id="437e1-102">Formas de interpretar los caracteres especiales como parte de un valor de campo</span><span class="sxs-lookup"><span data-stu-id="437e1-102">Ways to Interpret Special Characters as Part of a Field Value</span></span>
<span data-ttu-id="437e1-103">Los campos de los registros posicionales y delimitados pueden contener caracteres especiales de distintos tipos, como caracteres controlador, de ajuste y de escape.</span><span class="sxs-lookup"><span data-stu-id="437e1-103">Fields in both positional and delimited records can contain special characters of different types, such as pad, wrap, and escape characters.</span></span> <span data-ttu-id="437e1-104">Los registros delimitados también pueden tener uno o más caracteres de delimitador distintos para separar los campos de un registro o un registro de otro.</span><span class="sxs-lookup"><span data-stu-id="437e1-104">Delimited records can also contain one or more different delimiter characters that are used to separate the fields within a record and one record from another record.</span></span> <span data-ttu-id="437e1-105">Estos caracteres especiales a veces forman parte de los propios datos, en cuyo caso no deben interpretarse como especiales.</span><span class="sxs-lookup"><span data-stu-id="437e1-105">Sometimes these special characters are part of the data itself, and are not meant to be interpreted as special in those cases.</span></span>  
  
 <span data-ttu-id="437e1-106">Los esquemas de archivo sin formato usados por Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite dos técnicas distintas para marcar los casos de especial en caso contrario caracteres simplemente como parte de los datos contenidos en un campo.</span><span class="sxs-lookup"><span data-stu-id="437e1-106">The flat file schemas used by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] support two different techniques for flagging occurrences of otherwise special characters as simply part of the data contained by a field.</span></span> <span data-ttu-id="437e1-107">Estas dos técnicas se basan en el uso de caracteres de escape y de ajuste.</span><span class="sxs-lookup"><span data-stu-id="437e1-107">These two techniques employ escape characters and wrap characters, respectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="437e1-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="437e1-108">In This Section</span></span>  
  
-   [<span data-ttu-id="437e1-109">Caracteres de escape</span><span class="sxs-lookup"><span data-stu-id="437e1-109">Escape Characters</span></span>](../core/escape-characters.md)  
  
-   [<span data-ttu-id="437e1-110">Ajustar caracteres</span><span class="sxs-lookup"><span data-stu-id="437e1-110">Wrap Characters</span></span>](../core/wrap-characters.md)