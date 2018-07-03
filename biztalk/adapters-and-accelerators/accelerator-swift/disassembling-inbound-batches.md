---
title: Desensamblar lotes entrantes con SWIFT | Microsoft Docs
description: Desagrupar los mensajes entrantes y personalizar los esquemas por lotes mediante el Acelerador de SWIFT de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11cb5672-1155-4648-b1fd-c9a3bc30e351
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f234ca9c867d978216972f8359c77de88aeebfa8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976245"
---
# <a name="disassemble-inbound-batches"></a>Desensamblar lotes entrantes

## <a name="debatch-inbound-message"></a>Desagrupar los mensajes entrantes
El Desensamblador de SWIFT es capaz de desagrupación entrante en el que se procesa o Desensambla los lotes de entrada (archivos o mensajes que contienen varios mensajes SWIFT). Habilitar la desagrupación de entrada mediante la propiedad de configuración del desensamblador de SWIFT del mismo nombre. Después de habilitar la desagrupación de entrada, el Desensamblador de SWIFT espera a que todos los mensajes que recibe para los lotes que incluyen varios mensajes SWIFT. Un lote puede o no incluir un elemento envelope de lote (un encabezado de lote y un finalizador de lote) y cada mensaje SWIFT individual dentro de un lote puede o no incluir un sobre de mensaje (un encabezado de mensaje y un finalizador de mensaje). Puede configurar estos atributos de lote (formatos) con las siguientes propiedades de configuración del desensamblador de SWIFT:  
  
- Esquema de encabezado de lote  
  
- Esquema de finalizador de lote  
  
- Esquema de encabezado de mensaje  
  
- Esquema de finalizador de mensaje  
  
  > [!NOTE]
  >  Si establece cualquiera de estas propiedades en "None" indica que el lote entrante no incluye esa parte concreta.  
  
  El Desensamblador de SWIFT espera que todos los lotes de entrada para tener la siguiente estructura:  
  
  **Encabezado de lote**  
  
  **Encabezado de mensaje**  
  
  **SWIFT/mensaje de intercambio (SWIFT bloques de 1 a 5)**  
  
  **Finalizador de mensaje**  
  
  **Finalizador de lote**  
  
  Dentro de esta estructura, puede considerar un "bloque de mensajes" sea el **finalizador de mensaje de encabezado del mensaje: intercambio de SWIFT:** partes. Los mensajes SWIFT múltiples en un lote constituye una serie de varias "bloques de mensajes". El encabezado de lote, encabezado de mensaje, finalizador de mensaje y finalizador del proceso por lotes son opcionales, pero deben ser coherentes en las repeticiones.  
  
> [!NOTE]
>  No confunda el sobre del mensaje (mensaje de encabezado y finalizador de mensaje) con los bloques de encabezado y finalizador SWIFT. En el contexto de lotes, debería ver el mensaje SWIFT (intercambio), incluidos los bloques de encabezado y finalizador SWIFT, como una unidad (atomic) holística. En este contexto, el encabezado del mensaje y el finalizador de mensaje hacen referencia a la envoltura que encapsula cada mensaje SWIFT en un lote.  
  
 Para expresar esta estructura, sus opciones y su capacidad de repetición más formalmente, tenga en cuenta cómo [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] define un lote:  
  
- **Encabezado de lote** viene dado por **BH**  
  
- **Encabezado de mensaje** viene dado por **MH**  
  
- **Intercambio de SWIFT** viene dado por **SI**  
  
- **Finalizador de mensaje** viene dado por **MT**  
  
- **Finalizador de batch** viene dado por **BT**.  
  
  La expresión que representa la estructura del lote esperado es como sigue:  
  
  `[BH] ([MH] SI [MT])* [BT]  `
  
  Los corchetes ( `[ ] ` ) indican que el elemento es opcional. El asterisco (**\\***) indica que el bloque es repetible. Quienquiera que compila el lote de mensajes debe usar el encabezado del mensaje (*<em>MH</em>*) y el finalizador (*<em>MT</em>*) coherente en cada repetición de (`[MH] SI [MT]`).  
  
  El Desensamblador de SWIFT es capaz de procesar cualquier lote de entrada que sigue la estructura anterior, ya que cada parte de la estructura se ajusta a un esquema de archivo sin formato. Sin embargo, si no usa el lote opcional encabezado y finalizador y encabezado y finalizador de mensaje, el mensaje no se ajustará a esos esquemas. Como resultado, un lote que contiene solo los mensajes de SWIFT consecutivos tendrá el esquema de encabezado de lote, esquema de finalizador de Batch, esquema de encabezado de mensaje y propiedades de esquema de finalizador de mensaje establecida en "None".  

