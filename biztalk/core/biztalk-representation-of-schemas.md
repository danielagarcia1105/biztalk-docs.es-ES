---
title: Representación de esquemas de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0460a37-1f4f-4c0b-91db-bb457f434fe9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0951a0191a0cd6bf4d1d14c9c3aed19890004d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978429"
---
# <a name="biztalk-representation-of-schemas"></a>Representación de esquemas en BizTalk

## <a name="overview"></a>Información general
Aunque los esquemas de BizTalk se representan y almacenan en última instancia en el lenguaje de definición de esquemas XML (XSD), se representan en forma de jerarquía gráfica de nodos al trabajar en el Editor de BizTalk. La parte superior de la jerarquía siempre es el **\<esquema\>** nodo y el resto de tipos de nodos se utiliza para generar el esquema para que represente un mensaje concreto que se intercambia mediante BizTalk.  

## <a name="insert-schema-node-options"></a>Las opciones de nodo de esquema de inserción  
 El Editor de BizTalk proporciona un modo de construir esquemas XSD sin necesidad de aprender todas las complejidades de la sintaxis XSD. Cuando se usa el **Insertar nodo de esquema** comando el **BizTalk** menú o el menú contextual, existen las siguientes opciones para los nodos que va a insertar en el menú en cascada.  


