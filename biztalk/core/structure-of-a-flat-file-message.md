---
title: Estructura de un mensaje de archivo sin formato | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00f2adf6-a47c-498b-b5ae-c6bd55bafceb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: badb8aacf6f2ed8ce9e38f1ea6bbe432a1d3b89e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="structure-of-a-flat-file-message"></a><span data-ttu-id="691ba-102">Estructura de un mensaje de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="691ba-102">Structure of a Flat File Message</span></span>
<span data-ttu-id="691ba-103">En el contexto de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], un mensaje de instancia de archivo sin formato es un archivo de texto que puede contener tres partes lógicas: un encabezado, un cuerpo y un finalizador, en ese orden.</span><span class="sxs-lookup"><span data-stu-id="691ba-103">In the context of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a flat file instance message is a text file that can contain three logical parts: a header, a body, and a trailer, in that order.</span></span> <span data-ttu-id="691ba-104">Tanto el encabezado como el finalizador son opcionales.</span><span class="sxs-lookup"><span data-stu-id="691ba-104">Both the header and the trailer are optional.</span></span> <span data-ttu-id="691ba-105">En el siguiente ejemplo se muestra un mensaje de instancia de archivo sin formato formado por tres partes, donde el cuerpo aparece en negrita.</span><span class="sxs-lookup"><span data-stu-id="691ba-105">The following example shows a flat file instance message that consists of all three parts, with the body shown in bold type.</span></span>  
  
```  
Microsoft Corporation  
One Microsoft Way  
Redmond, WA 98033  
  
TRANSACTION-1111,1  
  
```  
  
 <span data-ttu-id="691ba-106">Para que el desensamblador de archivos sin formato distinga correctamente el encabezado, el cuerpo y el finalizador de un mensaje de instancia de archivo sin formato, es necesario crear y configurar un esquema independiente para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="691ba-106">For the flat file disassembler to correctly distinguish the header, the body, and the trailer of a flat file instance message, you must create and configure a separate schema for each of them.</span></span>  
  
 <span data-ttu-id="691ba-107">Dentro de una parte concreta de un mensaje de instancia de archivo sin formato, los distintos elementos de datos se agrupan en registros, que pueden contener subregistros y, en última instancia, los elementos individuales de datos a los que se conoce como campos.</span><span class="sxs-lookup"><span data-stu-id="691ba-107">Within a particular part of a flat file instance message, different items of data are grouped into records, which themselves can contain subrecords and ultimately the individual items of data, known as fields.</span></span> <span data-ttu-id="691ba-108">Estos registros y campos se distinguen unos de otros mediante dos metodologías básicas.</span><span class="sxs-lookup"><span data-stu-id="691ba-108">These records and fields are distinguished from each other using one of two different basic methodologies.</span></span> <span data-ttu-id="691ba-109">La primera metodología, conocida como posicional, define cada elemento de datos para que tenga una longitud preestablecida; se utilizan caracteres controladores para que los elementos de datos más cortos tengan la longitud esperada.</span><span class="sxs-lookup"><span data-stu-id="691ba-109">The first methodology, known as positional, defines each item of data to be of a pre-established length, with pad characters being used to bring a shorter item of data up to its expected length.</span></span> <span data-ttu-id="691ba-110">La segunda metodología, conocida como delimitada, utiliza uno o varios caracteres especiales para separar los elementos de datos entre sí.</span><span class="sxs-lookup"><span data-stu-id="691ba-110">The second methodology, known as delimited, uses one or more special characters to separate items of data from each other.</span></span> <span data-ttu-id="691ba-111">Esta metodología evita tener que usar caracteres controladores superfluos que de otro modo son necesarios, pero requiere que se tengan en cuenta una serie de cuestiones especiales cuando los propios datos contienen el carácter o la secuencia de caracteres utilizados como delimitador.</span><span class="sxs-lookup"><span data-stu-id="691ba-111">This methodology avoids the need for otherwise superfluous pad characters, but introduces some special considerations when the data itself contains the character or sequence of characters being used as a delimiter.</span></span>  
  
 <span data-ttu-id="691ba-112">En el resto de la sección se ofrece información general avanzada acerca de cómo BizTalk Server trata los encabezados, los cuerpos y los finalizadores de los mensajes de instancias de archivo sin formato y, en concreto, cómo decide si las partes opcionales están presentes y cómo separa las partes de los mensajes entrantes de instancias de archivo sin formato y las combina.</span><span class="sxs-lookup"><span data-stu-id="691ba-112">The remainder of this section provides a high-level overview of how BizTalk Server handles headers, bodies, and trailers in flat file instance messages, and specifically, how it decides whether the optional parts are present, and how it separates the parts of inbound flat file instance messages and combines the parts of outbound flat file instance messages.</span></span> <span data-ttu-id="691ba-113">También contiene información adicional acerca de las diferencias entre los mensajes de instancia de archivo sin formato que utilizan registros y campos posicionales y los que emplean registros y campos delimitados.</span><span class="sxs-lookup"><span data-stu-id="691ba-113">This section also provides additional information about the differences between flat file instance messages that employ positional records and fields and flat file instance messages that employ delimited records and fields.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="691ba-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="691ba-114">In This Section</span></span>  
  
-   [<span data-ttu-id="691ba-115">Encabezados de mensaje de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="691ba-115">Flat File Message Headers</span></span>](../core/flat-file-message-headers.md)  
  
-   [<span data-ttu-id="691ba-116">Cuerpos de mensaje de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="691ba-116">Flat File Message Bodies</span></span>](../core/flat-file-message-bodies.md)  
  
-   [<span data-ttu-id="691ba-117">Finalizadores de mensaje de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="691ba-117">Flat File Message Trailers</span></span>](../core/flat-file-message-trailers.md)  
  
-   [<span data-ttu-id="691ba-118">Mensajes de archivo sin formato con registros posicionales</span><span class="sxs-lookup"><span data-stu-id="691ba-118">Flat File Messages with Positional Records</span></span>](../core/flat-file-messages-with-positional-records.md)  
  
-   [<span data-ttu-id="691ba-119">Mensajes de archivo sin formato con registros delimitados</span><span class="sxs-lookup"><span data-stu-id="691ba-119">Flat File Messages with Delimited Records</span></span>](../core/flat-file-messages-with-delimited-records.md)  
  
-   [<span data-ttu-id="691ba-120">Migrar registros de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="691ba-120">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)