## <a name="customize-schemas-for-batching"></a>Personalizar esquemas para procesar por lotes  
 Puede personalizar los esquemas para el lote de encabezado y finalizador y encabezado y finalizador de mensaje. Un ejemplo es el siguiente lote:  
  
```  
4  
SWIFT Message # 1  
$  
SWIFT Message # 2  
$  
SWIFT Message # 3  
$  
SWIFT Message # 4  
$  
```  
  
 Para controlar este tipo de lote, se establece las propiedades del esquema para el lote como sigue:  
  
- Establezca la propiedad de esquema de encabezado de lote a un esquema de archivo sin formato que analiza un solo número (recuento de mensajes) delimitado por el retorno de carro.  
  
- Establece el esquema de finalizador de mensaje en un esquema de archivo sin formato que analiza un único símbolo $ y un retorno de carro.  
  
- Los esquemas de sobres restantes (esquema de finalizador de lote y esquema de encabezado de mensaje) se establece en None.  
  
  Puede configurar el Desensamblador de SWIFT que procesa cualquier lote de mensajes SWIFT creando y especificando la combinación adecuada de los esquemas de sobres de archivo sin formato. Esta funcionalidad es muy flexible.  
  
  El Desensamblador de SWIFT siempre intenta completar el procesamiento de un lote completo, incluso cuando encuentra errores en el camino. Esto le permite recopilar y notificar tantos errores como sea posible a la vez. Para llevar a cabo esta "mejor esfuerzo" heurística, el Desensamblador de SWIFT debe realizar determinadas decisiones y suposiciones al seleccionar el esquema que se utilizará al encontrar un nuevo elemento, o si se produce un error de análisis. Seleccionar el esquema correcto no siempre es posible según la naturaleza y la ubicación de un error de análisis y la ambigüedad/similitud entre los esquemas de sobres y los esquemas SWIFT intercambio. En algunos casos, puede minimizar la posibilidad de seleccionar un esquema incorrecto mediante el uso de los esquemas de sobres bien diseñada. Si el Desensamblador encuentra un error grave de análisis o el Desensamblador no puede determinar el esquema correcto, el Desensamblador se producirá un error del lote sin procesar los datos restantes.  
  
  Cuando **entrada desagrupación** es **habilitado** (establecido en **True**), el Desensamblador de SWIFT analiza el lote mediante los esquemas especificados para la envoltura de lote (esquema de encabezado de lote y el esquema de finalizador de lote) y el sobre del mensaje (esquema de encabezado de mensaje y esquema de finalizador de mensaje), como el esquema especificado para el análisis de los mensajes SWIFT (intercambios) en el lote. Para los mensajes SWIFT del lote, el tipo de mensaje y el esquema se pueden dinámicamente detectar y cargar en la misma manera que los mensajes con lotes individuales (mediante la especificación de un esquema de encabezado de SWIFT). Para obtener más información acerca de cómo el Desensamblador de SWIFT realiza la resolución de esquemas, vea [detección dinámica de tipos de mensaje y la resolución de esquemas](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md).  
  
  El Desensamblador de SWIFT analiza y valida individualmente cada mensaje SWIFT en un lote de entrada. Lleva a cabo el siguiente lote de secuencia de procesamiento:  
  
1. Analiza el encabezado de lote si se ha especificado el esquema de encabezado de lote.  
  
2. Analiza el encabezado del mensaje sobre si se ha especificado el esquema de encabezado de mensaje.  
  
3. Analiza el intercambio SWIFT (mensaje).  
  
4. Valida el mensaje SWIFT con restricciones de XML si ha habilitado la validación de XML.  
  
5. Valida el mensaje SWIFT según las directivas del BRE (reglas de red y el uso SWIFT) si ha habilitado la validación del BRE.  
  
6. Analiza el finalizador de sobres de mensaje si se especifica el esquema de finalizador de mensaje.  
  
7. Repite los pasos 2 a 6 hasta que el Desensamblador no encuentra más mensajes del lote.  
  
8. Analiza el finalizador del lote si se ha especificado el esquema de finalizador por lotes.  
  
   Puede configurar el Desensamblador de SWIFT para realizar diferentes operaciones con los datos del lote que analiza y se valida con las siguientes propiedades de configuración del desensamblador de SWIFT:  
  
