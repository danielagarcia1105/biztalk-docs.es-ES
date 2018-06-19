---
title: Mediante el análisis y serialización motores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parsing engine
- pipeline components [custom], engines
- serialization engine
- pipeline components [custom], assembling
- pipeline components [custom], parsing
ms.assetid: a9d19703-b074-402a-971a-b2a6cd5d0724
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e820b2dce1257ec948aa214c9fdf1d43a6a7152
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287684"
---
# <a name="using-the-parsing-and-serializing-engines"></a><span data-ttu-id="a7202-102">Utilizar los motores de análisis y serialización</span><span class="sxs-lookup"><span data-stu-id="a7202-102">Using the Parsing and Serializing Engines</span></span>
<span data-ttu-id="a7202-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye un análisis y motor para simplificar el proceso de análisis y serialización de documentos de archivos sin formato de serialización.</span><span class="sxs-lookup"><span data-stu-id="a7202-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes a parsing and serializing engine to simplify the process of parsing and serializing flat file documents.</span></span>  
  
 <span data-ttu-id="a7202-104">El motor de análisis es un marco de trabajo controlado por esquemas que puede analizar muy diferentes formatos de documentos en XML.</span><span class="sxs-lookup"><span data-stu-id="a7202-104">The parsing engine is a schema-driven framework that can parse many different document formats into XML.</span></span> <span data-ttu-id="a7202-105">Además, el motor dispone de un modelo de extensibilidad bien definido para facilitar aún más el análisis de los formatos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a7202-105">In addition, the engine has a well-defined extensibility model to make parsing custom formats even easier.</span></span>  
  
 <span data-ttu-id="a7202-106">Para análisis complejos se usan desensambladores.</span><span class="sxs-lookup"><span data-stu-id="a7202-106">For complex parsing, disassemblers are used.</span></span> <span data-ttu-id="a7202-107">Además de convertir el formato nativo en XML, el desensamblador también puede separar un solo documento en múltiples documentos.</span><span class="sxs-lookup"><span data-stu-id="a7202-107">In addition to converting the native format to XML, the disassembler can also separate a single document into multiple documents.</span></span>  
  
 <span data-ttu-id="a7202-108">El motor de serialización es similar al de análisis, pero trabaja en sentido opuesto.</span><span class="sxs-lookup"><span data-stu-id="a7202-108">The serializing engine is similar to the parsing engine, except that it works in the opposite direction.</span></span> <span data-ttu-id="a7202-109">Mientras que el motor de análisis convierte formatos nativos en XML, el motor de serialización convierte XML en formatos nativos.</span><span class="sxs-lookup"><span data-stu-id="a7202-109">Where the parsing engine converts native formats to XML, the serializing engine converts XML to native formats.</span></span> <span data-ttu-id="a7202-110">Y del mismo modo que el motor de análisis usa desensambladores, el motor de serialización usa ensambladores.</span><span class="sxs-lookup"><span data-stu-id="a7202-110">And just as the parsing engine uses disassemblers, the serializing engine uses assemblers.</span></span>  
  
 <span data-ttu-id="a7202-111">En esta sección se explica cómo llevar a cabo el análisis, la serialización y la codificación de caracteres según esquemas en lenguaje de definición de esquemas XML (XSD) y a efectuar otras tareas comunes mediante las API del motor de análisis y del motor de serialización.</span><span class="sxs-lookup"><span data-stu-id="a7202-111">This section discusses how to perform character encoding, parse and serialize based on XML Schema definition language (XSD) schemas, and perform other common tasks using the parsing engine and serializing engine APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7202-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a7202-112">In This Section</span></span>  
  
-   [<span data-ttu-id="a7202-113">Implementación de codificación de caracteres en un componente de canalización</span><span class="sxs-lookup"><span data-stu-id="a7202-113">Implementing Character Encoding in a Pipeline Component</span></span>](../core/implementing-character-encoding-in-a-pipeline-component.md)  
  
-   [<span data-ttu-id="a7202-114">Uso de esquemas</span><span class="sxs-lookup"><span data-stu-id="a7202-114">Using Schemas</span></span>](../core/using-schemas.md)  
  
-   [<span data-ttu-id="a7202-115">Usar el motor de análisis de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="a7202-115">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)  
  
-   [<span data-ttu-id="a7202-116">Usar el motor de serialización de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="a7202-116">Using the Flat File Serializing Engine</span></span>](../core/using-the-flat-file-serializing-engine.md)