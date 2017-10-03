---
title: "Estado de intercambio y el informe de estado de confirmación detalles | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebba4af5-6dff-4bb8-9c63-739ef49bbbb8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cc596a99d1a49b01ccc417abccb73d12ed34ad5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interchange-status-and-ack-details-status-report"></a>Detalles de la confirmación y del estado del intercambio (informe de estado)
Este informe de estado muestra detalles de un intercambio, así como de su confirmación (técnica) del intercambio y de las confirmaciones funcionales correlacionadas. Mostrar este informe con el botón secundario de un intercambio en el informe de estado de confirmación y del intercambio y, a continuación, haga clic en **detalles de confirmación y del estado de intercambio**.  
  
 Este informe proporciona las siguientes vistas diferencias para el intercambio y las confirmaciones correlacionadas:  
  
## <a name="interchange-status"></a>Estado del intercambio  
 En esta vista se incluye una tabla donde se muestran los valores de los campos siguientes:  
  
-   Id. de entidad remitente  
  
-   Id. de entidad receptora  
  
-   Id. de control  
  
-   Nombre de la entidad receptora  
  
-   Nombre de entidad remitente  
  
-   Dirección  
  
-   Fecha y hora de intercambio  
  
    > [!NOTE]
    >  Para los documentos recibidos, si la fecha especificada en el intercambio se encuentra en formato AAMMDD y AA es mayor o igual a 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mostrará el año como 19AA. Si la fecha es inferior a 75, se mostrará como 20AA.  
    >   
    >  Por ejemplo, si recibe un intercambio que contiene el valor 991113 en ISA09, la fecha de intercambio se indicará en el informe como 11/13/1999.  
  
-   Número de grupos  
  
-   Id. de puerto  
  
-   Estado del intercambio  
  
-   Tipo de codificación EDI  
  
-   Id. de correlación del conjunto de transacciones  
  
 Si hay una confirmación técnica habilitada para una entidad como receptora de un intercambio (en la página Configuración de la validación y el procesamiento de confirmación del cuadro de diálogo Propiedades de EDI), BizTalk Server espera que se devuelva una confirmación técnica (intercambio) en respuesta al intercambio que envía. Cuando crea inicialmente una entrada de estado de intercambio para un intercambio de salida, especificará Confirmación esperada en el campo Estado de intercambio. Cuando recibe una confirmación técnica y la correlaciona con el intercambio original, actualizará este campo para indicar que ha recibido la confirmación.  
  
## <a name="interchange-ack-status"></a>Estado de confirmación del intercambio  
 En esta vista se muestran valores de estado para una confirmación del intercambio (técnica):  
  
-   Identificador de control de intercambio de confirmación  
  
-   Entidad receptora.  
  
-   Entidad remitente  
  
-   Dirección  
  
-   Fecha de intercambio de confirmación  
  
-   Hora de intercambio de confirmación  
  
-   Estado de confirmación  
  
-   Código de estado  
  
-   Código de nota de confirmación 1  
  
-   Código de nota de confirmación 2  
  
## <a name="functional-acks"></a>Confirmaciones funcionales  
 En esta vista se muestran valores de estado para una confirmación funcional:  
  
-   Número de control de grupo  
  
-   Entidad receptora.  
  
-   Entidad remitente  
  
-   Dirección  
  
-   Estado  
  
-   Código de estado  
  
-   Código Id. funcional  
  
-   Recuento de TS  
  
-   Identificador de control de intercambio de confirmación  
  
-   Fecha de intercambio de confirmación  
  
-   Hora de intercambio de confirmación  
  
-   Número de conjuntos de transacciones entregados  
  
-   Número de conjuntos aceptados  
  
-   ErrorCode 1  
  
-   ErrorCode 2  
  
-   ErrorCode 3  
  
-   ErrorCode 4  
  
-   ErrorCode 5  
  
-   Hora de recepción