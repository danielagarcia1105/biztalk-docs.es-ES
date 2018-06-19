---
title: Cómo crear esquemas para mensajes de archivo sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48f2747b-7f26-4fb2-a855-523e093f3813
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58583037b8fae945dea07aa8af62e969b96e073f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249412"
---
# <a name="create-schemas-for-flat-file-messages"></a><span data-ttu-id="fe850-102">Crear esquemas para mensajes de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="fe850-102">Create Schemas for Flat File Messages</span></span>

## <a name="overview"></a><span data-ttu-id="fe850-103">Información general</span><span class="sxs-lookup"><span data-stu-id="fe850-103">Overview</span></span>
<span data-ttu-id="fe850-104">Después de crear un esquema de mensaje XML como se describe en [crear esquemas para mensajes XML](../core/how-to-create-schemas-for-xml-messages.md), use la **extensiones de Editor de esquemas** propiedad de la **esquema** nodo para habilitar el extensión de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="fe850-104">After creating an XML message schema as described in [Creating Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md), use the **Schema Editor Extensions** property of the **Schema** node to enable the flat file extension.</span></span> <span data-ttu-id="fe850-105">La habilitación de la extensión de archivo sin formato agrega un número considerable de propiedades a muchos de los tipos de nodos de un esquema.</span><span class="sxs-lookup"><span data-stu-id="fe850-105">Enabling the flat file extension adds a considerable number of properties to many of the node types within a schema.</span></span> <span data-ttu-id="fe850-106">Estas propiedades se utilizan normalmente para controlar cómo se traduce un documento empresarial de archivo sin formato a su equivalente XML, o a la inversa, y los valores se almacenan como anotaciones del lenguaje de definición de esquemas XML dentro del archivo de esquema.</span><span class="sxs-lookup"><span data-stu-id="fe850-106">These properties are generally used to control how a flat file business document is translated to and from its equivalent XML business document, and their values are stored as XML Schema definition language (XSD ) annotations within the schema file.</span></span> <span data-ttu-id="fe850-107">Utilizar correctamente estas propiedades requiere algo de práctica y un amplio conocimiento de los aspectos que rigen el formato de los archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="fe850-107">Using these properties properly takes some practice and a thorough understanding of which aspects of the flat file format they each govern.</span></span> 

<span data-ttu-id="fe850-108">Para conceptual y hacer referencia a información acerca de las propiedades de archivo sin formato, consulte [consideraciones al crear mensaje esquemas de archivo plano](../core/considerations-when-creating-flat-file-message-schemas.md) y **propiedades de nodo adicionales para esquemas de archivo sin formato** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="fe850-108">For conceptual and reference information about the flat file properties, see [Considerations When Creating Flat File Message Schemas](../core/considerations-when-creating-flat-file-message-schemas.md) and **Supplemental Node Properties for Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe850-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe850-109">See Also</span></span>  
-  [<span data-ttu-id="fe850-110">Administrar esquemas en proyectos</span><span class="sxs-lookup"><span data-stu-id="fe850-110">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)
-  <span data-ttu-id="fe850-111">Para obtener más información acerca de estas propiedades[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="fe850-111">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>