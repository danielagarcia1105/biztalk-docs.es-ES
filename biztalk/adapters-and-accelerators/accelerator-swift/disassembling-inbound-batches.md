---
title: Desensamblar lotes entrantes con SWIFT | Documentos de Microsoft
description: Debatch mensaje entrante y personalizar esquemas para procesamiento por lotes utilizando el Acelerador de SWIFT de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11cb5672-1155-4648-b1fd-c9a3bc30e351
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f14a199e3422a45235727d2d16fc1464e2e4927
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="disassemble-inbound-batches"></a>Desensamblar lotes entrantes

## <a name="debatch-inbound-message"></a>Debatch mensaje entrante
El Desensamblador SWIFT es capaz de anulando entrante en el que procesa o desensambla lotes entrantes (archivos o mensajes que contienen varios mensajes SWIFT). Habilitar anulando entrantes mediante la propiedad de configuración de SWIFT Desensamblador del mismo nombre. Después de habilitar anulando entrantes, el Desensamblador SWIFT espera a que todos los mensajes que recibe para los lotes que incluyen varios mensajes SWIFT. Un lote puede o no incluir un elemento envelope de lote (un encabezado de lote y un finalizador de lote), y cada mensaje SWIFT individual dentro de un lote puede o no incluir un sobre de mensaje (un encabezado del mensaje y un finalizador de mensaje). Puede configurar estos atributos de lote (formatos) con las siguientes propiedades de configuración de SWIFT Desensamblador:  
  
-   Esquema de encabezado de lote  
  
-   Esquema de finalizador de lote  
  
-   Esquema de encabezado de mensaje  
  
-   Esquema de finalizador de mensaje  
  
    > [!NOTE]
    >  Establecer cualquiera de estas propiedades en "None" indica que el lote entrante no incluye esa parte concreta.  
  
 El Desensamblador SWIFT espera que todos los lotes de entrada tiene la estructura siguiente:  
  
 **Encabezado de lote**  
  
 **Encabezado de mensaje**  
  
 **Intercambio/mensaje SWIFT (SWIFT bloques 1 a 5)**  
  
 **Finalizador de mensaje**  
  
 **Finalizador de lote**  
  
 Dentro de esta estructura, puede considerar un "bloque de mensajes" como el **finalizador de mensaje del encabezado del mensaje: intercambio de SWIFT:** partes. Los mensajes SWIFT varios en un lote constituye una serie de bloques de mensajes de varias"". El encabezado de lote, el encabezado del mensaje, el finalizador de mensaje y el finalizador de lote son opcionales, pero deben ser coherente entre repeticiones.  
  
> [!NOTE]
>  No confunda el sobre del mensaje (encabezado del mensaje y el finalizador de mensaje) con los bloques de encabezado y finalizador SWIFT. En el contexto de lotes, debería ver el mensaje SWIFT (intercambio), incluidos los bloques de encabezado y finalizador SWIFT, como una unidad (atómica) holística. En este contexto, el encabezado del mensaje y el finalizador de mensaje hacen referencia a la envoltura que encapsula cada mensaje SWIFT en un lote.  
  
 Para expresar esta estructura y sus opciones, su capacidad de repetición más formalmente, tenga en cuenta cómo [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] define un lote:  
  
-   **Encabezado de lote** se representa mediante **servidor cabeza de puente**  
  
-   **Encabezado de mensaje** se representa mediante **AG**  
  
-   **Intercambio de SWIFT** se representa mediante **SI**  
  
-   **Finalizador de mensaje** se representa mediante **MT**  
  
-   **Procesar por lotes finalizador** representado por **BT**.  
  
 La expresión que representa la estructura de lote esperado es como sigue:  
  
 `[BH] ([MH] SI [MT])* [BT]  `
  
 Los corchetes ( `[ ] ` ) indican que el elemento es opcional. El asterisco (**\***) indica que el bloque es repetible. Persona que crea el lote de mensajes debe usar el encabezado del mensaje (**AG**) y el finalizador (**MT**) forma coherente en cada repetición de (`[MH] SI [MT]`).  
  
 El Desensamblador SWIFT es capaz de procesar un lote entrante que obedece la estructura anterior, dado que cada parte de la estructura se ajusta a un esquema de archivo sin formato. Sin embargo, si no usa el lote opcional encabezado y finalizador y encabezado y finalizador de mensaje, el mensaje no se ajustará a esos esquemas. Como resultado, un lote que contiene solo de los mensajes de SWIFT consecutivos tendrá el esquema de encabezado de lote, esquema de finalizador de lote, esquema de encabezado de mensaje y propiedades de esquema de finalizador de mensaje establecida en "None".  