| Opciones del menú Insertar nodo de esquema |                                                                                                                                                                                                                                          Descripción                                                                                                                                                                                                                                          |
|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        **Registro secundario**        |                                                                                                                                                           Inserta un **registro** nodo al final de la secuencia del nodo seleccionado. Para obtener más información acerca de **registro** nodos, consulte [nodos Registro](../core/record-nodes.md).                                                                                                                                                            |
|   **Atributo de campo secundario**    |                                                                                                                                  Inserta un **atributo de campo** nodo al final del seleccionado **registro** o **grupo de atributos** nodo. Para obtener más información acerca de **atributo de campo** nodos, consulte [nodos atributo de campo](../core/field-attribute-nodes.md).                                                                                                                                   |
|    **Elemento de campo secundario**     |                                                                                                                                                           Inserta un **elemento de campo** nodo dentro del nodo seleccionado. Para obtener más información acerca de **elemento de campo** nodos, consulte [nodos elemento de campo](../core/field-element-nodes.md).                                                                                                                                                           |
|       **Registro hermano**       |                                                                                                                                                         Inserta un **registro** nodo al final de la secuencia que contiene el nodo seleccionado. Para obtener más información acerca de **registro** nodos, consulte [nodos Registro](../core/record-nodes.md).                                                                                                                                                          |
|  **Atributo de campo hermano**   |                                                                                                                        Inserta un **atributo de campo** nodo al final de la **registro** o **grupo de atributos** nodo que contiene el nodo seleccionado. Para obtener más información acerca de **atributo de campo** nodos, consulte [nodos atributo de campo](../core/field-attribute-nodes.md).                                                                                                                         |
|   **Elemento de campo hermano**    |                                                                                                                                           Inserta un **elemento de campo** nodo al final de la secuencia que contiene el nodo seleccionado. Para obtener más información acerca de **elemento de campo** nodos, consulte [nodos elemento de campo](../core/field-element-nodes.md).                                                                                                                                            |
|       **Grupo de secuencias**       |                                                                                                                           Inserta un **grupo Sequence** nodo (\<secuencia\> en la vista de árbol) al final de la secuencia del nodo seleccionado. Para obtener más información acerca de **grupo Sequence** nodos, consulte [nodos grupo de secuencias](../core/sequence-group-nodes.md).                                                                                                                            |
|        **Grupo de elecciones**        |                                                                                                                                Inserta un **grupo de elecciones** nodo (\<elección\> en la vista de árbol) al final de la secuencia del nodo seleccionado. Para obtener más información acerca de **grupo de elecciones** nodos, consulte [nodos grupos de elecciones](../core/choice-group-nodes.md).                                                                                                                                 |
|         **Todos los grupos**          | Inserta un **todos los grupos** nodo (\<todas\> en la vista de árbol) como nodo secundario sin atributos solo de un **registro** utilice el nodo, reemplazando el valor predeterminado de un **secuencia**  elemento dentro de la **registro** nodo con el uso de un **todas** elemento. Para poder insertar una **todos los grupos** nodo, debe cambiar la **tipo de contenido** propiedad de la que contiene **registro** nodo **ComplexContent**. Para obtener más información acerca de **todos los grupos** nodos, consulte [todos los nodos de grupo](../core/all-group-nodes.md). |
|      **Grupo de atributos**       |                                                                                  Inserta un **grupo de atributos** nodo (\<AttrGroup:attrGroup*N* \> en la vista de árbol, donde *N* es un número de progresión) en al final del seleccionado **registro** o **grupo de atributos** nodo. Para obtener más información acerca de **grupo de atributos** nodos, consulte [nodos grupo de atributos](../core/attribute-group-nodes.md).                                                                                   |
|        **Cualquier elemento**         |                                                                                 Inserta un **cualquier elemento** nodo (<strong>\<</strong>cualquier<strong>\></strong> en la vista de árbol) al final de la secuencia seleccionada **registro** , **Grupo sequence**, **grupo de elecciones**, o **todos los grupos** nodo. Para obtener más información acerca de **cualquier elemento** nodos, consulte [nodos cualquier elemento](../core/any-element-nodes.md).                                                                                 |
|       **Cualquier atributo**        |                                                                                         Inserta un **cualquier atributo** nodo (<strong>\<</strong>AnyAttribute<strong>\></strong> en la vista de árbol) al final de la secuencia dentro de la seleccionada **Registro** o **grupo de atributos** nodo. Para obtener más información acerca de **cualquier atributo** nodos, consulte [nodos cualquier atributo](../core/any-attribute-nodes.md).                                                                                         |

 En muchos casos, al agregar un nodo simple en el Editor de BizTalk, se agregan varios elementos anidados en la representación XSD correspondiente del esquema. Puesto que estos elementos anidados pueden tener una sintaxis compleja, el uso del Editor de BizTalk para organizar los nodos gráficamente constituye una forma de crear esquemas XSD con menor posibilidad de errores que la edición manual del XSD. Otro factor que hay que tener en cuenta es que, al usar el Editor de BizTalk siempre para construir esquemas XSD, se genera un subconjunto más controlado de XSD en uso en las descripciones de los esquemas.  

 En general, el Editor de BizTalk combina un enfoque simplificado para construir esquemas XSD mediante los conceptos genéricos de registros y campos con un control más explícito de XSD determinado construcciones, como **secuencia**,  **opción**, **cualquier**, y **anyattribute** elementos.  

 Cada tipo de nodo tiene un conjunto único de propiedades que se pueden configurar en la ventana Propiedades de Visual Studio. En general, estas propiedades se corresponden con los atributos de los elementos XSD en la representación XSD correspondiente del esquema. Para obtener más información acerca de las propiedades de nodo, vea **propiedades del nodo** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

 En esta sección se describen los tipos de nodos utilizados en el Editor de BizTalk, se explican brevemente sus propiedades y se proporcionan vínculos a información de referencia acerca de sus propiedades.  

## <a name="next-steps"></a>Pasos siguientes

-   [Nodos que se corresponden directamente con datos y estructuras de instancias de mensaje](../core/nodes-that-correspond-directly-to-message-instance-data-and-structure.md)  

-   [Nodos que controlan la estructura y las variaciones de los mensajes de instancia](../core/nodes-that-control-instance-message-structure-and-variations.md)  

-   [Nodos que simplifican la creación de esquemas](../core/nodes-that-simplify-schema-creation.md)  

-   [Nodos que proporcionan funciones de carácter comodín](../core/nodes-that-provide-wildcard-capabilities.md)  

-   [Propiedades de los nodos](../core/node-properties.md)