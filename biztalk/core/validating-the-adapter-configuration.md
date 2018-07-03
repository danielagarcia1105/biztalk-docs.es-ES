---
title: Validar la configuración del adaptador | Microsoft Docs
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
ms.openlocfilehash: 0d7fa3af1fa0116f859f0d3f39f2235be38cbc0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008133"
---
# <a name="validating-the-adapter-configuration"></a>Validar la configuración del adaptador
Al agregar la ubicación de recepción y el puerto de envío, le pedirá que configure las propiedades personalizadas en el **\<** <em>nombre de adaptador</em> **\> propiedades de transporte** cuadro de diálogo. Los archivos de esquema XSD del proyecto AdapterHarness definen estas propiedades.  
  
 La validación del esquema de configuración se realiza en tres partes:  
  
1.  Al mostrar una configuración guardada, el marco de trabajo de adaptadores valida el documento XML guardado con respecto al esquema antes de cargar el documento en la página de propiedades. El marco de trabajo asume que un documento que no es válido indica un cambio en la definición del esquema de configuración. En la página de propiedades solo se cargan los documentos válidos.  
  
2.  Al guardar una configuración, si el adaptador implementa la **IAdapterConfigValidation** interfaz, el marco de trabajo se pasa al adaptador el documento XML construido de serializar los datos de la página de propiedad. A continuación, el adaptador procesa el documento. Los errores deben producir excepciones que detecta el marco de trabajo y se muestran al usuario. Cualquier valor que falte o que se genere se debe generar durante la validación. Mediante el \<browsable show = "false"\> decoración suprime que muestra una entrada en la cuadrícula de propiedades, aunque el valor aparece en la instancia XML.  
  
3.  Al guardar una configuración antes de colocar el valor en la base de datos, el marco de trabajo valida de nuevo el documento XML con respecto al esquema. Esto asegura que solo se almacenan los datos válidos.  
  
## <a name="see-also"></a>Vea también  
 [Problemas de diseño del adaptador](../core/adapter-design-issues.md)