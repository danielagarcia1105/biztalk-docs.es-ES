---
title: Crear vínculos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, links
- BizTalk Mapper, links
ms.assetid: e8596c50-62e9-40a7-ad61-29cbdb4f4fc9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87570b82dc63a02c629e0fc024c2e44d57df1401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238572"
---
# <a name="creating-links"></a>Crear vínculos
El Asignador de BizTalk facilita la automatización de algunos elementos que intervendrán en la creación de vínculos. La creación de vínculos simples es similar a los tipos de datos simples. Existen formas más sofisticadas de crear vínculos que son más parecidas a las asignaciones de estructuras en un lenguaje de programación. Un ejemplo es la creación de un vínculo simple que especifique cómo se van a pasar varios elementos de datos de mensajes de instancia de entrada a los correspondientes mensajes de instancia de salida.  
  
 Se pueden crear vínculos con los siguientes métodos:  
  
-   **Creación de vínculos simples.** En la creación de vínculos simples, se arrastra para crear un vínculo. Arrastrar un campo del esquema de origen a un campo en el esquema de destino hace que se cree un elemento o atributo en un mensaje de instancia de salida e inserta el valor del elemento o atributo en el mensaje. Estos vínculos se pueden crear directamente entre **registro** y **campo** nodos en el esquema de origen y destino, o pueden incluir uno o más functoids en una ruta de acceso de vínculo entre **registro**y **campo** nodos en los esquemas de origen y de destino.  
  
-   **Vínculos de estructura.** En la creación de vínculos de estructura, se producen varios vínculos simples a la misma vez entre **registro** y **campo** nodos en los esquemas de origen y de destino que tienen la misma estructura relativa. Para utilizar la vinculación de estructuras, la estructura de las partes importantes de los dos esquemas debe ser la misma. Para obtener más información acerca de cómo configurar vínculos de estructura, vea [cómo vincular registros automáticamente](../core/how-to-link-records-automatically.md).  
  
-   **Vínculos de coincidencia de nombres.** Cuando utiliza este método, cree varios vínculos simples a la misma vez entre **registro** y **campo** nodos en los esquemas de origen y destino en función de los nombres de los **registros** y **campo** nodos. Para utilizar la vinculación de coincidencia de nombres, la estructura de los esquemas de origen y de destino debe ser muy similar, pero no exactamente igual. Para obtener más información acerca de cómo configurar vínculos de coincidencia de nombres, vea [cómo vincular registros automáticamente](../core/how-to-link-records-automatically.md).  
  
    > [!NOTE]
    >  También puede ver [cómo administrar vínculos existentes](../core/how-to-manage-existing-links.md) para obtener información acerca de cómo cambiar o modificar los vínculos existentes.  
  
## <a name="preserving-whitespace-in-a-link"></a>Conservar carácter en blanco en un vínculo  
 Si desea conservar el carácter en blanco de un elemento de origen al realizar asignaciones a un elemento de destino o functoid, será necesario escribir una secuencia de comandos personalizada.  
  
 Los caracteres en blanco no se conservan en el Asignador ni en el sistema de tiempo de ejecución. Ambos utilizaban BTSXslTransform.Transform que controla transformación de mensajes grandes y se basa en XmlReader para desplazarse mediante el modelo de datos XPath.  
  
 Para conservar caracteres en blanco, puede escribir una secuencia de comandos personalizada que devuelva la cantidad necesaria de espacios en blanco. Por ejemplo, el código que aparece a continuación siempre devuelve una cadena con 5 caracteres en blanco:  
  
```  
public string Whitespace(string param1)  
{  
  return "     ";  
}  
```  
  
 Si vincula un elemento de origen a la entrada de este script y un elemento de destino a la salida, cuando la asignación se ejecuta, el elemento de salida contendrá 5 caracteres en blanco.  
  
> [!NOTE]
>  Si visualiza la salida mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], el elemento aparecerá vacío. Esto se debe a que el visor XML trata elementos que contienen caracteres en blanco sólo como vacíos. Para ver el espacio en blanco, haga clic en la vista XML y seleccione **ver código fuente**.  
  
## <a name="see-also"></a>Vea también  
 [Cómo editar propiedades de vínculo](../core/how-to-edit-link-properties.md)