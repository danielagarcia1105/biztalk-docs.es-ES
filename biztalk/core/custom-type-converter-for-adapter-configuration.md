---
title: "Convertidor de tipos personalizado para la configuración del adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60e94dde-d29d-43ff-84b0-b2ba86851151
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6285cd61fd0738fb97c6192cd52b812d96ede7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="custom-type-converter-for-adapter-configuration"></a><span data-ttu-id="791b5-102">Convertidor de tipos personalizado para la configuración del adaptador</span><span class="sxs-lookup"><span data-stu-id="791b5-102">Custom Type Converter for Adapter Configuration</span></span>
<span data-ttu-id="791b5-103">Como el editor personalizado, el convertidor de tipos personalizado reemplaza la **System.ComponentModel.TypeConverter** clase de uno de sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="791b5-103">Like the custom editor, the custom type converter overrides the **System.ComponentModel.TypeConverter** class of one of its children.</span></span> <span data-ttu-id="791b5-104">El convertidor agrega formato al valor que se almacena pero que no aparece en la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="791b5-104">Here, the converter adds formatting to the value to be persisted but does not appear on the property page.</span></span> <span data-ttu-id="791b5-105">El **ConvertFrom** método agrega corchetes alrededor del valor de cadena y la **ConvertTo** método quita de ellos.</span><span class="sxs-lookup"><span data-stu-id="791b5-105">The **ConvertFrom** method adds square brackets around the string value and the **ConvertTo** method removes them.</span></span>  
  
 <span data-ttu-id="791b5-106">El código siguiente es la definición de clase del convertidor de tipos personalizado:</span><span class="sxs-lookup"><span data-stu-id="791b5-106">The following code is the class definition for the custom type converter:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="791b5-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="791b5-107">See Also</span></span>  
 <span data-ttu-id="791b5-108">[Diseñador de configuración de adaptador personalizado](../core/custom-adapter-configuration-designer.md) </span><span class="sxs-lookup"><span data-stu-id="791b5-108">[Custom Adapter Configuration Designer](../core/custom-adapter-configuration-designer.md) </span></span>  
 <span data-ttu-id="791b5-109">[Editor desplegable personalizado para la configuración del adaptador](../core/custom-drop-down-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="791b5-109">[Custom Drop-Down Editor for Adapter Configuration](../core/custom-drop-down-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="791b5-110">[Editor de cuadro de diálogo Modal personalizado para la configuración del adaptador](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="791b5-110">[Custom Modal Dialog Editor for Adapter Configuration](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span></span>  
 [<span data-ttu-id="791b5-111">Componentes de configuración avanzada para adaptadores</span><span class="sxs-lookup"><span data-stu-id="791b5-111">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)