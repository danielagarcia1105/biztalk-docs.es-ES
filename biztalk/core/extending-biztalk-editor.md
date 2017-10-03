---
title: Extender el Editor de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77c93ab2-0a9b-4c9d-81e5-3871fc8e6e13
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f8e4f574e652420ae11410e52268a199639cf6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="extending-biztalk-editor"></a><span data-ttu-id="83760-102">Extender el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="83760-102">Extending BizTalk Editor</span></span>
<span data-ttu-id="83760-103">El Editor de BizTalk está diseñado para permitir extensiones que sean compatibles con formatos alternativos de mensajes de instancia.</span><span class="sxs-lookup"><span data-stu-id="83760-103">BizTalk Editor is designed to allow extensions that support alternative instance message formats.</span></span> <span data-ttu-id="83760-104">De hecho, el formato XML es el único formato integrado en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="83760-104">In fact, the XML format is the only format that is built into BizTalk Editor.</span></span> <span data-ttu-id="83760-105">Incluso la compatibilidad de los formatos de archivo sin formato, que se incluye en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], está implementada como una extensión del Editor de BizTalk, y sirve por tanto como ejemplo del tipo de funcionalidad que se puede agregar con tales extensiones.</span><span class="sxs-lookup"><span data-stu-id="83760-105">Even support for flat file formats, which is included in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], is implemented as a BizTalk Editor extension, thereby serving as a good example of the type of functionality that can be added by such extensions.</span></span>  
  
 <span data-ttu-id="83760-106">En general, las extensiones del Editor de BizTalk almacenan sus datos personalizados como anotaciones de lenguaje de definición de esquemas XML (XSD) que están asociadas a los elementos XSD correspondientes a los nodos del árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="83760-106">In general, BizTalk Editor extensions persist their custom data as XML Schema definition (XSD) language annotations associated with the XSD elements that correspond to the nodes in the schema tree.</span></span> <span data-ttu-id="83760-107">De nuevo, el amplio conjunto de anotaciones agregadas por la Extensión de archivo sin formato al Editor de BizTalk sirve como ejemplo del modo en el que las extensiones del Editor de BizTalk pueden almacenar sus datos personalizados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="83760-107">Again, the extensive set of annotations added by the Flat File Extension to BizTalk Editor serves as a good example of the way in which BizTalk Editor extensions can persist their custom data in the schema.</span></span>  
  
 <span data-ttu-id="83760-108">Las extensiones del Editor de BizTalk son ensamblados .NET que amplían su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="83760-108">BizTalk Editor extensions are .NET assemblies that extend the functionality of BizTalk Editor.</span></span> <span data-ttu-id="83760-109">Para identificarse como una extensión, un ensamblado debe tener una clase que implementa el **IExtension** de interfaz y deben estar ubicados en la carpeta Developer Tools\Schema Editor Extensions en el directorio de instalación del producto.</span><span class="sxs-lookup"><span data-stu-id="83760-109">To be identified as an extension, an assembly must have one class that implements the **IExtension** interface, and must be located under the Developer Tools\Schema Editor Extensions folder in the product installation directory.</span></span>  
  
 <span data-ttu-id="83760-110">El programador de una extensión debe hacer que el ensamblado haga referencia a la biblioteca Microsoft.BizTalk.SchemaEditor.Extensibility.dll, que contiene la definición de todas las interfaces necesarias para exponer la funcionalidad ampliada en el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="83760-110">The developer of an extension must have its assembly reference the Microsoft.BizTalk.SchemaEditor.Extensibility.dll, which contains the definition of all the interfaces needed for exposing extended functionality to BizTalk Editor.</span></span> <span data-ttu-id="83760-111">Estas interfaces se definen en el **Microsoft.BizTalk.SchemaEditor.Extensibility** espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="83760-111">Those interfaces are defined under the **Microsoft.BizTalk.SchemaEditor.Extensibility** namespace.</span></span>  
  
 <span data-ttu-id="83760-112">El **IExtension** interfaz es el punto de entrada para la extensión, desde el que el Editor de BizTalk, tiene acceso a la funcionalidad extendida, como administradores de propiedades, vistas personalizadas, validación de esquemas, generación de instancias nativas y nativo validación de la instancia.</span><span class="sxs-lookup"><span data-stu-id="83760-112">The **IExtension** interface is the entry point for the extension, from which BizTalk Editor accesses the extended functionality, such as property managers, custom views, schema validation, native instance generation, and native instance validation.</span></span>  
  
 <span data-ttu-id="83760-113">Un esquema determinado puede tener varias extensiones asociadas con él, pero solo una puede establecerse como estándar en un momento dado; Esto se establece en el **estándar** propiedad de la **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="83760-113">A given schema can have multiple extensions associated with it, but only one can be set as the standard at a given time; this is set in the **Standard** property of the **Schema** node.</span></span> <span data-ttu-id="83760-114">La extensión actualmente establecida como estándar es la que se utiliza para la generación y validación de instancias nativas, así como para la validación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="83760-114">The extension currently set as the standard is the one used for native instance generation and validation, and for schema validation.</span></span>  
  
 <span data-ttu-id="83760-115">Las extensiones pueden asociarse con un esquema determinado mediante la edición de la **extensiones de Editor de esquemas** propiedad de la **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="83760-115">Extensions can be associated with a given schema by editing the **Schema Editor Extensions** property of the **Schema** node.</span></span> <span data-ttu-id="83760-116">La información sobre las extensiones asociadas con un esquema se almacena en el propio esquema, en el **anotación** elemento de la **esquema** elemento, como se muestra en el siguiente fragmento XSD.</span><span class="sxs-lookup"><span data-stu-id="83760-116">The information about the extensions associated with a schema is stored in the schema itself, within the **annotation** element of the **schema** element, as illustrated in the following XSD fragment.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema11"  
        xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
        targetNamespace="http://BizTalk_Server_Project1.Schema11"  
        xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
        <xs:appinfo>  
            <schemaEditorExtension:schemaInfo namespaceAlias="b"  
                extensionClass="Microsoft.BizTalk.FlatFileExtension.FlatFileExtension"  
                standardName="Flat File"  
                xmlns:schemaEditorExtension="http://schemas.microsoft.com/BizTalk/2003/SchemaEditorExtensions" />  
            <b:schemaInfo schema_type="document" root_reference="Root"  
                is_receipt="no" schema_name="abc"  
                standard="Flat File"  
                count_positions_by_byte="false" />   
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="Root">  
        ...  
  
