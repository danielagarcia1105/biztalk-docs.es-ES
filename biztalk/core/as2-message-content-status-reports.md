---
title: AS2 Informes de estado del contenido del mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6244aa59-a80d-450b-ab95-9a5e14c0c40e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b2dadb3231136255dcf532e5054c1a6228880f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230492"
---
# <a name="as2-message-content-status-reports"></a>Informes de estado del contenido del mensaje AS2

## <a name="overview"></a>Información general
En estos informes de estado se muestran las propiedades de contexto, los encabezados y la carga de un mensaje AS2 o un MDN. Hay tres informes de estado del contenido del mensaje AS2:  
  
-   Informe de formato de mensaje  
  
-   Informe de formato con descodificación de mensaje  
  
-   Informe de mensaje MDN  
  
 Para ver uno de estos informes con el botón secundario en el informe de estado AS2/MDN un mensaje AS2 y, a continuación, haga clic en **ver formato del mensaje**, **formato descodificado del mensaje vista**, o **vista Mdn Mensaje**. El comando de MDN mostrará el MDN que se correlaciona con el mensaje AS2.  
  
 Todos estos informes se encuentran disponibles solo si ha seleccionado las propiedades "Almacenar mensajes en la base de datos sin repudio" correspondientes de la página Entidad como remitente del mensaje AS2 o la página Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2 de la entidad relacionada. Los comandos almacenan mensajes AS2 o MDN en el formato correspondiente o con formato descodificado en la base de datos de BizTalkDTADb.  
  
 Este informe utiliza el **cuadro de diálogo de propiedades de detalles de mensaje** (vea los detalles de la interfaz de usuario [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) para mostrar los datos de mensaje, con la información dividida en páginas:  
  
|Página|Datos mostrados|  
|----------|--------------------|  
|**General**|Información general acerca del mensaje|  
|**Contexto**|Propiedades de contexto asociadas con este mensaje|  
|**Partes de mensaje**|Carga de documentos individuales dentro de este mensaje. Cada documento se puede ver como texto o binario:<br /><br /> -Vista de formato de texto muestra el contenido del mensaje AS2 o MDN en forma legible, como en un archivo de texto EDI. Esta vista muestra los encabezados AS2, finalizadores EDI y la carga EDI, con cada uno de los segmentos en una línea individual.<br />-La vista formato binario muestra el contenido del mensaje AS2 o MDN en formato de texto sin delimitar y una tabla de representaciones hexadecimales para cada carácter ASCII en el mensaje AS2 o MDN.|