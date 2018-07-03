---
title: Conservar un recibido el intercambio EDI por lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10d21b9b-9684-422a-8948-8bd71a4d5a10
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4883f6c6df9042d40b82138a4d3a871797a5fa1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985781"
---
# <a name="preserving-a-received-batched-edi-interchange"></a>Conservar un intercambio EDI por lotes recibido
> [!NOTE]
>  Todas las opciones de interfaz de usuario mencionadas en este tema están disponibles en el **configuración de Host Local** página (**configuración del receptor** sección) de las pestañas del acuerdo bidireccional en el  **Las propiedades del acuerdo** cuadro de diálogo.  

 Cuando la canalización de recepción EDI conserva un intercambio EDI por lotes de entrada, no se realiza el análisis normal de cada conjunto de transacciones/mensaje en archivos XML intermedios separados. La canalización de recepción EDI procesa el intercambio como un documento sin dividir los conjuntos de transacciones/mensajes. Esto se produce cuando el **opción de procesamiento por lotes de entrada** propiedad está establecida en **conservar intercambio: suspender intercambio en caso de un Error** o **conservar intercambio: suspender conjuntos de transacciones en Error**.  

 **Validación de esquemas**  

 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] valida el sobre de un lote conservado mediante los esquemas por lotes y los esquemas de servicio. El esquema por lotes se utiliza para validar el nodo raíz del mensaje conservado; los esquemas de servicio se utilizan para validar los finalizadores y los encabezados de conjuntos de transacciones, grupos e intercambios. Para obtener más información acerca de los esquemas por lotes, vea [esquemas por lotes de EDI](../core/edi-batch-schemas.md). Para obtener más información sobre los esquemas de servicio, consulte [esquemas de Control y servicio EDI](../core/edi-service-and-control-schemas.md).  

 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] valida los documentos de un intercambio por lotes mediante los esquemas de documentos del proyecto.  

 **Procesamiento de recepción**  

 El desensamblador EDI procesa lotes conservados de la siguiente forma:  

- Cuando el desensamblador EDI procesa un lote para que se conserve, convierte formato de archivo sin formato en XML y agrega X12InterchangeXML y EdifactInterchangeXML como el nodo raíz XML. Esto indica a la canalización de envío que el intercambio por lotes debe conservarse y que los esquemas Edifact_BatchSchema schema o X12_BatchSchema deben usarse para validar el nodo raíz.  

- El desensamblador agrega el atributo DelimiterSetSerializedData al nodo raíz de un mensaje XML por lotes para indicar los separadores que la canalización de envío va a utilizar cuando se genere un intercambio EDI por lotes a partir del mensaje XML. Cuando el XML es un lote conservado, el atributo se rellena mediante la canalización de recepción de los separadores que se utilizaron en el mensaje entrante. Cuando la orquestación por lotes genera el XML por lotes, el atributo se rellena a partir del valor especificado en las propiedades del acuerdo.  

- El desensamblador usa uno de los siguientes espacios de nombres cuando crea un intercambio conservado de codificación XML: `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006/InterchangeXML` o `http://schemas.microsoft.com/BizTalk/EDI/X12/2006/InterchangeXML`.  

- El desensamblador promociona propiedad de contexto `EDI.ReuseEnvelope == True` para identificar el intercambio como conservado. Esto le permite crear un puerto de envío suscrito a todos los intercambios por lotes que se conservan.  

  > [!NOTE]
  >  Un documento HIPAA no se dividirá en subdocumentos si la **opción de procesamiento por lotes de entrada** está establecido en **conservar intercambio**. Esto sucederá incluso si la anotación de interrupción de creación de subdocumento dentro del esquema HIPAA se establece en “Sí”.  

  **Error al procesar**  

  Si ha seleccionado **conservar intercambio: suspender intercambio en caso de un Error** para el **opción de procesamiento por lotes de entrada**, se suspenderá todo el intercambio como resultado de cualquier error. Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suspende el todo el intercambio conservado, la estructura de intercambio y se conservará  el orden de los conjuntos de transacciones dentro del intercambio. En caso de error, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] registra una entrada de error consolidada en el registro de eventos. Esta entrada incluirá cualquier error en los niveles de conjunto de transacciones, grupo funcionar e intercambio.  

  Si ha seleccionado **conservar intercambio: suspender conjuntos de transacciones de un Error** para la opción de procesamiento por lotes entrantes, la recepción EDI colocará cualquier conjunto de transacciones no válido del intercambio y continúe con la creación canalización del intercambio XML. Es necesario que el intercambio XML que se genera vuelva a utilizar los sobres de segmentos de control existentes (ISA, GS, GE e IEA para intercambios con codificación X12 o UNA, UNB, UNG, UNE y UNZ para intercambios con codificación EDIFACT). El intercambio se considerará un documento procesado correctamente, sin embargo, el error se notificará en el visor de eventos y si se genera una confirmación funcional, notificará el error. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] creará una entrada independiente en el registro de eventos para cada conjunto de transacciones que se muestra un error. Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] quita una transacción errónea del conjunto del intercambio, la estructura de intercambio y el orden no puede conservarse. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se actualizará el número de conjuntos de transacciones del intercambio.  

  Las siguientes casos especiales se aplican los conjuntos de transacción suspendidos en caso de error:  

- Si los conjuntos de transacciones en un grupo no son válidos, se suspende cada conjunto de transacciones de forma individual. Sin embargo, los segmentos de control de grupo (sin conjuntos de transacciones, ya que éstos se han colocado) se incluirán en el XML de intercambio generado.  

- Si los conjuntos de transacciones en un intercambio no son válidos, cada conjunto de transacciones se suspende de forma individual. Sin embargo, los segmentos de control de intercambio (sin conjuntos de transacciones ya que éstos se han colocado) se incluirán en el XM L de intercambio generado.  

- Si los segmentos de control de grupo no son válidos, todos los conjuntos de transacciones en el grupo se suspenderán individualmente.  

- Si los segmentos de control de intercambio no son válidos, todos los conjuntos de transacciones en el intercambio se suspenderán individualmente y el XML de intercambio no se generará. Se creará un registro en el visor de eventos para el intercambio rechazado.
