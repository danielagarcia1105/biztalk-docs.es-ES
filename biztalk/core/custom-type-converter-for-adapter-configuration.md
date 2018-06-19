---
title: Convertidor de tipos personalizado para la configuración del adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60e94dde-d29d-43ff-84b0-b2ba86851151
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6285cd61fd0738fb97c6192cd52b812d96ede7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238716"
---
# <a name="custom-type-converter-for-adapter-configuration"></a>Convertidor de tipos personalizado para la configuración del adaptador
Como el editor personalizado, el convertidor de tipos personalizado reemplaza la **System.ComponentModel.TypeConverter** clase de uno de sus elementos secundarios. El convertidor agrega formato al valor que se almacena pero que no aparece en la página de propiedades. El **ConvertFrom** método agrega corchetes alrededor del valor de cadena y la **ConvertTo** método quita de ellos.  
  
 El código siguiente es la definición de clase del convertidor de tipos personalizado:  
  
```  
using System;  
using System.ComponentModel;  
  
namespace AdapterManagement.ComponentModel {  
  
   public class DesignerTypeConverter : StringConverter {  
  
      public override bool CanConvertTo(ITypeDescriptorContext context, Type destinationType) {  
         return (typeof(String) == destinationType) || base.CanConvertTo (context, destinationType);  
      }  
  
      public override object ConvertTo(ITypeDescriptorContext context, System.Globalization.CultureInfo culture, object value, Type destinationType) {  
         if (typeof(String) == destinationType && value is String) {  
            return ((String)value).TrimStart('[').TrimEnd(']');  
         }  
         return base.ConvertTo (context, culture, value, destinationType);  
      }  
  
      public override bool CanConvertFrom(ITypeDescriptorContext context, Type sourceType) {  
         return (typeof(String) == sourceType) || base.CanConvertFrom (context, sourceType);  
      }  
  
      public override object ConvertFrom(ITypeDescriptorContext context, System.Globalization.CultureInfo culture, object value) {  
         if (value is String) {  
            return "["+(String)value+"]";  
         }  
         return base.ConvertFrom (context, culture, value);  
      }  
   }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Diseñador de configuración de adaptador personalizado](../core/custom-adapter-configuration-designer.md)   
 [Editor desplegable personalizado para la configuración del adaptador](../core/custom-drop-down-editor-for-adapter-configuration.md)   
 [Editor de cuadro de diálogo Modal personalizado para la configuración del adaptador](../core/custom-modal-dialog-editor-for-adapter-configuration.md)   
 [Componentes de configuración avanzada para adaptadores](../core/advanced-configuration-components-for-adapters.md)