```  
  
 <span data-ttu-id="83760-117">Después de crear instancias del objeto de extensión, el marco de trabajo invoca el **inicializar** método de la **IExtension** interfaz, pasa una **ITree** objeto para que la extensión puede acceder a información sobre el árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="83760-117">After instantiating the extension object, the framework invokes the **Initialize** method of the **IExtension** interface, passing an **ITree** object so that the extension can access information about the schema tree.</span></span> <span data-ttu-id="83760-118">Por ejemplo, la extensión podría atravesar todos los nodos secundarios mediante el acceso a la **ITree.RootNode** propiedad.</span><span class="sxs-lookup"><span data-stu-id="83760-118">For example, the extension could traverse all child nodes by accessing the **ITree.RootNode** property.</span></span>  
  
 <span data-ttu-id="83760-119">En esta sección se describen las formas de integrar una extensión del Editor de BizTalk en el entorno del Editor de BizTalk y de enlazarlo a los comandos existentes del mismo.</span><span class="sxs-lookup"><span data-stu-id="83760-119">This section describes the ways in which a BizTalk Editor extension can integrate into the BizTalk Editor environment and hook itself into existing BizTalk Editor commands.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83760-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="83760-120">In This Section</span></span>  
  
-   [<span data-ttu-id="83760-121">Administradores de propiedades</span><span class="sxs-lookup"><span data-stu-id="83760-121">Property Managers</span></span>](../core/property-managers.md)  
  
-   [<span data-ttu-id="83760-122">Vistas personalizadas</span><span class="sxs-lookup"><span data-stu-id="83760-122">Custom Views</span></span>](../core/custom-views.md)  
  
-   [<span data-ttu-id="83760-123">Validación de esquemas</span><span class="sxs-lookup"><span data-stu-id="83760-123">Schema Validation</span></span>](../core/schema-validation1.md)  
  
-   [<span data-ttu-id="83760-124">Validación de instancia</span><span class="sxs-lookup"><span data-stu-id="83760-124">Instance Validation</span></span>](../core/instance-validation.md)  
  
-   [<span data-ttu-id="83760-125">Generación de instancias</span><span class="sxs-lookup"><span data-stu-id="83760-125">Instance Generation</span></span>](../core/instance-generation.md)