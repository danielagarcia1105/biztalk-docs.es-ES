---
title: 'Lección 2: Enviar un mensaje MT103 que no es válido | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, invalid messages
- submitting, invalid messages
- submitting, MT103 messages
- MT103 messages
- messages, MT103 messages
ms.assetid: 4b070ae1-c400-421a-b2f6-b7b1f22c0e41
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cb8f0539f3a832e3b54a6fa45b300558a8e39a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014885"
---
# <a name="lesson-2-submitting-an-mt103-message-that-is-not-valid"></a>Lección 2: Enviar un mensaje MT103 que no es válido
En esta lección, envíe un mensaje MT103 que no es válido y, a continuación, solucionar el error resultante mediante las herramientas del sistema.  
  
### <a name="to-submit-an-mt103-message-that-is-not-valid"></a>Para enviar un mensaje MT103 que no es válido  
  
1. Copie el archivo MT103_Invalid_Sample.txt desde \< *unidad:*\>\Program Files\Microsoft Acelerador de BizTalk para SWIFT\SDK\Tutorial a \< *unidad* \>: Carpeta \Labs\Inbound\FlatFile. Tenga en cuenta el tiempo que coloque el archivo en la carpeta.  
  
2. Abra \< *unidad:*\>\Labs\Outbound para comprobar que ningún archivo XML correspondiente a MT103_Invalid_Sample.txt está en la carpeta. (El archivo XML correspondiente al mensaje MT103_Sample.txt válido debe ser todavía en esa carpeta.)  
  
3. En el Bloc de notas, abra el archivo MT103_Invalid_Sample.txt en \< *unidad:*\>\Program Files\Microsoft Acelerador de BizTalk para SWIFT\SDK\Tutorial.  
  
4. Iniciar **administración de BizTalk Server**.  
  
5. En la consola de administración de BizTalk Server, expanda **Visor de eventos (Local)** y, a continuación, haga clic en **aplicación**.  
  
6. Busque una entrada de error que tiene un origen del Acelerador de BizTalk para SWIFT y una hora que corresponde a cuando se quita el mensaje no válido en el \< *unidad*\>: carpeta \Labs\Inbound\FlatFile. Haga doble clic en esa entrada de error.  
  
7. En el cuadro de diálogo Propiedades de evento para el error, compruebe en el panel de descripción que se publicó el mensaje con errores en el cuadro de mensajes y que marca el Desensamblador de SWIFT **A4SWIFT_Failed** como **True**. Cierre el cuadro de diálogo Propiedades de evento.  
  
8. En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**y, a continuación, expanda **grupo de BizTalk**. En el **vista** menú, haga clic en **página concentrador de grupo**.  
  
9. En el **información general del grupo** panel, en el **instancias de servicio suspendidas agrupadas** panel, haga clic en **agrupadas por aplicación**.  
  
10. En el **vista previa del resultado de la consulta seleccionada** panel, haga doble clic en la entrada de **MT103_FlatFile_ReceivePort**.  
  
11. En el cuadro de diálogo Detalles del servicio, haga clic en el **mensajes** ficha. Haga doble clic en la entrada para el que es el nombre del servicio **MT103_FlatFile_ReceivePort**.  
  
12. En el cuadro de diálogo Detalles del mensaje, haga clic en **cuerpo** en el panel izquierdo.  
  
13. Compruebe que el mensaje que se muestra en el panel del cuerpo del cuadro de diálogo Detalles del mensaje se corresponde con MT103_Invalid_Sample.txt que abrió en el Bloc de notas.  
  
    Continúe con [lección 3: probar una instancia XML](../../adapters-and-accelerators/accelerator-swift/lesson-3-testing-an-xml-instance.md).