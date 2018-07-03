---
title: 'Lección 3: Probar una instancia XML | Microsoft Docs'
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
ms.openlocfilehash: 5660ab4e67545b1b98785aedeaeea6e123b6d008
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971901"
---
# <a name="lesson-3-testing-an-xml-instance"></a>Lección 3: Probar una instancia XML
En esta lección, envíe un MT103 válido creados en las lecciones anteriores de los puertos de recepción de mensajes en formato XML en el archivo. Esta acción comprueba las canalizaciones de envío que creó en los módulos anteriores. Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] escribe la salida como un archivo sin formato en la carpeta de salida que seleccionó para el puerto de envío en el módulo anterior.  
  
 Iniciar el archivo copiando un archivo con formato XML de SWIFT a la carpeta de entrada del adaptador de recepción. Esta acción da como resultado el sistema copiando un archivo plano SWIFT válido en la carpeta saliente.  
  
### <a name="to-test-an-xml-instance"></a>Para probar una instancia XML  
  
1. En el Explorador de Windows, abra \< *unidad*\>: \Labs\Outbound. Compruebe que esta carpeta contiene el archivo de {GUID} .xml que envía a esta carpeta en [lección 1: envío de un archivo plano de ejemplo](../../adapters-and-accelerators/accelerator-swift/lesson-1-submitting-a-sample-flat-file.md) de este módulo.  
  
2. Copie el archivo XML y péguelo en \< *unidad*\>: \Labs\Inbound\XMLFile. Tenga en cuenta el tiempo que pegó este archivo.  
  
3. Mover a \< *unidad*\>: \Labs\Outbound. Compruebe que hay un archivo denominado {GUID} .txt en esta carpeta, y que la hora en la columna de fecha de modificación de este archivo se corresponde con el tiempo que pegó en el archivo de \< *unidad*\>: \Labs\Inbound\ XMLFile.  
  
4. En el Bloc de notas, abra MT103_Sample.txt en \< *unidad*\>: Acelerador de BizTalk para SWIFT\SDK\Tutorial \Program Files\Microsoft.  
  
5. En otra instancia del Bloc de notas, abra {GUID} .txt en \< *unidad*\>: \Labs\Inbound\XMLFile.  
  
6. Compruebe que los dos archivos en el Bloc de notas contienen el mismo contenido.  
  
   Continúe con [módulo 8: reparación de un mensaje no válido](http://msdn.microsoft.com/fb531b22-ac7a-4620-b395-87aebf56077d).