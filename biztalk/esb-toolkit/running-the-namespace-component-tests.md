---
title: Ejecuta las pruebas de componente de Namespace | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13768608-ade6-44c0-897f-d417c3408302
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ae865e91fd6ff796cb870c71840bde8a95831e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294940"
---
# <a name="running-the-namespace-component-tests"></a>Ejecuta las pruebas de componente de Namespace
El siguiente procedimiento muestra cómo ejecutar los cuatro de los escenarios de prueba para el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] del ejemplo de componente de Namespace.  
  
 **Para ejecutar el componente de Namespace escenarios de prueba de ejemplo**  
  
1.  Antes de ejecutar este ejemplo por primera vez, asegúrese de que la recepción dirección URL de puerto de ubicación y envío apuntar a las subcarpetas correspondientes en los archivos de distribución de origen. Especifique el \Source\Samples\Namespace\Test\Filedrop\In subcarpeta de la ubicación de recepción y el \Source\Samples\Namespace\Test\Filedrop\Out subcarpeta para la dirección URL de puerto de envío.  
  
2.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de Microsoft BizTalk para iniciarlo.  
  
3.  Realice una copia del archivo denominado TEST_Add_to_PassThrough.0000.ns.xml (que se encuentra en la subcarpeta \Source\Samples\Namespace\Test\Data\ de la carpeta de instalación de ESB) y cambiar el nombre de la copia mediante la eliminación del prefijo "TEST_".  
  
4.  Copie el archivo renombrado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\In.  
  
5.  ESB recoge el mensaje, agrega un espacio de nombres y coloca el mensaje actualizado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\Out. Abra la entrada y salida de archivos en un editor de texto para ver el efecto de esta prueba.  
  
6.  Ahora ejecute la segunda prueba. Realizar una copia del archivo denominado TEST_Add_to_Remove.0000.ns.xml y cambie su nombre mediante la eliminación del prefijo "TEST_".  
  
7.  Copie el archivo renombrado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\In.  
  
8.  ESB recoge el mensaje, agrega un espacio de nombres, quita el espacio de nombres nuevo y coloca el mensaje actualizado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\Out. Abra la entrada y salida de archivos en un editor de texto para ver el efecto de esta prueba.  
  
9. Ahora ejecute la prueba terceros. Realizar una copia del archivo denominado TEST_PassThrough_to_Remove.0000.ns.xml y cambie su nombre mediante la eliminación del prefijo "TEST_".  
  
10. Copie el archivo renombrado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\In.  
  
11. ESB recoge el mensaje, quita el espacio de nombres existente y coloca el mensaje actualizado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\Out. Abra la entrada y salida de archivos en un editor de texto para ver el efecto de esta prueba.  
  
12. Por último, ejecute la cuarta de pruebas. Realizar una copia del archivo denominado TEST_AddViaExtraction_to_PassThrough.0000.ns.xml y cambie su nombre mediante la eliminación del prefijo "TEST_".  
  
13. Copie el archivo renombrado en la subcarpeta \Source\Samples\Namespace\Test\Filedrop\In.  
  
14. ESB recoge el mensaje, se extrae el elemento especificado en el **ExtractionNodeXPath** propiedad, crea un mensaje de este elemento con los valores de espacio de nombres especificado y coloca el mensaje actualizado en el \Source\Samples\ Subcarpeta Namespace\Test\Filedrop\Out. Abra la entrada y salida de archivos en un editor de texto para ver el efecto de esta prueba.