---
title: Ejecutar el ejemplo de componente Namespace | Microsoft Docs
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
ms.openlocfilehash: 83a24d2720fd9c46bd1d5ccb70d92a068f8a2ec4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021737"
---
# <a name="running-the-namespace-component-sample"></a>Ejecutar el ejemplo de componente de Namespace
La aplicación de ejemplo de componente Namespace contiene cuatro pares de puertos de envío o ubicación de recepción. Cada par representa una prueba. Estas son las cuatro pruebas:  

- **Agregar a paso a través**. Esta prueba agrega un espacio de nombres a un documento XML del mensaje y escribe el mensaje directamente en un archivo para que puedan ver el nuevo espacio de nombres. El archivo de entrada para esta prueba es TEST_Add_to_PassThrough.0000.ns.xml. Esta prueba usa el **NamespaceSampleReceivePipeline** que contiene un **AddNamespace** componente.  

- **Agregar a Remove**. Esta prueba agrega un espacio de nombres en un mensaje de documento XML y después lo quita. A continuación, escribe el mensaje directamente a un archivo. El archivo de entrada para esta prueba es Add_to_Remove.0000.ns.xml TEST_. Esta prueba usa el **NamespaceSampleReceivePipeline** que contiene un **AddNamespace** componente y la **NamespaceSampleSendPipeline** que contiene un **RemoveNamespace** componente.  

- **Acceso directo para quitar**. Esta prueba quita todos los espacios de nombres de un mensaje de documento XML y escribe el mensaje directamente en un archivo para que pueda confirmar esto. El archivo de entrada para esta prueba es TEST_PassThrough_to_Remove.0000.ns.xml. Esta prueba usa el **NamespaceSampleSendPipeline** que contiene un **RemoveNamespace** componente.  

- **Agregar a través de la extracción de paso a través**. Esta prueba extrae la **OrderDetails** elemento de un documento XML de documento mensaje y escribe un mensaje nuevo que contiene este elemento directamente en un archivo. El archivo de entrada para esta prueba es TEST_AddViaExtraction_to_PassThrough.0000.ns.xml. Esta prueba usa el **NamespaceSampleReceivePipeline** que contiene un **AddNamespace** componente con el **ExtractionNodeXPath** propiedad establecida en **/ CanonicalOrder/OrderDetails** (cualquier expresión XPath válida que devuelve un elemento será suficiente para esta propiedad).  

  Las ubicaciones de recepción subyacente en la aplicación de ejemplo tienen máscaras de archivo que son adecuadas para cada uno de los tipos de pruebas, y que se relaciona filtro de puertos de envío en el nombre del puerto de recepción. Por lo tanto, para ejecutar una prueba, simplemente coloque el mensaje con el nombre adecuado en la carpeta de entrada. Ejecuta la prueba de la aplicación de ejemplo y coloca el mensaje actualizado en la carpeta de salida con un nombre adecuado para la prueba actual e incluir el identificador de mensaje.  

  Esta sección contiene los siguientes temas:  

- [Ejecución de las pruebas de componente de espacio de nombres](../esb-toolkit/running-the-namespace-component-tests.md)  

- [Cómo funciona el ejemplo Agregar espacio de nombres](../esb-toolkit/how-the-add-namespace-sample-works.md)  

- [Cómo funciona el ejemplo Quitar espacio de nombres](../esb-toolkit/how-the-remove-namespace-sample-works.md)
