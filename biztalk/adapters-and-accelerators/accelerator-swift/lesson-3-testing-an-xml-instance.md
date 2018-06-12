---
title: 'Lección 3: Probar una instancia XML | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, XML instances
- XML instances
ms.assetid: 19d7dd18-17dc-4355-a4f1-5c5e6750faf3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcb9d5ada3054219b1387d92f4244475037c26ac
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848900"
---
# <a name="lesson-3-testing-an-xml-instance"></a>Lección 3: Probar una instancia XML
En esta lección, se envía un MT103 válido que creó en las lecciones anteriores de puertos de recepción de mensaje en formato XML en el archivo. Esta acción comprueba las canalizaciones de envío que creó en módulos anteriores. [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] Escribe la salida como un archivo sin formato en la carpeta de salida que seleccionó para el puerto de envío en el módulo anterior.  
  
 Iniciar el archivo de adaptador de recepción mediante la copia de un archivo con formato XML de SWIFT a la carpeta entrante. Esta acción hace que el sistema copia un archivo plano SWIFT válido a la carpeta de salida.  
  
### <a name="to-test-an-xml-instance"></a>Para probar una instancia XML  
  
1.  En el Explorador de Windows, abra \< *unidad*\>: \Labs\Outbound. Compruebe que esta carpeta contiene el archivo de {GUID} .xml que ha enviado a esta carpeta en [lección 1: enviar un archivo plano de ejemplo](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md) de este módulo.  
  
2.  Copie el archivo XML y péguelo en \< *unidad*\>: \Labs\Inbound\XMLFile. Tenga en cuenta el tiempo que pegó este archivo.  
  
3.  Mover a \< *unidad*\>: \Labs\Outbound. Compruebe que hay un archivo denominado .txt {GUID} en esta carpeta y que la hora en la columna de fecha de modificación de este archivo se corresponde con el tiempo que pegar el archivo en \< *unidad*\>: \Labs\Inbound\ XMLFile.  
  
4.  En el Bloc de notas, abra MT103_Sample.txt en \< *unidad*\>: \Program Acelerador de BizTalk para SWIFT\SDK\Tutorial.  
  
5.  En otra instancia del Bloc de notas, abra .txt {GUID} en \< *unidad*\>: \Labs\Inbound\XMLFile.  
  
6.  Compruebe que los dos archivos en el Bloc de notas contienen el mismo contenido.  
  
 Continúe con [módulo 8: reparar un mensaje no válido](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d).