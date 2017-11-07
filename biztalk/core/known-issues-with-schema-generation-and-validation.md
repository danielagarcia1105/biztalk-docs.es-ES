---
title: "Problemas conocidos con la validación y generación de esquema | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df1eaa6c-0d3e-4aec-9de0-8b9817b7bb97
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a462ab04aad857bf87b189cafce14bb9c3747e8
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="known-issues-with-schema-generation-and-validation"></a>Problemas conocidos con la generación de esquemas y validación
En este tema se proporciona información acerca de los problemas conocidos relacionados con la generación y validación de esquemas.  
  
## <a name="an-instance-message-generated-for-a-positional-record-with-tags-could-be-incorrect"></a>Un mensaje de instancia generado para un registro posicional con etiquetas puede ser incorrecto  
 En los registros posicionales, la etiqueta puede estar dentro de un campo o puede abarcar varios campos. En cualquier caso, la instancia generada no será válida y generará un error en el motor de análisis durante la fase de análisis.  
  
 Si la etiqueta no forma parte de ningún elemento secundario (registros o campos secundarios), no se producirá el problema.  
  
 Para solucionar este problema, incluya el valor real de las etiquetas como el valor predeterminado en el esquema. En la extensión de archivo sin formato del Editor de BizTalk, puede establecer la **valor fijo** o **Default Value** propiedad de campo posicional correspondiente con el valor de la etiqueta.  
  
## <a name="an-instance-message-generated-for-a-field-with-some-restrictions-may-not-pass-validation"></a>Un mensaje de instancia generado para un campo con algunas restricciones puede no pasar la validación  
 Al generar un mensaje de instancia de un esquema que contiene uno o varios **elemento de campo** y **atributo de campo** nodos que tienen tipos de datos que se han derivado mediante el mecanismo de restricción, como Cuando el **patrón** se utiliza la propiedad, los datos de ejemplo generados para estos campos no pueden cumplir los requisitos de la restricción, lo que evita que la validación correcta de ese mensaje de instancia mediante el mismo esquema de que se generó.  
  
## <a name="an-instance-message-generated-for-a-schema-that-contains-an-infinite-loop-may-not-be-valid"></a>Un mensaje de instancia generado para un esquema que contiene un bucle infinito puede no ser válido  
 El esquema puede contener un bucle infinito cuando contiene una referencia circular en un nodo con un **Min Occurs** valor de propiedad mayor que o igual a uno, lo que impediría una condición de finalización. La generación de mensajes de instancia se finalizará de forma artificial para que la operación de generación pueda finalizar. No obstante, el mensaje de instancia generado no se ajustará al esquema desde el que se generó. Dichos esquemas son normalmente sospechosos.  
  
## <a name="validation-of-xml-instance-fails-for-document-schema-which-has-the-target-namespacehttpwwww3orgxml1998namespace"></a>Se produce un error en Validación de instancia XML para el esquema del documento que tiene el espacio de nombres de destino = "http://www.w3.org/XML/1998/namespace"  
 El hipervínculo "http://www.w3.org/XML/1998/namespace" es un espacio de nombres reservado cuyo prefijo debería ser "XML". Puede modificar manualmente el prefijo a “XML”.

## <a name="see-also"></a>Vea también
Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
