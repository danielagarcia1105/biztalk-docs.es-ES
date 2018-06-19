---
title: Configurar la canalización de ensamblador de marco de trabajo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fd51047-b9dd-4b98-a968-45d69148664e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8816d021c49de2b683471246d4d0fa89cd003af7
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710751"
---
# <a name="configure-the-biztalk-framework-assembler-pipeline-component"></a>Configurar el componente de canalización de ensamblador de BizTalk Framework
  
1.  Arrastre el componente de canalización de ensamblador de BizTalk Framework a la fase de ensamblado de la canalización de envío.  
  
2.  En la ventana Propiedades, en la **propiedades de componente de canalización** sección, establezca los siguientes valores de propiedad.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Agregar texto de instrucciones de procesamiento**|Permite que todos los documentos XML ensamblados contengan instrucciones de procesamiento como valor de esta propiedad. Esta opción también permite que los documentos contengan instrucciones para las aplicaciones. **Nota:** texto debe cumplir los estándares de instrucciones de procesamiento de XML de W3C de instrucción de procesamiento. <br /><br /> Valor predeterminado: anexar|  
    |**Agregar declaración XML**|Agrega una declaración XML a un mensaje saliente. Cuando sea true, la declaración XML siguiente se agrega al mensaje saliente: `<?xml version='1.0' encoding='UTF8'>`. La codificación especificada depende de la codificación utilizada por el ensamblador de BizTalk Framework, que respeta las propiedades de tiempo de ejecución específicas que contienen la información de codificación.<br /><br /> Valor predeterminado: **True**|  
    |**Dirección de notificación de entrega**|Especifica la dirección a la que se enviará la notificación de entrega del documento de BizTalk Framework. **Advertencia:** al usar el ensamblador de BizTalk Framework con confirmaciones habilitadas, es probable que el procesamiento de confirmación puede acumulen resultado de un interbloqueo. El interbloqueo se produce cuando se procesan varias confirmaciones en lotes independientes para un único mensaje. Para evitar que se produzca este problema, debería configurar el tamaño del lote en 1 para la ubicación de puerto de dirección de recepción de la entrega especificada.|  
    |**Tipo de dirección de notificación de entrega**|Especifica el tipo de dirección a la que se enviará la notificación de entrega del documento de BizTalk Framework.<br /><br /> Valor predeterminado: biz: **Nota:** el prefijo biz: se utilizaba para indicar unos identificadores de organización para los extremos de origen y destino en el servidor BizTalk Server y para la interoperabilidad con esos sistemas. El prefijo se proporciona de forma predeterminada. Por ejemplo, escriba = "biz: OrganizationName", (src &#124; dest) = "Party1".|  
    |**Notificación de entrega enviada por tiempo**|Especifica el tiempo (en minutos) en el que se deberá haber recibido la notificación de entrega del documento de BizTalk Framework.<br /><br /> Valor predeterminado: 30|  
    |**Dirección de destino**|Especifica la dirección de destino.<br /><br /> Valor predeterminado: ninguno|  
    |**Tipo de dirección de destino**|Especifica el tipo de dirección de destino.<br /><br /> Valor predeterminado: biz: **Nota:** el prefijo biz: se utilizaba para indicar unos identificadores de organización para los extremos de origen y destino en el servidor BizTalk Server y para la interoperabilidad con esos sistemas. El prefijo se proporciona de forma predeterminada. Por ejemplo, escriba = "biz: OrganizationName", (src &#124; dest) = "Party1".|  
    |**Esquemas de documentos**|Indica el espacio de nombres y el nombre de tipo del esquema o esquemas que se van a aplicar al documento. Para obtener más información, consulte [cómo utilizar el Editor de propiedades de la colección de esquema](../core/how-to-use-the-schema-collection-property-editor.md). **Nota:** recibirá un error "dos o más esquemas seleccionados comparten el mismo espacio de nombres de destino" Si especifica dos o más esquemas para la **esquemas de documentos** propiedad. <br /><br /> Valor predeterminado: colección vacía|  
    |**Tema de documento**|Identifica una referencia de URI que identifica de forma exclusiva el propósito general del documento de BizTalk Framework.<br /><br /> Valor predeterminado: ninguno|  
    |**Esquemas de sobres**|Indica el espacio de nombres y nombre de tipo del esquema o esquemas que se aplicarán a los sobres. Para obtener más información, consulte [cómo utilizar el Editor de propiedades de la colección de esquema](../core/how-to-use-the-schema-collection-property-editor.md). **Nota:** recibirá un error "dos o más esquemas seleccionados comparten el mismo espacio de nombres de destino" Si especifica dos o más esquemas para la **esquemas de sobres** propiedad. <br /><br /> Valor predeterminado: BTF2Schemas.btf2_envelope|  
    |**Generar solicitud de notificación de entrega**|Indica si la solicitud de notificación de entrega del documento de BizTalk Framework debería generarse. Se utiliza esta opción para habilitar una mensajería confiable para BizTalk Framework.<br /><br /> Valor predeterminado: **True**|  
    |**Período de vida (en minutos)**|Especifica la cantidad de tiempo (en minutos) durante la que el mensaje es válido.<br /><br /> Valor predeterminado: 30|  
    |**Instrucciones de procesamiento**|Especifica cómo se controlan las instrucciones de procesamiento XML en el documento de instancia XML.<br /><br /> **Anexar**: el valor de **agregar texto de instrucciones de procesamiento** debería anexarse a las instrucciones de procesamiento en el mensaje preexistentes.<br /><br /> **Crear nuevo**: el valor de **agregar texto de instrucciones de procesamiento** especificado en el campo debería sobrescribir o reemplazar las instrucciones que aparecen en el mensaje de procesamiento preexistentes.<br /><br /> Si **crear nuevo** está seleccionada, **agregar texto de instrucciones de procesamiento** debe contener instrucciones de procesamiento válidas.<br /><br /> **Omitir**: si existe texto en el mensaje de instrucciones de procesamiento, se quita.<br /><br /> Valor predeterminado: **anexado**|  
    |**Dirección de origen**|Especifica la dirección de origen.<br /><br /> Valor predeterminado: ninguno|  
    |**Tipo de dirección de origen**|Especifica el tipo de dirección de origen.<br /><br /> Valor predeterminado: biz: **Nota:** el prefijo biz: se utilizaba para indicar unos identificadores de organización para los extremos de origen y destino en el servidor BizTalk Server y para la interoperabilidad con esos sistemas. El prefijo se proporciona de forma predeterminada. Por ejemplo, escriba = "biz: OrganizationName", (src &#124; dest) = "Party1".|  
    |**Juego de caracteres de destino**|Especifica el juego de caracteres de destino utilizado para codificar los mensajes salientes.<br /><br /> Valor predeterminado: ninguno|  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de ensamblador de BizTalk Framework](../core/biztalk-framework-assembler-pipeline-component.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [Pipelines\AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)