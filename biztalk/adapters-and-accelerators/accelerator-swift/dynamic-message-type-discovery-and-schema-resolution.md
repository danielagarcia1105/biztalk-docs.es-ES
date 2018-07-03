---
title: Detección de tipos de mensaje dinámicos y resolución de esquemas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic schema resolution
- disassembler, code sample
- schemas, dynamic resolution
- assembler, message types
- disassembler, message types
- code samples, disassembler
ms.assetid: 5f71d3df-a37e-4ef2-9055-b614656203e9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5bbc5f8afaa8c08da04e9eab1b476e5884b2e6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986413"
---
# <a name="dynamic-message-type-discovery-and-schema-resolution"></a>Detección de tipos de mensaje dinámicos y resolución de esquemas
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] habilita la resolución de detección y el esquema del tipo de mensaje dinámicos en el ensamblador y desensamblador de SWIFT.  
  
## <a name="swift-disassembler"></a>Desensamblador de SWIFT  
 El Desensamblador de SWIFT (DASM) tiene la capacidad para detectar el tipo de mensaje de un mensaje recibido y cargar el esquema correspondiente necesario para analizar el mensaje dinámicamente. La mayor ventaja de esta característica es que puede configurar una sola canalización mediante el Desensamblador SWIFT para procesar los mensajes de SWIFT de cualquier tipo de mensaje SWIFT. Al contrario que el Desensamblador de archivo sin formato nativo de BizTalk, el Desensamblador de SWIFT no requiere que crear una canalización de recepción independiente para cada tipo de mensaje que pueden surgir A4SWIFT.  
  
 Puede usar la detección de tipos de mensaje dinámicos si asume que, en la mayoría de los casos, todos los mensajes que recibe de un sistema comenzará con datos de encabezado de una estructura homogénea. Dentro del encabezado de datos son campos que revelan el tipo de mensaje del mensaje. Para los mensajes de SWIFT, datos de encabezado se componen de bloques de mensajes SWIFT 1, 2 y 3, con información de tipo de mensaje contenida en el bloque 2 (conocido como el encabezado de la aplicación).  
  
 El componente de SWIFT DASM puede procesar todos los "único" (no procesar por lotes) SWIFT mensajes de fábrica sin necesidad de realizar cualquiera de las propiedades que se va a establecer. De forma predeterminada, no se establecen los esquemas de intercambio de SWIFT y SWIFT encabezado; Sin embargo, el componente de SWIFT DASM utilizará el esquema de encabezado de SWIFT presente en Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll para detectar dinámicamente el tipo de mensaje SWIFT y procesar los mensajes. Además, BRE y validación de XML se habilitan de forma predeterminada por lo que se validarán completamente cualquier mensaje que procesa. Establecer la propiedad de esquema de encabezado de SWIFT para que apunte al encabezado de SWIFT en RuntimeSchemas.dll también dará como resultado el mismo comportamiento que anteriormente.  
  
 Cuando la propiedad de configuración de esquema de encabezado de SWIFT para el Desensamblador de SWIFT se establece en "None" (predeterminado), el Desensamblador resuelve dinámicamente y carga el esquema apropiado mediante los pasos siguientes:  
  
1. Usa el esquema de encabezado especificado por el usuario (especificado por la propiedad de configuración de esquema de encabezado de SWIFT) para analizar el principio (encabezado) del mensaje de recepción.  
  
2. Inspecciona el resultante "encabezado XML" para el campo de propiedad promocionada A4SWIFT_MessageType. Si este campo no existe, se utiliza el valor del campo como el "tipo de mensaje" y continúa con el paso 4. Si el campo no existe, pasa al paso 3.  
  
3. Inspecciona el encabezado XML para el campo de propiedad promocionada A4SWIFT_MessageType2 (esperado si el Desensamblador no encuentra el campo A4SWIFT_MessageType). Usa el valor del campo A4SWIFT_MessageType2 como el "tipo de mensaje".  
  
4. Si el "tipo de mensaje" identificado en el paso 2 o 3 es "574", el Desensamblador de SWIFT comprueba si el tipo de mensaje "574" está en la lista de tipos de mensaje especificado en la propiedad de configuración de la lista de mensajes de tipo doble (que es una propiedad del desensamblador). En caso afirmativo, continúa con el paso 5. Si no, los pasa al paso 6.  
  
5. Inspecciona el XML del encabezado para el campo de propiedad promocionada A4SWIFT_SecondaryMessageType. Si este campo no existe, el Desensamblador usa el valor del campo (por ejemplo, "IRSLST") como el "mensaje subtipo" y lo anexa al "tipo de mensaje", por ejemplo, "574_IRSLST".  
  
   > [!IMPORTANT]
   >  La explicación dada para el paso 5 es una simplificación de lo que el Desensamblador de SWIFT hace para evaluar el subtipo del mensaje. En realidad, el Desensamblador de SWIFT utiliza el siguiente algoritmo para determinar si un tipo de mensaje tiene subtipos y si es así, lo que es el siguiente subtipo.  
  
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
  
