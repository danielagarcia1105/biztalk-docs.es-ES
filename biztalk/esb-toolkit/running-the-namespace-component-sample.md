---
title: Ejecutar el ejemplo de componente de Namespace | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f334a8-06de-4a56-a41a-3df088bf4a72
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fc142ca70971f023e491dbdeee693a8d41c42fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295300"
---
# <a name="running-the-namespace-component-sample"></a>Ejecutar el ejemplo de componente de Namespace
La aplicación de ejemplo de componente de Namespace contiene cuatro pares de puertos de envío o ubicación de recepción. Cada par representa una prueba. Éstas son las cuatro pruebas:  
  
-   **Agregar a paso a través**. Esta prueba agrega un espacio de nombres a un documento XML del mensaje y escribe el mensaje directamente a un archivo para que pueda comprobar el espacio de nombres nuevo. El archivo de entrada para esta prueba es TEST_Add_to_PassThrough.0000.ns.xml. Esta prueba utiliza la **NamespaceSampleReceivePipeline** que contiene un **AddNamespace** componente.  
  
-   **Agregar a Remove**. Esta prueba agrega un espacio de nombres en un mensaje de documento XML y, a continuación, quita. A continuación, escribe el mensaje directamente a un archivo. El archivo de entrada para esta prueba es TEST_ Add_to_Remove.0000.ns.xml. Esta prueba utiliza la **NamespaceSampleReceivePipeline** que contiene un **AddNamespace** componente y el **NamespaceSampleSendPipeline** que contiene un **RemoveNamespace** componente.  
  
-   **Acceso directo para quitar**. Esta prueba quita todos los espacios de nombres de un mensaje de documentos XML y escribe el mensaje directamente a un archivo para que pueda confirmar esto. El archivo de entrada para esta prueba es TEST_PassThrough_to_Remove.0000.ns.xml. Esta prueba utiliza la **NamespaceSampleSendPipeline** que contiene un **RemoveNamespace** componente.  
  
-   **Agregar a través de extracción para el acceso directo**. Esta prueba extrae el **OrderDetails** elemento de un documento XML de documento mensaje y escribe un mensaje nuevo que contiene este elemento directamente en un archivo. El archivo de entrada para esta prueba es TEST_AddViaExtraction_to_PassThrough.0000.ns.xml. Esta prueba utiliza la **NamespaceSampleReceivePipeline** que contiene un **AddNamespace** componente con el **ExtractionNodeXPath** propiedad establecida en **/ CanonicalOrder/OrderDetails** (cualquier expresión XPath válida que devuelve un elemento será suficiente para esta propiedad).  
  
 Las ubicaciones de recepción subyacente en la aplicación de ejemplo tienen máscaras de archivo que son adecuadas para cada uno de los tipos de pruebas y relacionado filtro de puertos de envío en el nombre de puerto de recepción. Por lo tanto, para ejecutar una prueba, simplemente depositar el mensaje con el nombre adecuado en la carpeta de entrada. La aplicación de ejemplo ejecuta la prueba y coloca el mensaje actualizado en la carpeta de salida con un nombre adecuado para la prueba actual e incluir el identificador de mensaje.  
  
 Esta sección contiene los siguientes temas:  
  
-   [Ejecuta las pruebas de componente de Namespace](../esb-toolkit/running-the-namespace-component-tests.md)  
  
-   [Cómo agregar Namespace ejemplo funciona](../esb-toolkit/how-the-add-namespace-sample-works.md)  
  
-   [Cómo funciona el ejemplo de Namespace Remove](../esb-toolkit/how-the-remove-namespace-sample-works.md)