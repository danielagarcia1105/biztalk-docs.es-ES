---
title: Cómo usar los tipos de mensaje de varias partes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- multi-part message types, parts
- multi-part message types, creating
- multi-part message types, type modifiers
- messages
- multi-part message types, deleting
- orchestrations, messages
- deleting, multi-part messages
- multi-part message types, about multi-part message types
- orchestrations, type modifier
- messages, multi-parts
- creating, multi-part messages
- messages, about messages
ms.assetid: 009a39bd-cfc4-42d9-918c-88ac24bfc370
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 083746c38a175db840f4554297e86d26b5fcb366
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013950"
---
# <a name="how-to-use-multi-part-message-types"></a>Cómo usar los tipos de mensaje de varias partes
Cada mensaje tiene un tipo de mensaje de varias partes, una descripción de la estructura del mensaje que se compone de cero o más partes de mensaje. Las partes se definen en el lenguaje de definición de esquemas XML (XSD) mediante esquemas o clases .NET. Puede definir sus propios tipos de mensaje de varias partes o usar los esquemas y las clases .NET existentes.  

 Puede obtener acceso a las partes de mensaje o asignarlas directamente dentro de la orquestación, o bien usar elementos individuales de partes de mensaje que se exponen como campos distintivos o campos de propiedades. Para obtener más información, consulte [usar campos distintivos y las propiedades de mensaje](../core/using-distinguished-fields-and-property-fields.md).  

> [!NOTE]
>  Un tipo de mensaje de varias partes no tiene que contener necesariamente varias partes.  

> [!NOTE]
>  Una parte de mensaje puede definirse mediante el tipo .NET **XmlDocument**, que se puede usar para contener un documento XML arbitrario, mediante cualquier tipo .NET que es serializable con XML, o por cualquier .NET escribe el admitir la serialización personalizada.  

## <a name="add-a-multi-part-message-type"></a>Agregar un tipo de mensaje de varias partes  

1.  En el **Vista orquestación** ventana, expanda el **tipos** nodo.  

2.  Haga clic en **tipos de mensaje de varias partes** y, a continuación, haga clic en **nuevo tipo de mensaje de varias partes**.  

     El **tipos de mensaje de varias partes** carpeta se expande, si se contrae y se agrega un nuevo tipo de mensaje de varias partes con parte de mensaje de un valor predeterminado.  

3.  Asigne un nombre al tipo de mensaje de varias partes y a la parte de mensaje proporcionada.  

     Si el tipo de mensaje de varias partes requiere más de una parte de mensaje, puede agregar partes adicionales asignando un nombre para el \<New\> parte de mensaje.  

4.  Asocie cada parte de mensaje a un tipo; por ejemplo, esquema o clase .NET.  

## <a name="remove-a-multi-part-message-type"></a>Quitar un tipo de mensaje de varias partes  

-   En el **Vista orquestación** (ventana), con el botón secundario que desea quitar y, a continuación, haga clic en el tipo de mensaje que la parte de varios **eliminar**.  

    > [!NOTE]
    >  Al quitar un tipo de mensaje de varias partes de la orquestación también se quitará la información de tipo de los mensajes que lo utilicen.  

    > [!NOTE]
    >  Los elementos que aparecen como de solo de lectura se definen en otra orquestación.  

## <a name="remove-a-part-from-a-multi-part-message-type"></a>Quitar un elemento de un tipo de mensaje de varias partes  

-   En el **Vista orquestación** ventana, haga clic en el elemento que desea quitar y haga clic en **eliminar**.  

    > [!NOTE]
    >  No se puede eliminar parte de un tipo de mensaje del mensaje si el **parte del cuerpo del mensaje** propiedad está establecida en true. Debe establecer primero la **parte del cuerpo del mensaje** propiedad en True para otra de las partes del tipo de mensaje.  

## <a name="set-the-type-modifier-for-a-multi-part-message-type"></a>Establecer el modificador de tipo para un tipo de mensaje de varias partes  

- En el **propiedades** ventana, establezca la propiedad siguiente:  


  |     Property      |                                                                                                                                                                                        Descripción                                                                                                                                                                                         |
  |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | **Modificador de tipo** | Determina el ámbito del tipo de mensaje de varias partes:<br /><br /> -   <strong>Privado:</strong>acceso a este tipo de mensaje de varias partes está limitado al módulo contenedor.<br />-   <strong>Público:</strong>no se limita el acceso a este tipo de mensaje de varias partes.<br />-   <strong>Interno:</strong>acceso a este tipo de mensaje de varias partes está limitado a los módulos dentro del mismo proyecto. |

## <a name="add-parts-to-an-existing-multi-part-message"></a>Agregar elementos a un mensaje de varias partes existente  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite agregar partes a un mensaje de varias partes XLANG y también hacer referencia a una parte de mensaje mediante un índice mayor que el número de partes declarado originalmente si la parte existe. Esta funcionalidad puede ser útil para enviar o recibir mensajes SMTP con un número variable de datos adjuntos. Esta funcionalidad se implementa del modo siguiente:  

- Desde el proyecto, agregue una referencia a **Microsoft.XLANGs.BaseTypes**.  

- Cree una variable (por ejemplo *xlangPart*) de tipo **Microsoft.XLANGs.BaseTypes.XLANGMessage**.  

- Llame a <em>xlangPart</em>**. AddPart(...)**  usando los argumentos apropiados de una forma expresión.  

  > [!NOTE]
  >  Las partes agregadas son del tipo **XmlDocument** por lo que no puede agregar un elemento de mensaje con formato personalizado mediante la **AddPart()** método.  

> [!NOTE]
>  Si se recibe un mensaje de varias partes que contiene mayor que el número de partes declarados, las lecturas de motor de orquestación cuántas partes hay se encuentran en el mensaje, a continuación, crea los tipos de partes apropiados para los elementos que coinciden con el número de partes del mensaje declarado tipo y, a continuación, construcciones **XmlDocument** partes para las partes restantes.  

## <a name="see-also"></a>Vea también  
 **IBaseMessage.AddPart (método) (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
 [Recursos XSD en Internet](../core/xsd-resources-on-the-web.md)   
 [Usar campos distintivos y campos de propiedades](../core/using-distinguished-fields-and-property-fields.md)   
 [Uso de mensajes en orquestaciones](../core/using-messages-in-orchestrations.md)