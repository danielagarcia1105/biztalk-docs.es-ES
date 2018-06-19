---
title: Componente de canalización de ensamblador XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: 3adfd603-0577-49c2-ae9d-445d62fed385
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22348b61ca32567190fa99e103fe536f5199af58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289492"
---
# <a name="xml-assembler-pipeline-component"></a><span data-ttu-id="776be-102">Componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="776be-102">XML Assembler Pipeline Component</span></span>
<span data-ttu-id="776be-103">El componente de canalización de ensamblador XML combina la serialización y el ensamblado XML en un componente.</span><span class="sxs-lookup"><span data-stu-id="776be-103">The XML Assembler pipeline component combines XML serializing and assembling in one component.</span></span> <span data-ttu-id="776be-104">Su primera función es transferir propiedades del contexto del mensaje de vuelta a los sobres y documentos.</span><span class="sxs-lookup"><span data-stu-id="776be-104">Its primary function is to transfer properties from the message context back into envelopes and documents.</span></span>  
  
 <span data-ttu-id="776be-105">Las siguientes acciones tienen lugar en el componente de ensamblador XML después de recibir un lote de mensajes para formar un intercambio:</span><span class="sxs-lookup"><span data-stu-id="776be-105">The following actions occur in the XML Assembler component after receiving a batch of messages to form an interchange:</span></span>  
  
1.  <span data-ttu-id="776be-106">El ensamblador crea el sobre mediante la especificación de sobre definida.</span><span class="sxs-lookup"><span data-stu-id="776be-106">The assembler creates the envelope by using the specified envelope specification.</span></span>  
  
2.  <span data-ttu-id="776be-107">El componente coloca las propiedades del contenido en las instancias de mensaje mediante los XPaths predefinidos, codificados como anotaciones en los esquemas XSD asociados al mensaje.</span><span class="sxs-lookup"><span data-stu-id="776be-107">The component puts the content properties on the message instances by using the predefined XPaths coded as annotations in the XSD schemas associated with the message.</span></span>  
  
3.  <span data-ttu-id="776be-108">El componente anexa el mensaje al sobre.</span><span class="sxs-lookup"><span data-stu-id="776be-108">The component appends the message to the envelope.</span></span>  
  
4.  <span data-ttu-id="776be-109">El componente coloca las propiedades del contenido en el sobre mediante los XPaths predefinidos, codificados como anotaciones en los esquemas XSD asociados a los sobres.</span><span class="sxs-lookup"><span data-stu-id="776be-109">The component puts the content properties on the envelope by using the predefined XPaths coded as annotations in the XSD schemas associated with envelopes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="776be-110">El componente de canalización de ensamblador XML no llena los campos de atributos que faltan, pero llena los campos de elementos vacíos cuando los campos son opcionales pero no tienen valores predeterminados o fijos.</span><span class="sxs-lookup"><span data-stu-id="776be-110">The XML Assembler pipeline component does not populate missing attribute fields, but does populate empty element fields when the fields are optional but do not have default or fixed values.</span></span>  
  
 <span data-ttu-id="776be-111">Para obtener información acerca de cómo configurar el componente de canalización de ensamblador XML, vea [cómo configurar el componente de canalización de ensamblador XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md).</span><span class="sxs-lookup"><span data-stu-id="776be-111">For information about configuring the XML Assembler pipeline component, see [How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="776be-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="776be-112">In This Section</span></span>  
  
-   [<span data-ttu-id="776be-113">Codificación de caracteres en el componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="776be-113">Character Encoding in the XML Assembler Pipeline Component</span></span>](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="776be-114">Instrucciones de procesamiento en el componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="776be-114">Processing Instructions in the XML Assembler Pipeline Component</span></span>](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="776be-115">Mensajes desconocidos en el componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="776be-115">Unrecognized Messages in the XML Assembler Pipeline Component</span></span>](../core/unrecognized-messages-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="776be-116">Elementos Set de información XML en el componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="776be-116">XML Information Set Elements in the XML Assembler Pipeline Component</span></span>](../core/xml-information-set-elements-in-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="776be-117">Obligatoriedad de estructura del documento en el componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="776be-117">Document Structure Enforcement in the XML Assembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-xml-assembler-pipeline-component.md)