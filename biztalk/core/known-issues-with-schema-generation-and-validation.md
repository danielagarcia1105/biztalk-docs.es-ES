---
title: Problemas conocidos con la validación y generación de esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df1eaa6c-0d3e-4aec-9de0-8b9817b7bb97
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 298376e0d8e22e84964c2a70df165664f0da9b45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968221"
---
# <a name="known-issues-with-schema-generation-and-validation"></a>Problemas conocidos de validación y generación de esquema
En este tema se proporciona información acerca de los problemas conocidos relacionados con la generación y validación de esquemas.  
  
## <a name="an-instance-message-generated-for-a-positional-record-with-tags-could-be-incorrect"></a>Un mensaje de instancia generado para un registro posicional con etiquetas puede ser incorrecto  
 En los registros posicionales, la etiqueta puede estar dentro de un campo o puede abarcar varios campos. En cualquier caso, la instancia generada no será válida y generará un error en el motor de análisis durante la fase de análisis.  
  
 Si la etiqueta no forma parte de ningún elemento secundario (registros o campos secundarios), no se producirá el problema.  
  
 Para solucionar este problema, incluya el valor real de las etiquetas como el valor predeterminado en el esquema. En la extensión de archivo sin formato del Editor de BizTalk, puede establecer el **valor fijo** o **Default Value** propiedad de campo posicional correspondiente con el valor de la etiqueta.  
  
## <a name="an-instance-message-generated-for-a-field-with-some-restrictions-may-not-pass-validation"></a>Un mensaje de instancia generado para un campo con algunas restricciones puede no pasar la validación  
 Al generar un mensaje de instancia de un esquema que contiene uno o varios **elemento de campo** y **atributo de campo** nodos que tienen tipos de datos que se han derivado mediante el mecanismo de restricción como Cuando el **patrón** se usa la propiedad, los datos de ejemplo generados para estos campos pueden no cumplir los requisitos de la restricción, lo que impide realizar correctamente la validación de ese mensaje de instancia mediante el mismo esquema de que se generó.  
  
## <a name="an-instance-message-generated-for-a-schema-that-contains-an-infinite-loop-may-not-be-valid"></a>Un mensaje de instancia generado para un esquema que contiene un bucle infinito puede no ser válido  
 El esquema puede contener un bucle infinito cuando contiene una referencia circular a un nodo con un **Min Occurs** valor mayor o igual a uno, lo que impediría una condición de finalización de la propiedad. La generación de mensajes de instancia se finalizará de forma artificial para que la operación de generación pueda finalizar. No obstante, el mensaje de instancia generado no se ajustará al esquema desde el que se generó. Dichos esquemas son normalmente sospechosos.  
  
## <a name="validation-of-xml-instance-fails-for-document-schema-which-has-the-target-namespacehttpwwww3orgxml1998namespace"></a>Se produce un error de validación de instancia XML para el esquema de documento que tiene el espacio de nombres = "<http://www.w3.org/XML/1998/namespace>"  
 El hipervínculo "<http://www.w3.org/XML/1998/namespace>" es un espacio de nombres reservado cuyo prefijo debería ser "XML". Puede modificar manualmente el prefijo a “XML”.

## <a name="see-also"></a>Vea también
Para obtener más detalles acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
