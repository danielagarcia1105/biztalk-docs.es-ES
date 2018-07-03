---
title: EDI y AS2 de informes de estado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9e58b29-9be0-41d6-ad35-1aae28e1a784
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a109398f4b3bff99ce7f45493839df6c3e5320f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993141"
---
# <a name="edi-and-as2-status-reporting"></a>Informes de estado de EDI y AS2
Los informes de estado de EDI permiten que el personal de operaciones realice el seguimiento de las transmisiones EDI y AS2. Si están habilitados, los informes de estado proporcionan información completa sobre el estado de la transacción de intercambio de un documento, incluidos el intercambio y las confirmaciones correlacionadas. Estos informes proporcionan datos sobre el procesamiento de la recepción, la validación, el proceso por lotes y la confirmación de los mensajes EDI y AS2.  
  
 Se pueden usar para obtener el estado de los intercambios pendientes y sin confirmar, los intercambios completos, los escenarios de error o escenarios empresariales. Estos informes permiten llevar a cabo lo siguiente:  
  
- Confirmar la recepción de intercambios  
  
- Enumerar intercambios salientes en espera de confirmación  
  
- Enumerar todos los intercambios rechazados recibidos  
  
- Enumerar intercambios salientes que figuran como rechazados o aceptados parcialmente.  
  
  Los datos incluidos en los informes de estado se obtienen de los segmentos de control de intercambios, como ISA, TA1, GS, UNB y UNG (con la excepción del estado de confirmación funcional).  
  
  **Interfaz de usuario de informes de estado**  
  
  Los informes de estado de EDI y AS2 están disponibles en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Desde el **concentrador de grupo** página de la **grupo de BizTalk** nodo, dispone de vínculos al intercambio EDI y estado de confirmación correlacionado, estado del lote y el mensaje de AS2 y MDN correlacionado. Cada uno de estos informes proporciona una gama de parámetros de estado que pueden incluirse o excluirse de una expresión de consulta, lo que permite generar el informe de estado que necesite.  
  
  Además de ver el estado de un intercambio EDI, también se pueden ver los conjuntos de transacciones de un intercambio. Para ello, habilite el almacenamiento de cargas de mensajes en las tablas de EDI de la base de datos de seguimiento (BizTalkDTADb). Estos conjuntos de transacciones pueden verse mediante el comando de detalles de vista en la interfaz de usuario de los informes de estado.  
  
  También se pueden almacenar mensajes AS2 entrantes o salientes, así como MDN en la base de datos sin repudio. Para ver los conjuntos de transacciones o los mensajes AS2, haga clic con el botón secundario en el mensaje del informe de estado y seleccione el comando adecuado.  
  
  **Componentes de informes de estado**  
  
  Los componentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que intervienen en los informes de estado son los siguientes:  
  
- Desensamblador EDI en la canalización de recepción EDI que crea y actualiza las entradas de estado en el almacén de datos correspondientes a un intercambio entrante.  
  
- Ensamblador EDI en la canalización de envío EDI que crea y actualiza las entradas de estado en el almacén de datos correspondientes a un intercambio saliente.  
  
- Los almacenes de datos que guardan las entradas de los informes de estado. Se trata de la base de datos de importación principal de BAM para el seguimiento de datos y la tabla de contenido del mensaje EDI de la base de datos de seguimiento de BizTalk (BizTalkDTADb) para conjuntos de transacciones EDI o contenido de mensajes AS2.  
  
- Informes de estado la interfaz de usuario en el **concentrador de grupo** página de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, que se usa para mostrar datos de informes de estado  
  
- Las opciones de propiedad de acuerdo y de propiedad de acuerdo de reserva de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], que se usan para habilitar y configurar los informes de estado.  
  
- Servidor de análisis DTA y SQL que aprovecha la infraestructura de BAM.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configuración de informes de estado de EDI y AS2](../core/configuration-of-edi-and-as2-status-reporting.md)  
  
-   [Tipos de informes de estado AS2 y EDI](../core/types-of-edi-and-as2-status-reports.md)  
  
-   [Datos almacenados para informes de estado de EDI y AS2](../core/data-stored-for-edi-and-as2-status-reports.md)  
  
-   [Cómo se almacenan los datos correspondientes a informes de estado de EDI y AS2](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)