## <a name="customize-schemas-for-batching"></a>Personalizar esquemas para procesar por lotes  
 Puede personalizar los esquemas para el lote encabezado y finalizador y encabezado y finalizador de mensaje. Un ejemplo es el siguiente lote:  
  
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
  
 Para controlar este tipo de lote, establecería las propiedades del esquema para el lote como sigue:  
  
-   Establezca la propiedad de esquema de encabezado de lote a un esquema de archivo sin formato que analiza un número (número de mensajes) delimitado por retorno de carro.  
  
-   Establece el esquema de finalizador de mensaje en un esquema de archivo sin formato que analiza un único símbolo $ y un retorno de carro.  
  
-   Los esquemas de sobres restantes (esquema de finalizador de lote y esquema de encabezado de mensaje) se establece en None.  
  
 Puede configurar el Desensamblador SWIFT, que procesa casi cualquier lote de mensaje SWIFT mediante la creación y especificar la combinación adecuada de esquemas de sobres de archivo sin formato. Esta funcionalidad es muy flexible.  
  
 El Desensamblador SWIFT siempre intenta completar el procesamiento de un lote completo, incluso cuando encuentra errores durante el proceso. Esto le permite recopilar y notificar errores tantos como sea posible a la vez. Para llevar a cabo esta "esfuerzo" heurística, el Desensamblador SWIFT debe realizar ciertas decisiones y suposiciones al seleccionar el esquema que se utilizará al encontrar un nuevo elemento, o si se produce un error de análisis. Seleccionar el esquema correcto no siempre es posible dependiendo de la naturaleza y la ubicación de un error de análisis y la ambigüedad/similitud entre esquemas de sobres y los esquemas de intercambio SWIFT. En algunos casos, puede minimizar la posibilidad de seleccionar un esquema incorrecto mediante esquemas de sobres bien diseñada. Si el Desensamblador encuentra un error de análisis irrecuperable o el Desensamblador no puede determinar el esquema correcto, el Desensamblador se producirá un error del lote sin tener que procesar los datos restantes.  
  
 Cuando **entrada anulando** es **habilitado** (establecido en **True**), el Desensamblador SWIFT analiza el lote con los esquemas especificados para la envoltura de lote (esquema de encabezado de lote y esquema de finalizador de lote) y sobre del mensaje (esquema de encabezado de mensaje y esquema de finalizador de mensaje), así como el esquema especificado para el análisis de los mensajes SWIFT (intercambios) en el lote. Para los mensajes de SWIFT en el lote, el tipo de mensaje y el esquema pueden dinámicamente detectar y cargar en la misma manera que los mensajes de lote no son únicos (mediante la especificación de un esquema de encabezado de SWIFT). Para obtener más información acerca de cómo el Desensamblador SWIFT realiza la resolución de esquemas, vea [detección dinámica de tipo de mensaje y la resolución de esquema](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md).  
  
 El Desensamblador SWIFT analiza y valida cada mensaje SWIFT en un proceso por lotes entrante de forma individual. Realiza el siguiente lote de secuencia de procesamiento:  
  
1.  Analiza el encabezado de lote si se ha especificado el esquema de encabezado de lote.  
  
2.  Analiza el encabezado del mensaje sobre si se ha especificado el esquema de encabezado de mensaje.  
  
3.  Analiza el intercambio SWIFT (mensaje).  
  
4.  Valida el mensaje SWIFT con las restricciones XML si ha habilitado la validación de XML.  
  
5.  Valida el mensaje SWIFT según las directivas del BRE (reglas de red y el uso SWIFT) si ha habilitado la validación de BRE.  
  
6.  Analiza el finalizador de sobres de mensaje si no se especifica el esquema de finalizador de mensaje.  
  
7.  Repite los pasos 2 a 6 hasta que el Desensamblador no encuentra ningún mensaje más en el lote.  
  
8.  Analiza el finalizador del lote si se ha especificado el esquema de finalizador por lotes.  
  
 Puede configurar el Desensamblador SWIFT para realizar diferentes operaciones con los datos del lote que analiza y se valida con las siguientes propiedades de configuración de SWIFT Desensamblador:  
  
