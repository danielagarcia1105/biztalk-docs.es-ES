---
title: Validar la configuración del adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8eeb8742-7083-462b-8d3a-e58103112542
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c03054332e0cd2117c1219afec3dd1aa0a09d6bd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973306"
---
# <a name="validating-the-adapter-configuration"></a>Validar la configuración del adaptador
Al agregar la ubicación de recepción y el puerto de envío, le pedirá que configure las propiedades personalizadas en el  **\<**  *nombre de adaptador*  **\> propiedades de transporte**  cuadro de diálogo. Los archivos de esquema XSD del proyecto AdapterHarness definen estas propiedades.  
  
 La validación del esquema de configuración se realiza en tres partes:  
  
1.  Al mostrar una configuración guardada, el marco de trabajo de adaptadores valida el documento XML guardado con respecto al esquema antes de cargar el documento en la página de propiedades. El marco de trabajo asume que un documento que no es válido indica un cambio en la definición del esquema de configuración. En la página de propiedades solo se cargan los documentos válidos.  
  
2.  Al guardar una configuración, si el adaptador implementa la **IAdapterConfigValidation** interfaz, el marco de trabajo pasa al adaptador el documento XML construido de serializar los datos de la página de propiedades. A continuación, el adaptador procesa el documento. Los errores deben producir excepciones que detecta el marco de trabajo y se muestran al usuario. Cualquier valor que falte o que se genere se debe generar durante la validación. Mediante el \<browsable show = "false"\> decoración suprime la aparición de una entrada en la cuadrícula de propiedades, incluso aunque el valor aparece en la instancia XML.  
  
3.  Al guardar una configuración antes de colocar el valor en la base de datos, el marco de trabajo valida de nuevo el documento XML con respecto al esquema. Esto asegura que solo se almacenan los datos válidos.  
  
## <a name="see-also"></a>Vea también  
 [Problemas de diseño del adaptador](../core/adapter-design-issues.md)