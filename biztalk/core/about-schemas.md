---
title: Acerca de los esquemas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ec2b79c-7cfe-4b00-bcff-dfad3944c83b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a452675cb11b13ae83f940ce10b09c72a622dc8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224228"
---
# <a name="about-schemas"></a><span data-ttu-id="64cd3-102">Acerca de los esquemas</span><span class="sxs-lookup"><span data-stu-id="64cd3-102">About Schemas</span></span>
<span data-ttu-id="64cd3-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el lenguaje de definición de esquemas XML (XSD) para definir la estructura de todos los mensajes que procesa y hace referencia a estas definiciones de estructura de los mensajes como esquemas.</span><span class="sxs-lookup"><span data-stu-id="64cd3-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the XML Schema definition (XSD) language to define the structure of all messages that it processes, and refers to these definitions of message structure as schemas.</span></span> <span data-ttu-id="64cd3-104">Salvo contadas excepciones, los mensajes estructurados son la base de cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="64cd3-104">With few exceptions, structured messages are the core of any application.</span></span> <span data-ttu-id="64cd3-105">Estos mensajes estructurados pueden adoptar cualquier forma, ser grandes o pequeños, y dirigirse a un amplio conjunto de sistemas de servidor y almacenes de datos.</span><span class="sxs-lookup"><span data-stu-id="64cd3-105">These structured messages can take any form, large or small, and target a wide array of back-end systems and data stores.</span></span> <span data-ttu-id="64cd3-106">Los sistemas que crean y consumen mensajes estructurados a menudo usan distintos formatos.</span><span class="sxs-lookup"><span data-stu-id="64cd3-106">Systems that create and consume the structured messages frequently use different formats.</span></span> <span data-ttu-id="64cd3-107">Dos de los formatos más comunes en los mensajes estructurados son XML y archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="64cd3-107">Two of the most common formats for structured messages are XML and flat files.</span></span>  
  
 <span data-ttu-id="64cd3-108">El Editor de BizTalk se ha diseñado para simplificar el proceso de definir un esquema de mensaje y validar si un mensaje concreto se ajusta a ese esquema.</span><span class="sxs-lookup"><span data-stu-id="64cd3-108">BizTalk Editor is designed to simplify the process of defining a message schema and validating whether a particular message conforms to that schema.</span></span> <span data-ttu-id="64cd3-109">Durante el proceso de definición de los esquemas y validación de los mensajes, probablemente realizará algunas de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="64cd3-109">In the process of defining schemas and validating messages, you will likely perform some of the following tasks:</span></span>  
  
-   <span data-ttu-id="64cd3-110">Crear esquemas para mensajes XML estructurados</span><span class="sxs-lookup"><span data-stu-id="64cd3-110">Create schemas for structured XML messages.</span></span>  
  
-   <span data-ttu-id="64cd3-111">Crear esquemas para mensajes de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="64cd3-111">Create schemas for flat file messages.</span></span>  
  
-   <span data-ttu-id="64cd3-112">Generar esquemas a partir de datos de instancias XML con formato correcto</span><span class="sxs-lookup"><span data-stu-id="64cd3-112">Generate schemas from well-formed XML instance data.</span></span>  
  
-   <span data-ttu-id="64cd3-113">Validar que un mensaje se ajusta a un esquema específico</span><span class="sxs-lookup"><span data-stu-id="64cd3-113">Validate message conformance to a specific schema.</span></span>  
  
-   <span data-ttu-id="64cd3-114">Realizar la validación de esquemas en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="64cd3-114">Perform design-time validation of schemas.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="64cd3-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="64cd3-115">In This Section</span></span>  
  
-   [<span data-ttu-id="64cd3-116">Diferentes tipos de esquemas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="64cd3-116">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)  
  
-   [<span data-ttu-id="64cd3-117">Rol de XSD</span><span class="sxs-lookup"><span data-stu-id="64cd3-117">Role of XSD</span></span>](../core/role-of-xsd.md)  
  
-   [<span data-ttu-id="64cd3-118">Recursos XSD en Internet</span><span class="sxs-lookup"><span data-stu-id="64cd3-118">XSD Resources on the Web</span></span>](../core/xsd-resources-on-the-web.md)  
  
-   [<span data-ttu-id="64cd3-119">Representación de esquemas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="64cd3-119">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)  
  
-   [<span data-ttu-id="64cd3-120">Esquemas que usan otros esquemas</span><span class="sxs-lookup"><span data-stu-id="64cd3-120">Schemas That Use Other Schemas</span></span>](../core/schemas-that-use-other-schemas.md)  
  
-   [<span data-ttu-id="64cd3-121">Tipo reutilización y derivaciones</span><span class="sxs-lookup"><span data-stu-id="64cd3-121">Type Reuse and Derivations</span></span>](../core/type-reuse-and-derivations.md)  
  
-   [<span data-ttu-id="64cd3-122">Migración de esquema desde versiones anteriores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="64cd3-122">Schema Migration from Previous Versions of BizTalk Server</span></span>](../core/schema-migration-from-previous-versions-of-biztalk-server.md)  
  
-   [<span data-ttu-id="64cd3-123">Formas de usar el contenido de mensaje para el procesamiento de mensajes de Control</span><span class="sxs-lookup"><span data-stu-id="64cd3-123">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)  
  
-   [<span data-ttu-id="64cd3-124">Validación de esquema en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="64cd3-124">Schema Validation in Visual Studio</span></span>](../core/schema-validation-in-visual-studio.md)  
  
-   [<span data-ttu-id="64cd3-125">Validación y generación de mensajes de instancia</span><span class="sxs-lookup"><span data-stu-id="64cd3-125">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)