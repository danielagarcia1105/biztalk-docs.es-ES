---
title: Cómo validar los mensajes de instancia | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f6302c6-b56b-4572-aa76-0f4c4599672a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd0baa898f801c924cffc5a446aa1a22d063a8fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256796"
---
# <a name="how-to-validate-instance-messages"></a>Cómo validar los mensajes de instancia
Una vez construido un esquema, puede comprobarlo si valida un mensaje de instancia existente que sepa que representa correctamente a esos mensajes de instancia con respecto al esquema.  
  
 Este tema proporciona instrucciones paso a paso para esta tarea de validación.  
  
### <a name="to-validate-an-instance-message-against-a-schema"></a>Para validar un mensaje de instancia con respecto a un esquema  
  
1.  En el Explorador de soluciones, haga clic en el esquema y, a continuación, haga clic en **propiedades**.  
  
2.  Si es necesario, en la ventana Propiedades, expanda el **General** sección de la **General** ficha haciendo clic en su signo más (+) icono.  
  
3.  En el **nombre de archivo de instancia de entrada** campo de valor de propiedad, escriba el nombre de un archivo o utilice el botón de puntos suspensivos (**...** ) situado en el extremo derecho del campo de valor para buscar un archivo que contiene el mensaje de instancia que se valida con el esquema y, a continuación, haga clic en **abiertos**.  
  
4.  En **el Explorador de soluciones**, haga clic en el nombre de esquema y, a continuación, haga clic en **Validar instancia**.  
  
5.  En la ventana Resultados, vea los resultados. En esta ventana se muestran mensajes para indicar si la operación ha sido correcta o no.  
  
> [!NOTE]
>  En algunos casos, los mensajes de instancia generados desde un esquema concreto no pueden pasar la validación con ese mismo esquema. Para obtener más información acerca de estos casos, consulte [problemas conocidos relacionados con la validación y generación de esquema](../core/known-issues-with-schema-generation-and-validation.md). Normalmente, deseará editar un mensaje de instancia generado y cambiar los datos que contiene para que represente de una forma más real su situación. A continuación, use ese mensaje de instancia modificado para validar el esquema.  
  
## <a name="see-also"></a>Vea también  
 [Comprobación de esquemas](../core/testing-schemas.md)   
 [Validación de esquemas](../core/schema-validation1.md)   
 [Validación y generación de mensajes de instancia](../core/instance-message-generation-and-validation.md)