---
title: "Detección de tipo de mensaje dinámico y la resolución de esquemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic schema resolution
- disassembler, code sample
- schemas, dynamic resolution
- assembler, message types
- disassembler, message types
- code samples, disassembler
ms.assetid: 5f71d3df-a37e-4ef2-9055-b614656203e9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77e9a8949787fcd3c7e942c406c9f31470894a8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-message-type-discovery-and-schema-resolution"></a>Detección de tipo de mensaje dinámico y la resolución de esquemas
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] habilita la resolución de detección y el esquema del tipo de mensaje dinámico en las ensamblador y desensamblador SWIFT.  
  
## <a name="swift-disassembler"></a>Desensamblador SWIFT  
 El Desensamblador SWIFT (DASM) tiene la capacidad de detectar el tipo de mensaje de un mensaje recibido y cargar el esquema correspondiente necesario para analizar el mensaje dinámicamente. La mayor ventaja de esta característica es que puede configurar una sola canalización mediante el Desensamblador SWIFT para procesar los mensajes de SWIFT de cualquier tipo de mensaje SWIFT. Al contrario que el Desensamblador de archivos sin formato nativo de BizTalk, el Desensamblador SWIFT no es necesario crear una canalización de recepción independiente para cada tipo de mensaje que podría encontrar A4SWIFT.  
  
 Puede usar la detección de tipo de mensaje dinámico si asume que, en la mayoría de los casos, todos los mensajes que recibe de un sistema se iniciará con datos de encabezado estructuralmente homogéneas. Dentro del encabezado de datos son campos que revelan el tipo de mensaje del mensaje. Para los mensajes de SWIFT, los datos del encabezado constan de bloques de mensaje SWIFT 1, 2 y 3, con información del tipo de mensaje incluida en bloque 2 (conocido como el encabezado de la aplicación).  
  
 El componente de SWIFT DASM puede procesar todos los "único" (sin lotes) SWIFT mensajes de fábrica sin necesidad de cualquiera de las propiedades que puede establecer. De forma predeterminada, no se establecen el esquema de intercambio de SWIFT y el esquema de encabezado de SWIFT; Sin embargo, el componente de SWIFT DASM utilizará el esquema de encabezado de SWIFT presente en Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll para detectar el tipo de mensaje SWIFT dinámicamente y procesar los mensajes. Además, BRE y validación de XML están habilitadas de forma predeterminada para cualquier mensaje que procesa se validarán. Establecer la propiedad de esquema de encabezado de SWIFT para que apunte al encabezado de SWIFT en RuntimeSchemas.dll también se producirá en el mismo comportamiento que anteriormente.  
  
 Cuando la propiedad de configuración de esquema de encabezado de SWIFT para el Desensamblador SWIFT se establece en "None" (valor predeterminado), el Desensamblador resuelve dinámicamente y carga el esquema apropiado mediante los pasos siguientes:  
  
1.  Usa el esquema de encabezado especificado por el usuario (especificado por la propiedad de configuración de esquema de encabezado de SWIFT) para analizar el principio (encabezado) del mensaje de recepción.  
  
2.  Inspecciona el resultante "encabezado XML" para el campo de propiedad promocionada A4SWIFT_MessageType. Si este campo no existe, se utiliza el valor del campo como el "tipo de mensaje" y continúa con el paso 4. Si el campo no existe, continúa con el paso 3.  
  
3.  Inspecciona el encabezado XML para el campo de propiedad promocionada A4SWIFT_MessageType2 (esperado si el Desensamblador no encuentra el campo A4SWIFT_MessageType). Utiliza el valor del campo A4SWIFT_MessageType2 como el "tipo de mensaje".  
  
4.  Si el "tipo de mensaje" identificado en el paso 2 o 3 es "574", el Desensamblador SWIFT comprueba si el tipo de mensaje "574" está en la lista de tipos de mensaje especificado en la propiedad de configuración de la lista de mensajes de tipo doble (que es una propiedad del desensamblador de formato). En caso afirmativo, continúa con el paso 5. Si no, se pasa al paso 6.  
  
5.  Inspecciona el XML del encabezado para el campo de propiedad promocionada A4SWIFT_SecondaryMessageType. Si este campo no existe, el Desensamblador usa el valor del campo (por ejemplo, "IRSLST") como el "mensaje subtipo" y lo anexa al "tipo de mensaje", por ejemplo, "574_IRSLST".  
  
    > [!IMPORTANT]
    >  La explicación dada para el paso 5 es una simplificación de lo que el Desensamblador SWIFT hace para evaluar el subtipo del mensaje. En realidad, el Desensamblador SWIFT utiliza el siguiente algoritmo para determinar si un tipo de mensaje tiene subtipos y si es así, lo que es el siguiente subtipo.  
  
    ```  
    Given MT type number nxx ...  
    if nxx is in the Dual-Type list {  
      if field 119 exists AND field 119 is NOT null/empty {  
        if n == 1 {  
          if field 119 == "STP" {  
            Use MTnxxPLUS schema  
          } else if field 119 == "REMIT" {  
            Use MTnxx schema  
          } else {  
            Use MTnxx_<field 119> schema  
          }   
        } else {  
          // n != 1  
          Use MTnxx_<field 119> schema  
        }  
      } else {  
        // field 119 does not exist or 119 does exist but is null/empty  
        Use MTnxx schema  
      }  
    } else {  
      // nxx is not a dual-type message  
      Use MTnxx schema  
    }  
    ```  
  