6. Ahora, el Desensamblador conoce el tipo de mensaje, y puede formar el nombre del esquema de intercambio mediante la concatenación de algunos prefijos y sufijos (por ejemplo, "MT" en el prefijo para realizar "MT574_IRSLST") de nombres de esquema fijo.  
  
7. Carga el esquema de intercambio (por nombre) y analiza el mensaje completo, **comenzando desde el principio**, mediante el esquema cargado (Esto significa que el Desensamblador analiza los datos de encabezado dos veces: una vez con el esquema de encabezado y nuevo utilizando el principio del esquema de intercambio). El esquema de intercambio debe ser capaz de analizar el mensaje completo, incluido el encabezado.  
  
   > [!NOTE]
   >  El Desensamblador puede utilizar todos los esquemas de mensaje SWIFT A4SWIFT para analizar todo el intercambio SWIFT (SWIFT bloques 1, 2, 3, 4 y 5). El Desensamblador usa el esquema predeterminado de encabezados de SWIFT para analizar los bloques 1, 2 y 3 solo. A continuación se incluye información detallada.  
  
   El algoritmo de resolución de esquema que se ha descrito anteriormente implica que para que funcione la detección de tipo de mensaje dinámicos, el esquema de encabezado de SWIFT debe contener los campos que se ha promovido el Desensamblador mediante las siguientes propiedades promocionadas (definidas en el A4SWIFT Esquema de propiedades, Microsoft.Solutions.A4SWIFT.Property.PropertySchema):  
  
- **A4SWIFT_MessageType**  
  
- **A4SWIFT_MessageType2** (opcional si **A4SWIFT_MessageTypes** se utiliza)  
  
- **A4SWIFT_SecondaryMessageType** (opcional)  
  
  Para obtener más información sobre estas y otras propiedades promocionadas, consulte [A4SWIFT_ * las propiedades promocionadas](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).  
  
> [!NOTE]
>  Si establece el esquema de encabezado de SWIFT **ninguno**, debe especificar un esquema de intercambio completo para el **esquema de intercambio de SWIFT** propiedad. En este caso, el Desensamblador usa el esquema de intercambio especificado para analizar todos los mensajes que recibe de A4SWIFT. Es decir, deshabilitar la resolución de esquema dinámico y configurar la canalización para recibir sólo los mensajes cuyo tipo coincide con el esquema de intercambio especificado.  
  
 A4SWIFT instala un esquema de encabezado SWIFT predeterminado (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) que puede analizar los datos de encabezado estándar SWIFT y tiene las propiedades promocionadas necesarias para facilitar la resolución de esquema dinámico.  
  
 El esquema de encabezado SWIFT predeterminado tiene los siguientes campos promocionados:  
  
- **SWIFTHeader/ApplicationHeaderBlock_Input/MessageType**. El Desensamblador promociona esto mediante la **A4SWIFT_MessageType** propiedad.  
  
- **SWIFTHeader/ApplicationHeaderBlock_Output/MessageType**. El Desensamblador promociona esto mediante la **A4SWIFT_MessageType2** propiedad.  
  
- **SWIFTHeader/UserHeaderBlock/ValidationFlag_119**. El Desensamblador promociona esto mediante la **A4SWIFT_MessageType** propiedad.  
  
  El Desensamblador usa **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** de forma predeterminada como el esquema de encabezado si establece las propiedades de configuración de esquema de encabezado de SWIFT y esquema de intercambio de SWIFT " None".  
  
## <a name="swift-assembler"></a>Ensamblador de SWIFT  
 Al igual que el Desensamblador de SWIFT, el ensamblador de SWIFT tiene la capacidad de detectar el tipo de mensaje de un mensaje saliente y cargar el esquema adecuado necesario para serializar el mensaje dinámicamente. Esta característica le permite configurar una única canalización mediante el ensamblador de SWIFT para procesar los mensajes de SWIFT de cualquier tipo de mensaje SWIFT. Al contrario que el ensamblador de archivo sin formato nativo de BizTalk, el ensamblador de SWIFT no requiere crear una canalización de envío independiente para cada tipo de mensaje que pueden surgir A4SWIFT.  
  
 Resolución de esquema dinámico en el ensamblador de SWIFT es mucho más sencilla que en el Desensamblador de SWIFT porque el ensamblador realiza el trabajo de serialización de XML a formato de archivo sin formato SWIFT. El XML que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ofrece para el ensamblador de SWIFT para serialización contiene el esquema y el tipo de información del mensaje, que puede usar el ensamblador de SWIFT directamente para cargar el esquema apropiado para la serialización. Por lo tanto, el ensamblador de SWIFT no tiene ninguna capacidad de configuración para los esquemas de encabezado y el intercambio: siempre utiliza el esquema especificado en el XML que serializará.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con el desensamblador y el ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)