---
title: "Etiquetas de decoración de esquema de configuración de adaptador Framework | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d5d7f6b-2273-45a6-ba9d-43201760cf22
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b834482b70e75d12bb6786dac2a5d9eb6f9fef40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-framework-configuration-schema-decoration-tags"></a>Etiquetas de decoración de esquema de configuración de adaptador Framework
Las etiquetas que se describen en este tema se pueden usar en los archivos de esquema de configuración para que los datos se muestren y organicen en las páginas de propiedades de adaptador.  
  
 En la ilustración siguiente se muestra cómo la página de propiedades de la ubicación de recepción de FTP implementa algunas de estas etiquetas.  
  
 ![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")  
El \<descripción >, \<displayname >, y \<categoría > etiquetas en la página de propiedades del adaptador FTP  
  
## <a name="designer"></a>\<Diseñador >  
 La decoración de adaptador de BizTalk Framework aparece entre un \<Designer > etiqueta y \</baf:designer > etiqueta de cierre. El \<Designer > tag ayuda a distinguir entre el marco de trabajo \<appinfo > y otros suministrada por el adaptador \<appinfo > información.  
  
## <a name="category"></a>\<categoría >  
 El \<categoría > decoración contiene la cadena utilizada para separar las entradas de la cuadrícula de propiedades en grupos. La decoración muestra todas las entradas con la misma cadena de categoría como las cadenas subordinadas de la categoría.  
  
 Puede localizar \<categoría > entradas.  
  
## <a name="description"></a>\<Descripción >  
 El \<descripción > decoración contiene la cadena utilizada para proporcionar texto descriptivo para las entradas en la parte inferior de la cuadrícula de propiedades.  
  
 Puede localizar \<descripción > entradas.  
  
## <a name="displayname"></a>\<DisplayName >  
 El \<displayname > decoración contiene la cadena utilizada para mostrar el nombre de una entrada. Esto le permite usar espacios, frases y así sucesivamente, cuando no se permitirá para un \<elemento > o \<atributo > nombre.  
  
 Puede localizar \<displayname > entradas.  
  
## <a name="readonly"></a>\<ReadOnly >  
 El \<readonly fijada = "" > decoración controla si un campo se puede editar. El valor del atributo "fixed" `true` (predeterminado) hace que un campo sea de solo lectura.  
  
 Al implementar un editor externo, implemente una referencia externa **TypeConverter** clase e invalidar el **GetStandardValuesExclusive** método en su lugar. La devolución de `true` hace que un campo sea de solo lectura pero mantiene el acceso al editor personalizado.  
  
## <a name="browsable"></a>\<puede examinar >  
 El \<browsable show = "" > decoración controla si un campo aparece en la cuadrícula de propiedades. Valor de atributo de un "Mostrar" `True` (valor predeterminado) hace que el campo aparecen en la cuadrícula.  
  
## <a name="converter"></a>\<convertidor >  
 El \<ensamblado convertidor = "" > decoración especifica lo que se desea **TypeConverter** nombre de clase para la \<elemento > o \<atributo >. El valor del atributo "assembly" opcional especifica la ruta de acceso al ensamblado que contiene lo que se desea **TypeConverter**. Sin un valor de "assembly" especificado, el nombre de la clase debe incluir los valores de nombre del ensamblado de la caché de ensamblados global, la clave, la referencia cultural y la versión.  
  
## <a name="editor"></a>\<Editor de >  
 El \<ensamblado editor = "" > decoración especifica lo que se desea **UITypeEditor** nombre de clase para la \<elemento > o \<atributo >. El valor del atributo "assembly" opcional especifica la ruta de acceso al ensamblado que contiene lo que se desea **UITypeEditor**. Sin un valor de "assembly" especificado, el nombre de la clase debe incluir los valores de nombre del ensamblado de la caché de ensamblados global, la clave, la referencia cultural y la versión.  
  
## <a name="null-values-for-optional-enumerations"></a>Valores nulos para enumeraciones opcionales  
 Al usar una enumeración opcional, debe tener uno de los valores \<ninguno > para indicar un valor nulo. No se trata de una etiqueta integrada aunque se puede conseguir al proporcionar un valor de enumeración que se trate como ninguno si la enumeración se deriva desde xsd:string. Esto no es posible para las enumeraciones que se derivan desde xsd:int, ya que el entero debe contener un valor.  
  
## <a name="see-also"></a>Vea también  
 [Extensiones de esquema de configuración de marco de trabajo de adaptadores](../core/adapter-framework-configuration-schema-extensions.md)