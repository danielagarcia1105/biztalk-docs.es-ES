---
title: "Configurar componentes de canalización nativos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, pipeline components
- pipeline components, configuring
- Pipeline Designer, code sample
- IPersistPropertyBag interface
ms.assetid: a3332a60-8cd6-43fa-9ecf-e1e54e71fef7
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94475334395f8c360bbb636cfa9cbadcf3bf4fe3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-native-pipeline-components"></a><span data-ttu-id="4be27-102">Configurar componentes de canalización nativos</span><span class="sxs-lookup"><span data-stu-id="4be27-102">Configuring Native Pipeline Components</span></span>
<span data-ttu-id="4be27-103">Los componentes de canalización pueden exponer sus propiedades personalizadas en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="4be27-103">Pipeline components can expose their own custom properties at design time.</span></span> <span data-ttu-id="4be27-104">Cualquier propiedad pública definida en el componente se procesará en el Diseñador de canalizaciones siempre que los descriptores de acceso de lectura y escritura para esta propiedad estén implementados.</span><span class="sxs-lookup"><span data-stu-id="4be27-104">Any public property defined in the component will be rendered in Pipeline Designer providing that read and write accessors for that property are implemented.</span></span> <span data-ttu-id="4be27-105">El Diseñador de canalizaciones mostrará las propiedades del componente según su declaración; por ejemplo, si la propiedad se declara como de solo lectura, se mostrará como tal en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="4be27-105">Pipeline Designer will display the component properties in accordance with their declaration; for example, if the property is declared as read-only, it will be displayed as such in Pipeline Designer.</span></span>  
  
 <span data-ttu-id="4be27-106">Componentes de canalización personalizado deben implementar la **IPersistPropertyBag** interfaz para habilitar la creación de estas propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="4be27-106">Custom pipeline components must implement the **IPersistPropertyBag** interface to enable the creation of these custom properties.</span></span> <span data-ttu-id="4be27-107">Las propiedades creadas con la **IPersistPropertyBag** interfaz se puede establecer en la ventana Propiedades de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], igual que todas las propiedades de los componentes de canalización nativos.</span><span class="sxs-lookup"><span data-stu-id="4be27-107">Properties created with the **IPersistPropertyBag** interface can be set in the Properties window of Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], just like all the properties of the native pipeline components.</span></span> <span data-ttu-id="4be27-108">Esta sección contiene procedimientos para configurar todos los componentes de canalización incluidos.</span><span class="sxs-lookup"><span data-stu-id="4be27-108">This section contains procedures for configuring each of the included pipeline components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4be27-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4be27-109">In This Section</span></span>  
  
-   [<span data-ttu-id="4be27-110">Cómo configurar los componentes de canalización nativos</span><span class="sxs-lookup"><span data-stu-id="4be27-110">How to Configure Native Pipeline Components</span></span>](../core/how-to-configure-native-pipeline-components.md)  
  
-   [<span data-ttu-id="4be27-111">Cómo configurar el componente de canalización de ensamblador de BizTalk Framework</span><span class="sxs-lookup"><span data-stu-id="4be27-111">How to Configure the BizTalk Framework Assembler Pipeline Component</span></span>](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="4be27-112">Cómo configurar el componente de canalización de desensamblador de BizTalk Framework</span><span class="sxs-lookup"><span data-stu-id="4be27-112">How to Configure the BizTalk Framework Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="4be27-113">Propiedades y esquema de BizTalk Framework</span><span class="sxs-lookup"><span data-stu-id="4be27-113">BizTalk Framework Schema and Properties</span></span>](../core/biztalk-framework-schema-and-properties.md)  
  
-   [<span data-ttu-id="4be27-114">Cómo configurar el componente de canalización de ensamblador de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="4be27-114">How to Configure the Flat File Assembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="4be27-115">Cómo configurar el componente de canalización de desensamblador de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="4be27-115">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="4be27-116">Cómo configurar el componente de canalización de descodificador de MIME-SMIME</span><span class="sxs-lookup"><span data-stu-id="4be27-116">How to Configure the MIME-SMIME Decoder Pipeline Component</span></span>](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)  
  
-   [<span data-ttu-id="4be27-117">Cómo configurar el componente de canalización de codificador de MIME/SMIME</span><span class="sxs-lookup"><span data-stu-id="4be27-117">How to Configure the MIME-SMIME Encoder Pipeline Component</span></span>](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)  
  
-   [<span data-ttu-id="4be27-118">Propiedades y esquema de propiedades de MIME-SMIME</span><span class="sxs-lookup"><span data-stu-id="4be27-118">MIME-SMIME Property Schema and Properties</span></span>](../core/mime-smime-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="4be27-119">Cómo configurar el componente de canalización de resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="4be27-119">How to Configure the Party Resolution Pipeline Component</span></span>](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
  
-   [<span data-ttu-id="4be27-120">Cómo configurar el componente de canalización de ensamblador XML</span><span class="sxs-lookup"><span data-stu-id="4be27-120">How to Configure the XML Assembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="4be27-121">Cómo configurar el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="4be27-121">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="4be27-122">Propiedades y esquema de propiedad de archivo sin formato y XML</span><span class="sxs-lookup"><span data-stu-id="4be27-122">XML and Flat File Property Schema and Properties</span></span>](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="4be27-123">Cómo configurar el componente de canalización de validador XML</span><span class="sxs-lookup"><span data-stu-id="4be27-123">How to Configure the XML Validator Pipeline Component</span></span>](../core/how-to-configure-the-xml-validator-pipeline-component.md)