---
title: Propiedades y esquema de propiedades de MIME-SMIME | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26dd25b9-7eb8-4354-9929-dc1985dd1d77
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 882b25733a46b8b7b973c992d465132df4c47b75
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22263196"
---
# <a name="mime-smime-property-schema-and-properties"></a>Propiedades y esquema de propiedades de MIME-SMIME

## <a name="namespace-properties"></a>Propiedades de Namespace
El **http://schemas.microsoft.com/BizTalk/2003/mime-properties** espacio de nombres contiene propiedades que puede utilizar para establecer propiedades de contexto de mensajes y partes para el componente de canalización de codificador de MIME/SMIME. El componente de canalización de codificador de MIME/SMIME utiliza estas propiedades para generar los encabezados MIME/SMIME apropiados en el mensaje que se crea. En la tabla siguiente se describen las propiedades MIME/SMIME.  
  
|Propiedad|Ámbito|Tipo|Description|  
|--------------|-----------|----------|-----------------|  
|**FileName**|Por parte de mensaje|xs:string|Establece el encabezado de nombre de archivo de la parte MIME/SMIME.|  
|**ContentID**|Por parte de mensaje|xs:string|Establece el encabezado de Id. de contenido de la parte MIME/SMIME.|  
|**ContentDescription**|Por parte de mensaje|xs:string|Establece el encabezado de descripción de contenido de la parte MIME/SMIME.|  
|**Contenttransferencoding correspondiente**|Por parte de mensaje|xs:string|Establece el encabezado de codificación de la transferencia de contenido de la parte MIME/SMIME generada.<br /><br /> Este valor invalida la **codificación de transferencia de contenido** valor configurado en el Diseñador de canalizaciones. Para un mensaje de varias partes, puede utilizar codificaciones diferentes para partes MIME/SMIME diferentes.|  
|**ContentLocation**|Por parte de mensaje|xs:string|Establece el encabezado de ubicación de contenido de la parte MIME/SMIME generada.|  
|**IsMIMEEncoded**|Por parte de mensaje|xs:boolean|Especifica si el mensaje tiene carga MIME/SMIME. El componente MIME escribe este valor, por lo tanto usted no tiene que establecerlo.|  
  
 El codificador MIME/SMIME también utiliza las siguientes propiedades del elemento de la **System** espacio de nombres.  
  
|Propiedad|Tipo|Description|  
|--------------|----------|-----------------|  
|ContentType|xs:string|Corresponde al encabezado de tipo de contenido de la parte MIME/SMIME generada.|  
|FileName|xs:string|Corresponde al nombre de archivo.|  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar el componente de canalización de descodificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)   
 [Cómo configurar el componente de canalización de codificador de MIME-SMIME](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [MIME (ejemplo de BizTalk Server)](../core/mime-biztalk-server-sample.md)   
 **Propiedades de contexto de mensaje** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]