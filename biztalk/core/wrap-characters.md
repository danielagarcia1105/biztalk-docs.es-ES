---
title: Ajustar caracteres | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7268f46-9bf6-4c76-9b3a-b4ee0e8db997
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7d88c412c94505600443d351a150b6ca8a6876a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996597"
---
# <a name="wrap-characters"></a>Incluir caracteres adicionales.

## <a name="overview"></a>Información general
Un carácter de ajuste es un carácter simple que sirve para ajustar los caracteres de datos en un campo con el fin de suprimir el significado especial que, en caso contrario, tendría cualquiera de estos caracteres de datos. Por ejemplo, si define un registro de archivo sin formato con las siguientes características:  
  
- Nombre = Record1  
  
- Delimitado  
  
- Delimitador secundario = coma (,)  
  
- Orden secundario = infijo  
  
- Carácter de escape = barra diagonal inversa (\\)  
  
- Etiqueta = RECORD1  
  
- Tres campos denominados Field1, Field2 y Field3, cada uno de ellos definido para que use el carácter de signo de número (#) como carácter de ajuste.  
  
  Serán aplicables al registro los datos de archivo sin formato siguientes:  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 Los datos se desensamblan en el siguiente fragmento de XML.  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2></Field2>  
    <Field3></Field3>  
</Record1>  
  
```  
  
 Tenga en cuenta que se han quitado los caracteres de ajuste (#) que rodean a los caracteres de datos en negrita fieldl1, field2 y field3.  
  
 Cuando el ensamblador de archivo sin formato realiza la operación inversa, convertir la versión XML del registro a registro de archivo sin formato equivalente, se insertan los caracteres de ajuste antes y después de cada uno de los campos para producir la secuencia original de los caracteres de datos caracteres de archivo sin formato.  
  
 El carácter de escape definido y el carácter de ajuste definido se pueden usar de forma conjunta. Por ejemplo, supongamos que se cambia el valor de Field1 como se muestra a continuación (en negrita):  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2>field2</Field2>  
    <Field3>field3</Field3>  
</Record1>  
  
```  
  
 Cuando se ensamble el fragmento XML, mediante las definiciones de registro y campo proporcionadas, se generará la siguiente secuencia de caracteres de archivo sin formado (la secuencia de caracteres de signo de número con escape se muestra en negrita).  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 Al crear un esquema de archivo sin formato mediante el Editor de BizTalk, puede definir un carácter de ajuste predeterminado para el esquema completo mediante la **carácter de ajuste predeterminado** y **tipo de carácter de ajuste predeterminado** propiedades de la **Esquema** nodo. A continuación, puede configurar cada campo en el esquema para usar este carácter de ajuste predeterminado o un carácter de ajuste personalizado, específica de campo mediante el **carácter de ajuste** y **tipo de carácter de ajuste** propiedades de la **elemento de campo** o **atributo de campo** nodos en esquemas de archivo sin formato.
  
## <a name="see-also"></a>Vea también  
- [Formas de interpretar los caracteres especiales de un valor de campo](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- Propiedades de carácter de ajuste [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    -  Carácter de ajuste predeterminado (propiedad de nodo de esquemas de archivo sin formato
    -  Tipo de carácter de ajuste predeterminado (propiedad de nodo de esquemas de archivo sin formato
    -  (Propiedad de nodo de esquemas de archivo sin formato de carácter de ajuste  
    -  Tipo de carácter (propiedad de nodo de esquemas de archivo sin formato de ajuste