- El **fragmentación** propiedad determina si el Desensamblador de SWIFT debe publicar cada mensaje del lote para la base de datos de cuadro de mensajes individualmente (es decir, para cada mensaje, después de cada aparición del paso 6 anterior), o si debe Complete todos los pasos 1 a 8 y, a continuación, publicar todo el lote, en forma nativa (copia exacta de entrada), como un solo mensaje a la base de datos de cuadro de mensajes. Establece **fragmentación** a **True** para habilitar la fragmentación y publicar mensajes desde un lote de forma individual. Establece **fragmentación** a **False** para deshabilitar la fragmentación y publicar todo el lote, en forma nativa, como un solo mensaje solo después de procesar el lote completo. Normalmente, establece **fragmentación** a **deshabilitado**para escenarios cuando solo necesite el Acelerador de BizTalk para SWIFT ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]) para analizar y validar los lotes de entrada y no se pudo o reenvían, en la misma forma que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibido. Normalmente establece **fragmentación** a **habilitado** para escenarios en los que desea que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] para transformar o modificar mensajes dentro de un lote después de analizar y validar, o cuando desee [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]para volver a ordenar los mensajes en un lote en un orden distinto de lo que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibió originalmente en. Además, establecer **fragmentación** a **habilitado** para escenarios en los que un lote de entrada contiene los mensajes que tienen diferentes destinos finales.  
  
- El **conservar encabezado de lote / conservar Batch finalizador** propiedad determina si el Desensamblador de SWIFT debe descartar o conservar los datos sobre batch (encabezado y finalizador) después de su análisis. Si establece **conservar encabezado de lote o conservar el finalizador de lote** a **True**, el Desensamblador publica el elemento de lote (XML analizado) correspondiente a la base de datos de cuadro de mensajes como mensajes individuales. El Desensamblador publica los datos en la parte del cuerpo del mensaje de varias partes. El Desensamblador promociona las propiedades de contexto especial para que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puede correlacionar estos mensajes para el lote contraerlas y la posición ordinal que se encontraban dentro del lote (primera posición para el encabezado de lote, última posición para el finalizador de batch). Si establece **conservar encabezado de lote o conservar el finalizador de lote** a **False**, el Desensamblador descarta la parte del lote correspondiente (datos analizados) después del análisis.  
  
  > [!NOTE]
  >  Estas propiedades de configuración solo son válidas cuando se habilita la fragmentación (**fragmentación** establecido en **True**). Cuando se deshabilita la fragmentación, el Desensamblador publica una copia exacta de todo el lote, en forma nativa, la base de datos de cuadro de mensajes, por lo que la configuración de preservación es irrelevantes (*todo* se conservan).  
  
- El **conservar el encabezado del mensaje** / **conservar el finalizador de mensaje** propiedad determina si el Desensamblador de SWIFT debe descartar o conservar los sobres de mensajes (encabezados y finalizadores) Después de analizarlos. Si establece **conservar el encabezado del mensaje o conservar el finalizador de mensaje** a **True**, el Desensamblador publica el elemento de lote (XML analizado) correspondiente a la base de datos de cuadro de mensajes *junto con el cada mensaje SWIFT que encapsula*. El Desensamblador publica los encabezados de envoltura del mensaje en el **encabezado** parte del mensaje de varias partes. El Desensamblador publica los finalizadores de sobres de mensaje en el **finalizador** parte del mensaje de varias partes. El Desensamblador publica el mensaje SWIFT contenido en el mensaje en el **cuerpo** parte del mismo mensaje de varias partes. El Desensamblador promociona las propiedades de contexto especial para que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puede correlacionar estos mensajes para el lote contraerlas y la posición ordinal que se encontraban dentro del lote. Si establece **conservar el encabezado del mensaje o conservar el finalizador de mensaje** a **False**, el Desensamblador descarta la parte del lote correspondiente (datos analizados) después del análisis.  
  
  > [!NOTE]
  >  Estas propiedades de configuración solo son válidas cuando se habilita la fragmentación (**fragmentación** establecido en **True**). Cuando se deshabilita la fragmentación, el Desensamblador publica una copia exacta de todo el lote, en forma nativa, la base de datos de cuadro de mensajes, por lo que la configuración de preservación es irrelevantes (*todo* se conservan).  
  
  Para obtener más información sobre cada propiedad de configuración, así como otra información de uso y la configuración, consulte [propiedades de configuración del desensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md). Para obtener más información acerca de la publicación de la base de datos de cuadro de mensajes y mensajes de varias partes, vea la Ayuda de BizTalk Server.  
  
## <a name="next-step"></a>Paso siguiente
  
[Propiedades promocionadas relacionadas con los lotes](batch-related-promoted-properties.md)