6.  Ahora, el Desensamblador conoce el tipo de mensaje y pueda formar el nombre de esquema de intercambio mediante la concatenación de algunos prefijos y sufijos (por ejemplo, "MT" en el prefijo para realizar "MT574_IRSLST") de nombres de esquema fijo.  
  
7.  Carga el esquema de intercambio (por nombre) y analiza el mensaje completo, **desde el principio**, mediante el esquema cargado (Esto significa que el Desensamblador analiza el encabezamiento de datos dos veces: una vez utilizando el esquema de encabezado y utilizando de nuevo el principio del esquema de intercambio). El esquema de intercambio debe ser capaz de analizar el mensaje completo, incluido el encabezado.  
  
    > [!NOTE]
    >  El Desensamblador puede utilizar todos los esquemas de mensaje SWIFT A4SWIFT para analizar todo el intercambio SWIFT (SWIFT bloques 1, 2, 3, 4 y 5). El Desensamblador usa el esquema de encabezado SWIFT predeterminado para analizar los bloques 1, 2 y 3 únicamente. A continuación se incluye información detallada.  
  
 El algoritmo de resolución de esquema que se ha descrito anteriormente implica que para que funcione la detección de tipo de mensaje dinámico, el esquema de encabezado de SWIFT debe contener campos que el Desensamblador ha promocionado mediante las siguientes propiedades promocionadas (definidas en el A4SWIFT Esquema de propiedades, Microsoft.Solutions.A4SWIFT.Property.PropertySchema):  
  
-   **A4SWIFT_MessageType**  
  
-   **A4SWIFT_MessageType2** (opcional si **A4SWIFT_MessageTypes** se utiliza)  
  
-   **A4SWIFT_SecondaryMessageType** (opcional)  
  
 Para obtener más información sobre estas y otras propiedades promocionadas, consulte [A4SWIFT_ * las propiedades promocionadas](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).  
  
> [!NOTE]
>  Si establece el esquema de encabezado de SWIFT en **ninguno**, debe especificar un esquema de intercambio completo para la **esquema de intercambio de SWIFT** propiedad. En este caso, el Desensamblador usa el esquema de intercambio especificado para analizar todos los mensajes que recibe de A4SWIFT. Es decir, deshabilitar la resolución de esquema dinámico y configurar la canalización para recibir sólo los mensajes cuyo tipo coincide con el esquema de intercambio especificado.  
  
 A4SWIFT instala un esquema de encabezado SWIFT predeterminado (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) que puede analizar los datos de encabezado estándar SWIFT y tiene las propiedades promocionadas necesarias para facilitar la resolución de esquemas dinámico.  
  
 El esquema de encabezado SWIFT predeterminado tiene los siguientes campos promocionados:  
  
-   **SWIFTHeader/ApplicationHeaderBlock_Input/MessageType**. El Desensamblador promociona esto mediante la **A4SWIFT_MessageType** propiedad.  
  
-   **SWIFTHeader/ApplicationHeaderBlock_Output/MessageType**. El Desensamblador promociona esto mediante la **A4SWIFT_MessageType2** propiedad.  
  
-   **SWIFTHeader/UserHeaderBlock/ValidationFlag_119**. El Desensamblador promociona esto mediante la **A4SWIFT_MessageType** propiedad.  
  
 El Desensamblador usa **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** de forma predeterminada como el esquema de encabezado si establece propiedades de configuración del esquema de encabezado de SWIFT y esquema de intercambio de SWIFT en " None".  
  
## <a name="swift-assembler"></a>Ensamblador SWIFT  
 Al igual que el Desensamblador SWIFT, el ensamblador SWIFT tiene la capacidad de detectar el tipo de mensaje de un mensaje saliente y cargar el esquema apropiado necesario para serializar el mensaje dinámicamente. Esta característica permite configurar una sola canalización utilizando el ensamblador de SWIFT para procesar los mensajes de SWIFT de cualquier tipo de mensaje SWIFT. A diferencia del ensamblador de archivo sin formato nativo de BizTalk, el ensamblador SWIFT no requiere crear una canalización de envío independiente para cada tipo de mensaje que podría encontrar A4SWIFT.  
  
 Resolución de esquema dinámico en el ensamblador SWIFT es mucho más fácil que en el Desensamblador SWIFT porque el ensamblador realiza el trabajo de serialización de XML a formato de archivo sin formato SWIFT. El código XML que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona para el ensamblador de SWIFT para serialización contiene el esquema y el tipo de información del mensaje, que puede utilizar el ensamblador SWIFT directamente para cargar el esquema apropiado para la serialización. Por lo tanto, el ensamblador SWIFT no tiene ninguna capacidad de configuración para los esquemas de encabezado y el intercambio: siempre se utiliza el esquema especificado en el XML que serializará.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con el Desensamblador SWIFT y de ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)