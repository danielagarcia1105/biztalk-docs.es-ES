---
title: Extender el Editor de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77c93ab2-0a9b-4c9d-81e5-3871fc8e6e13
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f8e4f574e652420ae11410e52268a199639cf6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246244"
---
# <a name="extending-biztalk-editor"></a>Extender el Editor de BizTalk
El Editor de BizTalk está diseñado para permitir extensiones que sean compatibles con formatos alternativos de mensajes de instancia. De hecho, el formato XML es el único formato integrado en el Editor de BizTalk. Incluso la compatibilidad de los formatos de archivo sin formato, que se incluye en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], está implementada como una extensión del Editor de BizTalk, y sirve por tanto como ejemplo del tipo de funcionalidad que se puede agregar con tales extensiones.  
  
 En general, las extensiones del Editor de BizTalk almacenan sus datos personalizados como anotaciones de lenguaje de definición de esquemas XML (XSD) que están asociadas a los elementos XSD correspondientes a los nodos del árbol de esquema. De nuevo, el amplio conjunto de anotaciones agregadas por la Extensión de archivo sin formato al Editor de BizTalk sirve como ejemplo del modo en el que las extensiones del Editor de BizTalk pueden almacenar sus datos personalizados en el esquema.  
  
 Las extensiones del Editor de BizTalk son ensamblados .NET que amplían su funcionalidad. Para identificarse como una extensión, un ensamblado debe tener una clase que implementa el **IExtension** de interfaz y deben estar ubicados en la carpeta Developer Tools\Schema Editor Extensions en el directorio de instalación del producto.  
  
 El programador de una extensión debe hacer que el ensamblado haga referencia a la biblioteca Microsoft.BizTalk.SchemaEditor.Extensibility.dll, que contiene la definición de todas las interfaces necesarias para exponer la funcionalidad ampliada en el Editor de BizTalk. Estas interfaces se definen en el **Microsoft.BizTalk.SchemaEditor.Extensibility** espacio de nombres.  
  
 El **IExtension** interfaz es el punto de entrada para la extensión, desde el que el Editor de BizTalk, tiene acceso a la funcionalidad extendida, como administradores de propiedades, vistas personalizadas, validación de esquemas, generación de instancias nativas y nativo validación de la instancia.  
  
 Un esquema determinado puede tener varias extensiones asociadas con él, pero solo una puede establecerse como estándar en un momento dado; Esto se establece en el **estándar** propiedad de la **esquema** nodo. La extensión actualmente establecida como estándar es la que se utiliza para la generación y validación de instancias nativas, así como para la validación de esquemas.  
  
 Las extensiones pueden asociarse con un esquema determinado mediante la edición de la **extensiones de Editor de esquemas** propiedad de la **esquema** nodo. La información sobre las extensiones asociadas con un esquema se almacena en el propio esquema, en el **anotación** elemento de la **esquema** elemento, como se muestra en el siguiente fragmento XSD.  
  
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
  
 Después de crear instancias del objeto de extensión, el marco de trabajo invoca el **inicializar** método de la **IExtension** interfaz, pasa una **ITree** objeto para que la extensión puede acceder a información sobre el árbol de esquema. Por ejemplo, la extensión podría atravesar todos los nodos secundarios mediante el acceso a la **ITree.RootNode** propiedad.  
  
 En esta sección se describen las formas de integrar una extensión del Editor de BizTalk en el entorno del Editor de BizTalk y de enlazarlo a los comandos existentes del mismo.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Administradores de propiedades](../core/property-managers.md)  
  
-   [Vistas personalizadas](../core/custom-views.md)  
  
-   [Validación de esquemas](../core/schema-validation1.md)  
  
-   [Validación de instancia](../core/instance-validation.md)  
  
-   [Generación de instancias](../core/instance-generation.md)