-   El **fragmentación** propiedad determina si el Desensamblador SWIFT debería publicar cada mensaje en el lote de la base de datos de cuadro de mensajes individualmente (es decir, para cada mensaje, después de cada aparición del paso 6 anterior), o si debería Complete cada uno de los pasos 1 a 8 y, a continuación, publicar el lote completo, en forma nativa (copia exacta de entrada), como un solo mensaje a la base de datos de cuadro de mensajes. Establece **fragmentación** a **True** para habilitar la fragmentación y publicar mensajes desde un lote de forma individual. Establece **fragmentación** a **False** para deshabilitar la fragmentación y publicar el lote completo, en forma nativa, como un solo mensaje solo después de procesar el lote completo. Normalmente, establece **fragmentación** a **deshabilitado**para escenarios cuando solo necesite el Acelerador de BizTalk para SWIFT ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]) para analizar y validar los lotes de entrada y no se pudo o reenvíen, en la misma forma que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibirlos. Normalmente establece **fragmentación** a **habilitado** para escenarios en los que desea [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] para transformar o modificar mensajes dentro de un lote después de analizar y validar, o cuando desee [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]para volver a ordenar los mensajes en un lote en un orden distinto de lo que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] en recibidos originalmente. También establece **fragmentación** a **habilitado** para escenarios en los que un lote entrante contiene mensajes que tienen diferentes destinos finales.  
  
-   El **conservar encabezado de lote / conservar lote finalizador** propiedad determina si el Desensamblador SWIFT debe descartar o conservar los datos del lote sobre (encabezado y finalizador) después del análisis se. Si establece **conservar encabezado de lote o conservar el finalizador de lote** a **True**, el Desensamblador publica el elemento de lote correspondiente (XML analizado) en la base de datos de cuadro de mensajes como mensajes individuales. El Desensamblador publica los datos de la parte del cuerpo del mensaje de varias partes. El Desensamblador promociona las propiedades de contexto especial para que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puede correlacionar estos mensajes para el lote que se obtuvieron de y la posición ordinal que se encontraban en el lote (primera posición para el encabezado de lote, última posición para el finalizador de lote). Si establece **conservar encabezado de lote o conservar el finalizador de lote** a **False**, el Desensamblador descarta el elemento de lote correspondiente (datos analizados) después del análisis.  
  
    > [!NOTE]
    >  Estas propiedades de configuración son válidas solamente cuando está habilitada la fragmentación (**fragmentación** establecido en **True**). Cuando se deshabilita la fragmentación, el Desensamblador publica una copia exacta del lote completo, en forma nativa, la base de datos de cuadro de mensajes, lo que configuración de conservación es irrelevante (*todo* se conserva).  
  
-   El **conservar encabezado del mensaje** / **conservar el finalizador de mensaje** propiedad determina si el Desensamblador SWIFT debe descartar o conservar los sobres de mensaje (mensaje encabezados y finalizadores) después del análisis de ellos. Si establece **conservar encabezado del mensaje o conservar el finalizador de mensaje** a **True**, el Desensamblador publica el elemento de lote correspondiente (XML analizado) en la base de datos de cuadro de mensajes *junto con la mensaje SWIFT individual que contiene*. El Desensamblador publica encabezados de envoltura del mensaje en el **encabezado** partes de mensaje de varias partes. El Desensamblador publica finalizadores de sobres de mensaje en el **finalizador** partes de mensaje de varias partes. El Desensamblador publica el mensaje SWIFT contenido en el sobre del mensaje en el **cuerpo** parte del mismo mensaje de varias partes. El Desensamblador promociona las propiedades de contexto especial para que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puede correlacionar estos mensajes para el lote que proceden y la posición ordinal que se encontraban en el lote. Si establece **conservar encabezado del mensaje o conservar el finalizador de mensaje** a **False**, el Desensamblador descarta el elemento de lote correspondiente (datos analizados) después del análisis.  
  
    > [!NOTE]
    >  Estas propiedades de configuración son válidas solamente cuando está habilitada la fragmentación (**fragmentación** establecido en **True**). Cuando se deshabilita la fragmentación, el Desensamblador publica una copia exacta del lote completo, en forma nativa, la base de datos de cuadro de mensajes, lo que configuración de conservación es irrelevante (*todo* se conserva).  
  
 Para obtener más información sobre cada propiedad de configuración, así como otra información de uso y la configuración, consulte [propiedades de configuración de SWIFT Desensamblador](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md). Para obtener más información acerca de la publicación de la base de datos de cuadro de mensajes y mensajes de varias partes, vea la Ayuda de BizTalk Server.  
  
## <a name="next-step"></a>Paso siguiente
  
[Propiedades promocionadas relacionadas con los lotes](batch-related-promoted-properties.md)
