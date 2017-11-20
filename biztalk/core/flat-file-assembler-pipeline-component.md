---
title: "Componente de canalización de ensamblador de archivos planos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component]
ms.assetid: 3c851771-55b2-4d21-9291-d707dd66837c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385b1f8ea6c2ce707069cde522ea2f6712290be7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-assembler-pipeline-component"></a><span data-ttu-id="5ec7b-102">Componente de canalización de ensamblador de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="5ec7b-102">Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="5ec7b-103">Un ensamblador de archivo sin formato combina documentos individuales en un lote y, opcionalmente, le agrega un encabezado o finalizador (o ambos).</span><span class="sxs-lookup"><span data-stu-id="5ec7b-103">A Flat File Assembler combines individual documents into a batch and optionally adds a header or trailer (or both) to it.</span></span> <span data-ttu-id="5ec7b-104">Para obtener más información acerca de los archivos sin formato, vea [mensajes de archivo sin formato con registros delimitados](../core/flat-file-messages-with-delimited-records.md).</span><span class="sxs-lookup"><span data-stu-id="5ec7b-104">For more information about flat files, see [Flat File Messages with Delimited Records](../core/flat-file-messages-with-delimited-records.md).</span></span> <span data-ttu-id="5ec7b-105">Consulte también [mensajes de archivo sin formato con registros posicionales](../core/flat-file-messages-with-positional-records.md).</span><span class="sxs-lookup"><span data-stu-id="5ec7b-105">Also see [Flat File Messages with Positional Records](../core/flat-file-messages-with-positional-records.md).</span></span>  
  
 <span data-ttu-id="5ec7b-106">El componente de canalización de ensamblador de archivo sin formato no valida el mensaje XML entrante.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-106">The Flat File Assembler pipeline component does not validate the incoming XML message.</span></span> <span data-ttu-id="5ec7b-107">Para garantizar la validación XML, incluya el componente de validador XML en la fase de preensamblado de la canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-107">To ensure XML validation, include the XML Validator component in the Pre-Assemble stage of the send pipeline.</span></span>  
  
 <span data-ttu-id="5ec7b-108">El componente de canalización de ensamblador de archivo sin formato solo admite conversiones que admita Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-108">The Flat File Assembler pipeline component only supports conversions supported by the Microsoft .NET Framework.</span></span> <span data-ttu-id="5ec7b-109">Cualquier conversión adicional puede hacerse escribiendo en un escritor de texto personalizado.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-109">Any additional conversion can be done by writing to a custom text writer.</span></span>  
  
 <span data-ttu-id="5ec7b-110">Para obtener información acerca de cómo configurar el componente de canalización de ensamblador de archivo sin formato, vea [cómo configurar el componente de canalización de ensamblador de archivo sin formato](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="5ec7b-110">For information about configuring the Flat File Assembler pipeline component, see [How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ec7b-111">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], no puede ensamblar mensajes en un intercambio.</span><span class="sxs-lookup"><span data-stu-id="5ec7b-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you cannot assemble messages into one interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ec7b-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5ec7b-112">In This Section</span></span>  
  
-   [<span data-ttu-id="5ec7b-113">Codificación de caracteres en el componente de canalización de ensamblador de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="5ec7b-113">Character Encoding in the Flat File Assembler Pipeline Component</span></span>](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="5ec7b-114">Obligatoriedad de estructura del documento en el componente de canalización de ensamblador de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="5ec7b-114">Document Structure Enforcement in the Flat File Assembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="5ec7b-115">Conservar delimitadores en el componente de canalización de ensamblador de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="5ec7b-115">Retaining Delimiters in the Flat File Assembler Pipeline Component</span></span>](../core/retaining-delimiters-in-the-flat-file-assembler-pipeline-component.md)